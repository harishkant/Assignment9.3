# Assignment9.3

Explain the below concepts with an example in brief.


Nosql Databases
NoSQL is an approach to database design that can accomodate a wide variety of data models, including key-value, document, columnar and graph formats. NoSQL, which stand for "not only SQL," is an alternative to traditional relational databases in which data is placed in tables and data schema is carefully designed before the database is built. NoSQL databases are especially useful for working with large sets of distributed data.

Key-value stores
Key-value stores, or key-value databases, implement a simple data model that pairs a unique key with an associated value. Because this model is simple, it can lead to the development of key-value databases, which are extremely performant and highly scalable for session management and caching in web applications. Implementations differ in the way they are oriented to work with RAM, solid-state drives or disk drives. Examples include Aerospike, Berkeley DB, MemchacheDB, Redis and Riak.


Types of Nosql Databases

Document databases
Document databases, also called document stores, store semi-structured data and descriptions of that data in document format. They allow developers to create and update programs without needing to reference master schema. Use of document databases has increased along with use of JavaScript and the JavaScript Object Notation (JSON), a data interchange format that has gained wide currency among web application developers, although XML and other data formats can be used as well.  Document databases are used for content management and mobile application data handling. Couchbase Server, CouchDB, DocumentDB, MarkLogic and MongoDB are examples of document databases.
Wide-column stores
Wide-column stores organize data tables as columns instead of as rows. Wide-column stores can be found both in SQL and NoSQL databases. Wide-column stores can query large data volumes faster than conventional relational databases. A wide-column data store can be used for recommendation engines, catalogs, fraud detection and other types of data processing.  Google BigTable, Cassandra and HBase are examples of wide-column stores.
Graph stores
Graph data stores organize data as nodes, which are like records in a relational database, and edges, which represent connections between nodes. Because the graph system stores the relationship between nodes, it can support richer representations of data relationships. Also, unlike relational models reliant on strict schemas, the graph data model can evolve over time and use. Graph databases are applied in systems that must map relationships, such as reservation systems or customer relationship management. Examples of graph databases include AllegroGraph, IBM Graph, Neo4j and Titan.
Evolution of NoSQL
Berkeley DB was an influential system in the early evolution of NoSQL database usage. Developed at the University of California, Berkeley, beginning in the 1990s, Berkeley DB was widely described as an embedded database that closely supported specific applications' storage needs. This open source software provided a simple key-value store. Berkeley DB was commercially released by Sleepycat Software in 1999. The company was later acquired by Oracle in 2006. Oracle has continued to support open source Berkeley DB.


CAP Theorem

CAP Theorem reiterates the need to find balance between Consistency, Availability and Partition tolerance. Consistency means all the nodes see the same data at the same time. Availability implies that every request receives a response about whether it was successful or failed. It’s more of a handshaking mechanism in computer network methodology.
Coming to partition tolerance, the system continues to operate despite arbitrary message loss or failure of part of the system. Systems with partition tolerance feature works well despite physical network partitions.

Wide-column stores organize data tables as columns instead of as rows. Wide-column stores can be found both in SQL and NoSQL databases. Wide-column stores can query large data volumes faster than conventional relational databases. A wide-column data store can be used for recommendation engines, catalogs, fraud detection and other types of data processing.  Google BigTable, Cassandra and HBase are examples of wide-column stores.
Graph stores
Graph data stores organize data as nodes, which are like records in a relational database, and edges, which represent connections between nodes. Because the graph system stores the relationship between nodes, it can support richer representations of data relationships. Also, unlike relational models reliant on strict schemas, the graph data model can evolve over time and use. Graph databases are applied in systems that must map relationships, such as reservation systems or customer relationship management. Examples of graph databases include AllegroGraph, IBM Graph, Neo4j and Titan.
Evolution of NoSQL
Berkeley DB was an influential system in the early evolution of NoSQL database usage. Developed at the University of California, Berkeley, beginning in the 1990s, Berkeley DB was widely described as an embedded database that closely supported specific applications' storage needs. This open source software provided a simple key-value store. Berkeley DB was commercially released by Sleepycat Software in 1999. The company was later acquired by Oracle in 2006. Oracle has continued to support open source Berkeley DB.


HBase Architecture

Hbase architecture consists of mainly HMaster, HRegionserver, HRegions and Zookeeper. Zookeeper is a centralized monitoring server which maintains configuration information and provides distributed synchronization. If the client wants to communicate with regions servers, client has to approach Zookeeper.
HMaster
HMaster in Hbase plays vital role in terms of performance and maintaining nodes in the cluster. It provides admin performance and distributes services to different region servers. HMaster assigns regions to region servers.
The HMaster has the features like controlling load balancing and failover to handle the load over nodes present in the cluster. When client wants to change any schema and to change any Meta data operations, HMaster takes responsibility for these operations.
HRegions Servers
It will perform the following functions in communication with HMaster and Zookeeper.
Hosting and managing regions.
Splitting regions automatically.
Handling read and writes requests.
Communicating with clients directly.
HRegions
It contains multiple stores, one for each column family. It consists of mainly two components, which are Memstore and Hfile. The Memstore holds in-memory modifications to the store.




Data Flow
The client communicates in a bi-directional way with both Zoo keeper and HMaster. To read and write operations, it directly contacts with HRegion servers. HMaster assigns regions to region servers and in turn check the health status of region servers. In entire architecture, we have multiple regional servers. Hlog present in region servers will be used to store all the log files.
Hbase Use Cases
In this Hbase use case, we have to take some parameters into consideration like amount of data, speed at data flows and scalability. If the client wants to access a single row details from billions of records Hbase will be used. Hbase permits high compression rates due to few distinct values in the column.
Telecom Industry Use case - Storing billions of mobile call records and providing real time access to the call records and billing information to customers. Traditional storage/database systems couldn't scale to the loads and provide a cost effective solution.
The solution to this use case HBase is used to store billions of rows of call record details. 20TB of data is added monthly. To handle large amount of data in this use case Hbase gives the best solution in telecom industry.






HBase vs RDBMS
HBASE                                                                   RDBMS
Schema-less in database.                                            Having fixed schema in database.
Column oriented database.                                           Row oriented data store.
Designed to store De-normalized data.                               Designed to store Normalized data.
Wide and sparsely populated tables present in Hbase.                Contains thin tables in database.
Supports automatic partitioning.                                    Has no built in support for partitioning.
Well suited for OLAP systems.                                       Well suited for OLTP systems.
Read only relevant data from database.                             To retrieve one row at a time and hence could 
                                                                   read unnecessary data if only some of the 
                                                                   data in a row is required.
Structured and semi structure data can                            Structured data can be stored and processed using an RDBMS
be stored and processed using Hbase.
Enables aggregation over many rows and columns.                     Aggregation is an expensive operation

