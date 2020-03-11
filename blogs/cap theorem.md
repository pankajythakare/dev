[[_TOC_]]

A very common question for system design. Which database should I use and why should I use? So below question is foundation for starting with requirements to understand needs, use cases and data.

# What is CAP theorem?<a name="cap"></a>
**CAP or Brewers** theorem states that it is highly impossible for distributed data store to simultaneously provide more than two out of 
1. Consistency - All nodes or instances display same the data at same time.
2. Availability - Replication of data on different servers to display success/failure on each request.
3. Partition Tolerance - Data is replicated across combinations of nodes and network to tolerate outages.

We cannot have all above three for any distributed data store as to be consistent, all nodes should be updated in an order simultaneously. If any network issue can cause partition failure impacting other nodes and consumers may point to old data set. To overcome this, data store can stop serving requests on out-of-date partitions and hence availability will have an impact.

When network partition failure starts to happen should we
* cancel the operation?
* proceed with operation?

Since we now understand what theorem states, let's dig more into databases.

#SQL Database <a name="sql"></a>
These are relational databases like MS SQL Server, MySQL, SqlLite, PostgreSql etc. which stores data in predefined schema as rows and column. Each table will have columns and their schema and then data is stored in rows as a different data points. 
SQL Databases use Structured Query Language (SQL) to perform computations on data stored. Transactions and relational data are perfect candidates for those databases. To scale-up those databases to handle load and performance, only vertical scaling is supported, where very costly hardware upgrades for RAM, CPU etc. upgrades are required. Horizontal scaling is supported but its a very time consuming complex process and hence not preferred. To maintain high availability, they can be run in cluster where node failures can be done on alternate instance running.

*Fact*: [Stackoverflow](https://stackoverflow.com) which is highly used by developer community across globe uses SQL server for data storage.

#NoSQL Database: <a name="nosql"></a>
These databases are not relational and they support unstructured data.
 
##Key-Value database <a name="key-value"></a>
Redis, DynamoDb are some of the examples of key-value database. Redis is well-known for caching strategy due to high performance, availability and security.
Aws offers DnynamoDb which is highly used for serverless applications.

##Document database <a name="document"></a>
MongoDb and CouchDb are some of the examples of document database where each document can have any shaped data and always stored under collection which is group of documents. Each document can be different and unique in shape.

##Columnar database (Wide Column Database) <a name="wide-column"></a>
Instead of tables, it does have column families which are containers for rows. Each row can have different columns and hence suitable for large datasets and analytics. Well known examples are Cassandra & HBase.

##Graph database <a name="graph"></a>
Used frequently to store data which is in graph format where we have a node, properties for a node and lines for each property. Widely used ones are Neo4J and Infinite Graph.

#Which one to use? <a name="use"></a>

###For SQL <a name="use-sql"></a>
* If Data is well structured and differs change.
* If ACID principle (atomic, consistency, isolation and durability) needs to be ensured for a data being processed. Mostly e-commerce and financial institution prefer their data to follow ACID.

###For NoSQL <a name="use-nosql"></a>
* If volume of data is huge and data is unstructured or less structured
* If leveraging cloud provided services and offerings
* If low cost and high performance are requirements
* If rapid development aimed

Even though most of the NoSQL databases are gaining popularity in market, still there are few use cases and businesses which prefers SQL databases and gain performance comparatively. Choosing right database to get most out of it really depends upon the data, use case, and business needs as per CAP.

Always remember to consider those factors while designing distributed application data store, use cases implementation and data processing.

Please share your thoughts and feedback.