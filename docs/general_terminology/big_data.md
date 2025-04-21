# Big Data

To understand some concepts behind Big Data, there are some terminologies that should be properly defined. Below are some of the most common terms that should come in handy.

## Big Data

- A large collection of data characterized by the three V’s: volume, velocity, and variety.

    - Volume refers to the amount of data—big data deals with high volumes of data

    - Velocity refers to the rate at which data is collected—big data is collected at a high velocity and often streams directly into memory

    - Variety refers to the range of data formats—big data tends to have a high variety of structured, semi-structured, and unstructured data, as well as a variety of formats such as numbers, text strings, images, and audio.

## As-a-service Infrastructure

- Some examples: Data-as-a-service, software-as-a-service, platform-as-a-service

- All of them refer to the idea that rather than selling data, licences to use data, or platforms for running Big Data technology, it can be provided "as a service", rather than as a product.

## Data Lake

- A storage repository that holds a vast amount of raw data in its native format until it's required.

- Every data element within a data lake is assigned a unique identifier and set of extended metadata tags. When a business question arises, users can access the data lake to retrieve any relevant, supporting data. 

## Data Mining

- Process of discovering insights from data.

-  In terms of Big Data, because it is so large, this is generally done by computational methods in an automated way using methods such as decision trees, clustering analysis and, most recently, machine learning.

## Apache

- The name of a prominent open-source web server and also a non-profit organization that supports many open-source projects, including the web server.

### Apache Hadoop

- A Java-based framework for Big Data computing which has been released into the public domain as a open source software, and so can freely be used by anyone.

- It is mainly used for distributed storage and processing of large datasets and analytics jobs, breaking workloads down into smaller workloads that can be run at the same.

For more information, refer to: [Google Cloud - What is Apache Hadoop?](https://cloud.google.com/learn/what-is-hadoop).

### Apache Spark

- A unified analytics engine for large-scale data processing, offering built-in modules for SQL, streaming, machine learning, and graph processing, and can run on various platforms and against diverse data sources.

- More recently developed and more suited to handling cutting-edge Big Data tasks involving real time analytics and machine learning.

- Does not include its own file system, but is designed to work with Hadoop's HDFS or a number of other options. 

- However, for certain data related processes it is able to calculate at over 100 times the speed of Hadoop, thanks to its in-memory processing capability.

For more information, refer to [Amazon Web Services - Whta is Apache Spark?](https://aws.amazon.com/what-is/apache-spark/).

### Apache Hadoop vs. Apache Spark

| Feature                         | Apache Spark                                | Apache Hadoop (MapReduce)                  |
|---------------------------------|----------------------------------------------|--------------------------------------------|
| **Processing Model**           | In-memory processing                         | Disk-based batch processing                |
| **Speed**                      | Faster due to in-memory computation          | Slower due to frequent disk I/O            |
| **Ease of Use**                | Easier with APIs in Python, Scala, Java      | More complex, primarily Java-based         |
| **Data Processing Type**       | Supports batch, streaming, and ML workloads  | Primarily batch processing                 |
| **Fault Tolerance**            | RDD lineage and DAG recovery                 | Data replication via HDFS                  |
| **Resource Management**        | Integrates with YARN, Mesos, or Kubernetes   | Uses YARN for resource management          |
| **Machine Learning Support**   | Built-in MLlib library                       | No native ML support, relies on tools like Mahout |
| **Streaming Support**          | Yes, via Spark Streaming or Structured Streaming | Not inherently designed for streaming     |
| **Data Caching**               | Yes, supports in-memory data caching         | No, data read/written from disk each time  |
| **Use Cases**                  | Real-time analytics, ML pipelines, ETL       | Long-running batch jobs, ETL               |

For more information, refer to [Spark vs. Hadoop](https://www.openlogic.com/blog/spark-vs-hadoop).

## MapReduce

- A computing procedure for working with large datasets, which was devised due to difficulty of reading and analysing really Big Data using conventional computing methodologies.

- As its name suggests, it consists of two procedures – mapping (sorting information into the format needed for analysis – i.e. sorting a list of people according to their age) and reducing (performing an operation, such checking the age of everyone in the dataset to see who is over 21).

## NoSQL

- A database format designed to hold more than data which is simply arranged into tables, rows, and columns, as is the case in a conventional relational database.

- This database format has proven very popular in Big Data applications because Big Data is often messy, unstructured and does not easily fit into traditional database frameworks.

<div style="display: flex; justify-content: space-between;" markdown="1">

[:material-arrow-left: Programming Languages](./languages.md){ .md-button }

[Data Engineering :material-arrow-right:](./data_engineering.md){ .md-button }

</div>