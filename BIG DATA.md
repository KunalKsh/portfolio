#                          BIG DATA



Big Data - Volume + Velocity + Variety

* Structured Data - Rows \& Columns - RDMS
* Semi-Structured Data - JSON (Document Database)
* Unstructured

Schema- Design/Rules of the data

API - APPLICATION PROGRAM INTERFACES - SEND REQUEST GIVES RESPONSE - USES JSON OR XML

XML - EXTENSIBLE MARKUP LANGUAGE - WAY OF STORING DATA

HTML - HYPERTEXT MARKUP LANGUAGE - CODING LANGUAGE



PRIMARY KEY - Unique Identification Number

COMPOSITE KEY, CANDIDATE KEY, FOREIGN KEY - RELATIONSHIP



ERD DIAGRAM - ENTITY-RELATIONSHIP DIAGRAM

Cardinality - One to One, One to Many, Many to One, Many to Many



REFERENTIAL INTEGRITY - Ensure relationships between tables



METADATA - Data about Data, Characteristics of Data



Normalization - Data to minimize redundant Data elements



**OLTP** - Online Transaction Processing - Processing focused on managing transaction-oriented applications.

ACID - ATOMICITY, CONSISTENCY, ISOLATION, DURABILITY



NOSQL - Not Only SQL

HADOOP - Storing \& Processing massive Data across distributed clusters of computers.



Dimensions of Big Data - Volume, Velocity, Variety, Veracity, Variability, Value, Visualization



Web Usage Mining, Web Structure Mining, Web Content Mining



Social Media- Sentiment Analysis, Social Network Analysis



Streaming Analytics-  Input \& Output has small window



1. Monitoring 2. Control 3. Optimization 4. Autonomy



Descriptive Analytics- What happened

Diagnostic Analytics- Why it happened

Predictive Analytics- What will happen

Prescriptive Analytics - What should happen



NOSQL Characteristics -

1. Schema Flexibility
2. Horizontal Scalability
3. High Performance
4. Distributed Architecture
5. Relaxed Consistency - BASE Model - Basically Available + Soft State + Eventual Consistency



CAP Theorem - Consistency + Availability + Partition Tolerance

* Consistency - Most recent write
* Availability - Each request receives a response
* Partition Tolerance - System works despite network partitions

When a partition occurs, choose between Consistency \& Availability



* CP System
* AP System
* CA System

CAP is for failure scenarios, not speed or performance



Key-Value Stores- Partitioning, Replication, In-memory+ Disk Hybrid Storage, Eventual Consistency

* Schema-Less
* Fast
* Scalable
* Distributed



Document Databases - JSON, BSON or XML

* Flexible Schema
* Collections \& Documents
* Embedded/Nested Data
* Horizontal Scaling
* Denormalization Common



MongoDB - Document-Oriented Database, JSON like documents(BSON)

* Data Model
* Schema
* Querying
* Scaling





Column-Family Stores(Wide Column) - Apache Cassandra + Apache HBase + Google Bigtable

Rows - Row keys - Millions of Columns

Column Families

Horizontal Scaling, Eventual or Tunable Consistency, Vectorized Processing



Data Sources-Kafka/Flume-Column Family Store-Analytics/ML



Data Lakes \& File-Based Columnar Formats- Apache Parquet, Apache ORC; Used in - Hadoop + Spark analytics + S3,GCS, Azure Blob



Graph Database - Store, Manage, Query Relationship

* Nodes - Entities
* Edges(Relationship)- Connections between nodes
* Properties - Key-value data stored on nodes \& edges

"Neo4j, Amazon Neptune, ArangoDB"



Resource Description Framework Graph (RDF) - Subject,Predicate,Object - SPARQL

Graph Database supports - Centrality, Community Detection, Similarity \& recommendations, Pathfindings

Graph Neural Network(GNN)



* Netflix- Cassandra for streaming data
* Amazon- DynamoDB for massive-scale services
* Facebook- HBASE for messaging
* Twitter/X- Redis for caching



CASSANDRA - Columnar Database  -OLAP- ONLINE ANALYTICAL PROCESSING - Multidimensional Data Model

Data Cube - Multi-dimensional array of values

Dimension- Descriptive attributes or qualitative data, Measures - Quantitative data, Grain - Single record of data

Fact Table- Contains all the measures

Aggregation - Process of summarizing data

Star Schema - Fact Table- Dimension- Sub-Dimensional Table

Snowflake Schema - Normalized Dimension Tables



OLAP Operation

1. Roll-Up(Aggregation)
2. Drill-Down
3. Slice
4. Dice
5. Pivot(Rotate)



**Hadoop -** Open-source framework- Distributed storage, Distributed processing

1. HDFS - Hadoop Distributed File System - Storage
2. YARN - Yet Another Resource Negotiator - Resource Management
3. MapReduce - Processing
4. Hadoop Common - Utilities \& Libraries



Data Storage - HDFS, HBASE

Data Processing - Map Reduce, YARN

Data Access - Hive, Pig, Mahout, Avro, Sqoop

Data Management - Oozie, Chukwa, Flume, ZooKeeper



Client->Cluster-Master Nodes-NameNode-ResourceManager-> Rack A-Worker Node-DataNode-NodeManager-Container



**HDFS** - Stores large files across multiple machines -> NameNode- MetaData Manager -> DataNode - Stores actual Data Blocks

Scalibility, Fault Tolerance, High Throughput, Write Once Read Many



Batch Processing - Processing large volume of data - Optimised throughput - Apache MapReduce, Apache Spark



Master-Slave Architecture - Master:NameNode, Slave: DataNodes

NameNode - Manages file system Metadata - File names, Block Location, Permissions

Data Node - Stores actual data blocks, Serve read/write requests

Secondary -  Edit logs,, FSImage - Helps NameNode



FSImage (File System Image) - Snapshot of the entire HDFS filesystem metadata at a point in time - Creates Recovery Point-Restores

EditLogs (Edit Log Files) - Every operations is noted \& stored

Standby NameNode - Secondary NameNode- Backup option - Copy of NameNode

JournalNodes - Information stored about MetaData - Required for High Availability - Works on quorum-based system



Block - Files divided into blocks- 128 MB



Racks - Logical Grouping of DataNodes that are physically located in the same rack of machines in a data center

HDFS - Rack-aware, DataNodes belong to which rack \& uses this informatiion when placing data.

1st Replica - Local DataNode

2nd Replica - Different rack

3rd Replica - Same rack as 2nd but different DataNode

Survives rack failure, Minimize cross-rack traffic



MapReduce - For data that are large for a single machine, High failure probability

Latency is high because of Batch Processing-Processing Time

Spark does real time data analysis so the latency is low.



Sequential Flow->Input splitting-Map Phase-Shuffling \& Sorting-Reduce-Output

Mapper-Reducer-Driver-InputFormat/OutputFormat

JobTracker,TaskTracker was used before YARN(Hadoop 1.0)



**YARN** - Deciding where Mapping \& Reducing will happen - YET ANOTHER RESOURCE NEGOTITATOR

Resource Manager - Allocates Containers

Node Manager - Manages Containers

ApplicationMaster - Negotiates Resource, Monitors Exceution



* Resource management from processing
* Support multiple framework



YARN is the operating system of HADOOP.

1. Resource Manager(Master) - Talks to Node Manager - One active Resource Manager per cluster
2. Node Manager(Slave) - Manages resource on a single node, launches \& reports container, Runs on every worker node
3. ApplicationMaster(Per Application) - End to End Task management
4. Container(Resource Unit) - Bundle of CPU \& Memory



YARN does not know what runs inside a container(MapReduce,Spark)



STEP 1 - DATA STORED N HDFS

STEP 2 - JOB SUBMITTED

STEP 3 - APPLICATIONMASTER REQUESTS RESOURCE



HADOOP COMMON - Group of Shared Utilities \& Libraries

1. Configuration Management
2. Filesystem API
3. Remote Procedure Call (RPC)
4. Serialization Framework
5. Native Libraries
6. Security Services
7. Hadoop Common CLI Tools- hadoop fs, hadoop version, hadoop classpath

Sim

Tool using Hadoop Common -

1. HIVE - SQL Queries
2. Pig - Data Scripting
3. HBase - NoSQL DB
4. Sqoop - RDMS Transfer
5. Flume - Log Ingestion
6. Spark - Fast Processing



**Apache HIVE** - Data warehousing tool built on Hadoop - Converts SQL queries into MapReduce/Spark jobs; HiveQL(Language)

1. Command Like Interface, Beeline, Web UI; Driver - Manager query -> Compiler - Pases HiveQL

Partitioning (Reduce data scanned), Bucketing (Joins \& Sampling), ORC/Parquet (Columnar Storage), Indexing (Selective queries), CBO (Best execution)

&#x20;

**HIVE METASTORE -** Stores Metadata - Databases, Tables, Columns, Partitions, HDFS Location



**Hadoop Spark -** Apache spark open-source distributed computing engine

Spark is faster than MapReduce.

Driver Program - Runs - Creates - Builds - Coordinates

Cluster Manager - Standalone, YARN, Mesos, Kubernetes

Executors

Spark Execution Flow - Job - DAG - Job-Stages-Task - Executors - Result

* RDD(Resilient Distributed Dataset) - Distributed collection of data
* DataFrame - Similar to RDBMS
* Dataset - Type safety of RDDs
* Lazy Evaluation
* DAG(Directed Acyclic Graph) - Logical execution plan
* Spark SQL
* Spark Streaming
* Spark MLib - Machine Learning Library
* Spark GraphX



**Spark** - It is a unified big data engine, DAG - based execution, Faster than MapReduce

**Apache HBase -**  Column-oriented database - Inspired by Google BigTable

**Apache Pig -** High-level data flow platform - Simplify MapReduce Programming

**Apache Sqoop -** Transfer data between RDBMS \& Hadoop

**Apache Flume -** Continuous streaming log data - Data ingestion tool



**Hadoop Ecosystem**

* Data Management -  Data Access - Data Processing - Data Storage

Data Management - Workflow Monitoring - Management

Data Access - SQL, Dataflow, Machine Learning, RDBMS Connector

Data Processing - Cluster Management, Cluster \& Resource Management

Data Storage - File System, Column DB storage



**Social Media Analysis-**

* Sentiment Analysis - Entity, Sentence, Document level, Lexicon-Based, Machine Learning

Cleaning - Removing stop words, Tokenization, Stemming, Lemmatization

* Social Network Analysis - Network structure, connections, nodes, network density, network centrality, network flows



Centrality in Social Network -

1. Degree Centrality  - No. of people you are directly connected to.
2. Closeness Centrality -  How fast can this person can reach directly
3. Harmonic Centrality
4. Betweenness Centrality - How many times on an average it comes between two nodes
5. Degree Centrality - How many people can this person reach directly



**Degree Centrality -**

1. Social Network
2. Epidemiology
3. Marketing



**Betweenness Centrality (Bridges \& Bottleneck)-**

1\. Transportation Networks

2\. Cybersecurity

3\. Organizational Analysis



**Closeness Centrality**

1. Emergency Response Planning
2. Urban Planning
3. Internet \& Web Networks



**MACHINE LEARNING VS. DEEP LEARNING-**

Machine Learning -> Input - Feature Extraction - Classification - Output

Deep Learning -> Feature Extraction + Classification - Output



Deep Learning - Can learn from both Supervised \& Unsupervised manner; Outperforms ML techniques; Black Box



**Explainable AI - Explainability - What, Why, When, How?**

In Neural Network we don't select the features so it's a Black Box what feature has been used

Handwritten digit recognition (MNIST dataset)

Neural Network - Input layer(Pixels)

