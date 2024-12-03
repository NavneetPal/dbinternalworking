
# DataSource
The default DataSource in Sprint Boot is HikariDataSource.

````
A factory for connections to the physical data source that this DataSource object represents. An alternative to the DriverManager facility, a DataSource object is the preferred means of getting a connection. An object that implements the DataSource interface will typically be registered with a naming service based on the Java Naming and Directory (JNDI) API.
The DataSource interface is implemented by a driver vendor. 

There are three types of implementations:
1.Basic implementation -- produces a standard Connection object
2.Connection pooling implementation -- produces a Connection object that will automatically participate in connection pooling. This implementation works with a middle-tier connection pooling manager.
3.Distributed transaction implementation -- produces a Connection object that may be used for distributed transactions and almost always participates in connection pooling. This implementation works with a middle-tier transaction manager and almost always with a connection pooling manager.

A DataSource object has properties that can be modified when necessary. For example, if the data source is moved to a different server, the property for the server can be changed. The benefit is that because the data source's properties can be changed, any code accessing that data source does not need to be changed.
A driver that is accessed via a DataSource object does not register itself with the DriverManager. Rather, a DataSource object is retrieved through a lookup operation and then used to create a Connection object. With a basic implementation, the connection obtained through a Dat

````

DriverManagerDataSource is just for the development purpose as it lacks the connection polling concept. 
It's the simple implementation of the standard JDBC DataSource interface, configuring the plain old JDBC DriverManager via bean properties, and returning a new Connection from every getConnection call. 