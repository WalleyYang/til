##Apache Hadoop 
Open-source scalable data-processing platform that reliably runs on commodity hardware. Hadoop components work together to provide data, operational, and platform services to the enterprise.

##Hadoop Core
**HDFS:** Self-healing, distributed file system for multi-structured data; breaks files into blocks and stores redundantly across cluster
<br><br>
**MAPREDUCE:** Framework for running large data processing jobs in parallel across many nodes and combining results
<br><br>
**YARN:** New application management framework that enables Hadoop to go beyond MapReduce apps.
<br><br>
**WEBHDFS:** Web service interface for HDFS. Scalable REST API that enables easy and scalable access to HDFS. Move files in and out and delete from HDFS and leverages parallelism of cluster. Perform file and directory functions. webhdfs://<HOST>:<HTTP PORT>/PATH

##Hadoop Data Services - Store, process, and access data
**FLUME:** Store log files and events. Distributed service for efficiently collecting, aggregating, and moving streams of log data into HDFS. Streaming capability with failover and recovery mechanisms. Primary use case: Move web log files directly into Hadoop.
<br><br>
**SQOOP:** Get data from/to SQL databases. Move structured data in and out of Hadoop. Tools and connectors that enable data from traditional SQL databases and data warehouses (ex. Oracle and Teradata) to be stored to and retrieved from Hadoop. SQ-OOP: SQL to Hadoop.
<br><br>
**PIG:** Scripting language for Hadoop. Enables data workers to write complex data transformations using a simple scripting language. Pig latin(the language) defines a set of transformations on a data set such as aggregate, join, and sort among others; can be extended using UDF (User Defined Functions), which can be written in Java and called directly Pig. Pig appeals to developers familiar with scripting languages and SQL. 
<br><br>
**HIVE:** SQL interface for Hadoop. The de-facto SQL-like interface for Hadoop that enables data summarization, ad-hoc query, and analysis of large datasets. Connects to Excel, Microstrategy, PowerPivot, Tableau, and other leading BI tools via Hortonworks Hive ODBC Driver. HiveQL (HQL) is a language that appeals to data analysts familiar with SQL.
<br><br>
**HBASE:** NoSQL DB for interactive apps. Non-relational, columnar database that provides a way for developers to create, read, update, and delete data in Hadoop in a way that performs well for interactive applications. Commonly used for serving “intelligent applications” that predict user behavior, detect shifting usage patterns, or recommend ways for users to engage.
<br><br>
**HCATALOG:** Metadata and table management. Metadata service that enables users to access Hadoop data as a set of tables without needing to be concerned with where or how their data is stored. Enables consistent data sharing and interoperability across data processing tools such as Pig, MapReduce, and Hive. Enables deep interoperability and data access with systems such as Teradata, SQL Server, etc.

##Hadoop Operational Services - Productive operations and management
**AMBARI:** Management and monitoring. Make Hadoop clusters easy to operate. Simplified cluster provisioning with a step-by-step install wizard. Pre-configured operational metrics for insight into health of Hadoop services. Visualization of job and task execution for visibility into performance issues. Complete RESTful API for integrating with existing operational tools. Intuitive user interface that makes controlling a cluster easy and productive.
<br><br>
**OOZIE:** Workflow and scheduling. Workflow system that coordinates jobs written in multiple languages such as MapReduce, Pig, and Hive. Allows specification of order and dependencies between jobs so processing can happen in an orderly manner.

##Hadoop Platform Services - Makes Hadoop ready for the enterprise
