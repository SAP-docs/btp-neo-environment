<!-- loio937ca0a472bb101490cf767db0e91070 -->

# Creating SAP HANA Column-Store Tables

The SAP HANA database lets you create tables with row-based storage or column-based storage. By default, tables are created with row-based storage, but you can change the type of table storage you have applied, if necessary.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The example below shows the SQL syntax used by the SAP HANA database to create different table types. The first two SQL statements both create row-store tables, the third a column-store table, and the fourth changes the table type from row-store to column-store:

```sql

CREATE TABLE T_PERSON
CREATE ROW TABLE T_PERSON
CREATE COLUMN TABLE T_PERSON
ALTER TABLE T_PERSON COLUMN

```



<a name="loio937ca0a472bb101490cf767db0e91070__section_B4570A426CE447598463351D434CF00E"/>

## EclipseLink JPA

When using EclipseLink JPA for data persistence, the table type applied by default in the SAP HANA database is row-store. To create a column-store table or alter an existing row-store table, you can manually modify your database using SQL DDL statements, or you can use open source tools, such as Liquibase \(with plain SQL statements\), to handle automated database migrations.

Due to the limitations of the EclipseLink schema generation feature, you'll need to use one of the above options to handle the life cycle management of your database objects.



<a name="loio937ca0a472bb101490cf767db0e91070__section_A52B41E773744C6083308E9729133668"/>

## ALTER TABLE Example

You can use the ALTER TABLE statement to change a row-store table in the SAP HANA database to a column-store table. The example is based on the *Adding Application-Managed Persistence with JPA \(SDK for Java Web\)* tutorial and has been designed specifically for this tutorial and use case.

The example allows you to take advantage of the automatic table generation feature provided by JPA EclipseLink. You merely alter the existing table at an appropriate point, when the schema containing the relevant table has just been created. The applicable code snippet is added to the `init()` method of the servlet \(`PersistenceWithJPAServlet`\). The main changes to the servlet code are outlined below:

1.  Since the table must already exist when the ALTER statement is called, a small workaround has been introduced in the `init()` method. An entity manager is created at an earlier stage than in the original version of the tutorial to trigger the generation of the schema:

    ```
    
    //workaround: create EntityManager to trigger schema generation
    emf.createEntityManager().close();
    
    ```

2.  The SAP HANA database table SYS.M\_TABLES contains information about all row and column tables in the current schema. A new method, which uses this table to check that T\_PERSON is not already a column-store table, has been added to the servlet.
3.  Another new method alters the table using the SQL statement ALTER TABLE <table name\> COLUMN.

To apply the solution, replace the entire servlet class `PersistenceWithJPAServlet` with the following content:

```

package com.sap.cloud.sample.persistence;

import java.io.IOException;
import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

import javax.naming.InitialContext;
import javax.naming.NamingException;
import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.Persistence;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.sql.DataSource;

import org.eclipse.persistence.config.PersistenceUnitProperties;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

import com.sap.security.core.server.csi.IXSSEncoder;
import com.sap.security.core.server.csi.XSSEncoder;

/**
* Servlet implementing a simple JPA based persistence sample application for SAP BTP.
 */
public class PersistenceWithJPAServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;
    private static final Logger LOGGER = LoggerFactory.getLogger(PersistenceWithJPAServlet.class);
    private static final String SQL_GET_TABLE_TYPE = "SELECT TABLE_NAME, TABLE_TYPE FROM SYS.M_TABLES WHERE TABLE_NAME = ?";
    private static final String PERSON_TABLE_NAME = "T_PERSON";

    private DataSource ds;
    private EntityManagerFactory emf;

    /** {@inheritDoc} */
    @SuppressWarnings({ "rawtypes", "unchecked" })
    @Override
    public void init() throws ServletException {
        Connection connection = null;
        try {
            InitialContext ctx = new InitialContext();
            ds = (DataSource) ctx.lookup("java:comp/env/jdbc/DefaultDB");

            Map properties = new HashMap();
            properties.put(PersistenceUnitProperties.NON_JTA_DATASOURCE, ds);
            boolean onHANA = runsOnHANADatabase();
            if (onHANA) {
                properties.put("eclipselink.target-database", "com.sap.persistence.platform.database.HDBPlatform");
            }

            emf = Persistence.createEntityManagerFactory("persistence-with-jpa", properties);

            // convert T_PERSON to column table
            // workaround: create EntityManager to trigger schema generation
            emf.createEntityManager().close();
            if (onHANA) {
            	convertToColumnTable(PERSON_TABLE_NAME);
            }
        } catch (NamingException e) {
            throw new ServletException(e);
        } catch (SQLException e) {
            LOGGER.error("Could not determine database product.", e);
            throw new ServletException(e);
        } finally {
            if (connection != null) {
                try {
                    connection.close();
                } catch (SQLException x) {
                    LOGGER.debug("Unable to close connection.", x);
                }
            }
        }
    }

    /** {@inheritDoc} */
    @Override
    public void destroy() {
        emf.close();
    }

    /** {@inheritDoc} */
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.getWriter().println("<p>Persistence with JPA Sample!</p>");
        try {
            appendPersonTable(response);
            appendAddForm(response);
        } catch (Exception e) {
            response.getWriter().println("Persistence operation failed with reason: " + e.getMessage());
            LOGGER.error("Persistence operation failed", e);
        }
    }

    /** {@inheritDoc} */
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException,
            IOException {
        try {
            doAdd(request);
            doGet(request, response);
        } catch (Exception e) {
            response.getWriter().println("Persistence operation failed with reason: " + e.getMessage());
            LOGGER.error("Persistence operation failed", e);
        }
    }

    private void appendPersonTable(HttpServletResponse response) throws SQLException, IOException {
        // Append table that lists all persons
        EntityManager em = emf.createEntityManager();
        try {
            @SuppressWarnings("unchecked")
            List<Person> resultList = em.createNamedQuery("AllPersons").getResultList();
            response.getWriter().println(
                    "<p><table border=\"1\"><tr><th colspan=\"3\">"
                            + (resultList.isEmpty() ? "" : resultList.size() + " ")
                            + "Entries in the Database</th></tr>");
            if (resultList.isEmpty()) {
                response.getWriter().println("<tr><td colspan=\"3\">Database is empty</td></tr>");
            } else {
                response.getWriter().println("<tr><th>First name</th><th>Last name</th><th>Id</th></tr>");
            }
            IXSSEncoder xssEncoder = XSSEncoder.getInstance();
            for (Person p : resultList) {
                response.getWriter().println(
                        "<tr><td>" + xssEncoder.encodeHTML(p.getFirstName()) + "</td><td>"
                                + xssEncoder.encodeHTML(p.getLastName()) + "</td><td>" + p.getId() + "</td></tr>");
            }
            response.getWriter().println("</table></p>");
        } finally {
            em.close();
        }
    }

    private void appendAddForm(HttpServletResponse response) throws IOException {
        // Append form through which new persons can be added
        response.getWriter().println(
                "<p><form action=\"\" method=\"post\">" + "First name:<input type=\"text\" name=\"FirstName\">"
                        + "&nbsp;Last name:<input type=\"text\" name=\"LastName\">"
                        + "&nbsp;<input type=\"submit\" value=\"Add Person\">" + "</form></p>");
    }

    private void doAdd(HttpServletRequest request) throws ServletException, IOException, SQLException {
        // Extract name of person to be added from request
        String firstName = request.getParameter("FirstName");
        String lastName = request.getParameter("LastName");

        // Add person if name is not null/empty
        EntityManager em = emf.createEntityManager();
        try {
            if (firstName != null && lastName != null && !firstName.trim().isEmpty() && !lastName.trim().isEmpty()) {
                Person person = new Person();
                person.setFirstName(firstName);
                person.setLastName(lastName);
                em.getTransaction().begin();
                em.persist(person);
                em.getTransaction().commit();
            }
        } finally {
            em.close();
        }
    }

    private boolean runsOnHANADatabase() throws SQLException {
    	boolean onHANA = false;
        Connection connection = ds.getConnection();
        try {
	        String databaseProductName = connection.getMetaData().getDatabaseProductName();
	        if (databaseProductName.equals("HDB")) {
	            onHANA = true;
	        }
        } finally {
        	connection.close();
        }
        return onHANA;
    }

    private void convertToColumnTable(String tableName) throws SQLException {
    	if (!isColumnTable(tableName)) {
	    	Connection connection = ds.getConnection();
	    	try {
	    		String sql = "ALTER TABLE " + tableName + " COLUMN";
	    		PreparedStatement stmt = connection.prepareStatement(sql);
	    		stmt.executeUpdate();
	    		stmt.close();
	    	} finally {
	    		connection.close();
	    	}
    	}
    }

    private boolean isColumnTable(String tableName) throws SQLException {
    	boolean exists = false;
    	boolean columnTable = false;
    	Connection connection = ds.getConnection();
    	String tableTypeStart = null;
    	try {
	    	PreparedStatement stmt = connection.prepareStatement(SQL_GET_TABLE_TYPE);
	    	stmt.setString(1, tableName);
	    	ResultSet rs = stmt.executeQuery();
	    	while (rs.next()) {
	    		exists = true;
	    		tableTypeStart = rs.getString(2);
	    		break;
	    	}
	    	rs.close();
	    	if (!exists) {
	    		throw new SQLException("Table " + tableName + " does not exist");
	    	}
	    	if (tableTypeStart.equalsIgnoreCase("COLUMN")) {
	    		columnTable = true;
	    	}
    	} finally {
    		connection.close();
    	}
    	return columnTable;
    }
}

```

**Related Information**  


[Tutorial: Adding Application-Managed Persistence with JPA \(SDK for Java Web\)](tutorial-adding-application-managed-persistence-with-jpa-sdk-for-java-web-e4aeacd.md#loioe4aeacd2bb5710148ee99255136d96a5 "Use JPA to apply application-managed persistence in a simple Java EE web application that manages a list of persons.")

