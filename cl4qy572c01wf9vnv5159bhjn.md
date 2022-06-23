## How to connect with SQL database using java?(JDBC connectivity)

> **prerequisites:**
> 
> 1) WAMPSERVER
> 
> 2) Eclipse/Apache NetBeans IDE

**The Java Database Connectivity (JDBC) API:**

Java Database Connectivity (JDBC) is an application programming interface (API) which defines how a client may access a database. JDBC is like a bridge between a Java application and a database. Let's see a step-by-step implementation of JDBC connectivity in java.

**step 1:** open WAMPSERVER and click phpmyadmin option. By default the username is root and password is empty ("") and click go option.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655959824189/bFenJCw1U.png align="left")

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655959505009/4vIqr-p0W.png align="left")

**step 2:** open your favourite java IDE to type the following code.

**CREATE DATABASE:**(DatabaseCreation.java)

```

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class DatabaseCreation {
   static final String DB_URL = "jdbc:mysql://localhost/";
   static final String USER = "root";
   static final String PASS = "";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
         String sql = "CREATE DATABASE JAVADATABASE";
         stmt.executeUpdate(sql);
         System.out.println("Database created successfully...");   	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}

``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655961557741/hont1pTWZ.png align="left")

**CREATE TABLE:**(CreateTable.java)

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class CreateTable {
   static final String DB_URL = "jdbc:mysql://localhost/JAVADATABASE";
   static final String USER = "root";
   static final String PASS = "";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
          String sql = "CREATE TABLE REGISTRATION " +
                   "(id INTEGER not NULL, " +
                   " first VARCHAR(255), " + 
                   " last VARCHAR(255), " + 
                   " age INTEGER, " + 
                   " PRIMARY KEY ( id ))"; 

         stmt.executeUpdate(sql);
         System.out.println("Created table in given database...");   	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655981222070/72s-sRSdY.png align="left")


**INSERTION:**(Insertion.java)

```

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class Insertion {
   static final String DB_URL = "jdbc:mysql://localhost/JAVADATABASE";
   static final String USER = "root";
   static final String PASS = "";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
          String sql = "INSERT INTO REGISTRATION VALUES (1,'Naveen','kumar',20)"; 
          stmt.executeUpdate(sql);
          System.out.println("Value inserted in table successfully....");  	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655981071685/ru4u3NF4w.png align="left")

**
UPDATION:**(UpdateTable.java)

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.sql.Statement;

public class UpdateTable {
   static final String DB_URL = "jdbc:mysql://localhost/JAVADATABASE";
   static final String USER = "root";
   static final String PASS = "";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
          PreparedStatement ps=conn.prepareStatement("update registration set id=? where first=?");
          ps.setInt(1,101);
          ps.setString(2,"Naveen");
          ps.executeUpdate();  
          System.out.print("Updation done successfully.......");
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
```
 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655981808132/u6h1oDv8v.png align="left")

**SELECTION:**(Selection.java)

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class Selection {
   static final String DB_URL = "jdbc:mysql://localhost/JAVADATABASE";
   static final String USER = "root";
   static final String PASS = "";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
    	  String strSelect="select * from registration";
		  System.out.println("The SQL statement is: "+strSelect+"\n");
		  ResultSet rs=stmt.executeQuery(strSelect);
			while(rs.next()) {
				System.out.println(rs.getInt(1)+", "+rs.getString(2)+rs.getString(3)+", "+rs.getInt(4));
			}
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655982123350/70binA4oc.png align="left")

**DELETION:**(Deletion.java)

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class Deletion {
   static final String DB_URL = "jdbc:mysql://localhost/JAVADATABASE";
   static final String USER = "root";
   static final String PASS = "";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
    	  String sql="delete from registration where id='101'";
          stmt.executeUpdate(sql);
          System.out.println("Deletion done successfully.....");
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655982534814/mH8z9DQM9.png align="left")








