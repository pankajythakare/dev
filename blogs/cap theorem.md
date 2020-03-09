[[_TOC_]]

# What is CAP theorem?
CAP or Brewers theorem states that it is highly impossible for distributed data store to simultaneously provide more than two out of 
    Consistency
    Availability
    Partition Tolerance

When network partition failure starts to happen should we
    cancel the operation?
    proceed with operation?

![CAP.png](/.attachments/CAP-8ac6ff05-94ed-4fea-ba98-e2f7e8d6c454.png)

This is the point which helps in deciding the database to use according to needs and use cases.

#SQL Database
 Those are relation databases like MS SQL Server, MySQL, SqlLite, PostgreSql etc which stores data in predefined schema as rows and column. Each table will have columns and their schema and then data is stored in rows as a different data points. SQL Databases use Structured Query Language (SQL) to perform computations on data stored and they are very high performance. Transactional and relational data is perfect candidate for those databases. To scale-up those databases, only vertical scaling where very costly hardware upgrades for RAM, CPU etc upgrades are required to improve performance and computation. Horizontal scaling is supported but time consuming complex process and hence not preferred. To maintain high availability, they can be run in cluster where node failures can be done on alternate instance running.
Fun Fact: Stackoverflow which is highly used by developer community across globe does make use of SQL server to serve 5K requests/sec on single instance backed by failover instance.

#NoSQL Database:
Those databases are not relational and they support unstructured data. 
##Key-Value database
Redis, DynamoDb are some of the examples of key-value database. Redis is well-known for caching strategy as it's high performance, availability and secure database.
##Document database
MongoDb and CouchDb are some of the examples of document database where each document can have any shaped data and always stored under collection which is group of collections. Each document can be different and unique.
##Columnar database (Wide Column Database)
Instead of tables, it does have column families which are containers for rows. Each row can have different columns and hence suitable for large datasets and analytics. Well known examples are Cassandra & HBase.
##Graph database
Used frequently to store data which is in graph format where we have a node, properties for a node and lines for each property. Widely used ones are Neo4J and Infinite Graph.

#Which one to use?
###For SQL 
If Data is well structured and differs change.
If ACID principle which is for atomic, consistency, isolation and durability needs to be ensured for a data being processed. e-commerce and financial institution requires their data to follow ACID and hence widely used.

###For NoSQL
Volume of Data and data is unstructured or less structured
Leveraging cloud provided services and offerings
Low cost and high performance
Rapid development

Even though most of the NoSQL databases are gaining popularity in market, still there are few use cases and businesses which prefers and perform SQL databases comparatively. Choosing right database to get most out of it really depends upon the data, use case, and business needs as per CAP. Feel free to explore more and learn about individual databases in depth which will give you more perspective to make decisions.

In next, I will go through details of individual databases and how to use them. Thank you!