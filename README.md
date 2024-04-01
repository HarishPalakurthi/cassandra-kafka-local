# Kafka with PySpark Data Transfer from Cassandra to Local File System

## Overview

This demonstration showcases the integration of Kafka, PySpark, and Cassandra within a Docker environment. The objective is to transfer data from a Cassandra database to the local file system using Kafka as an intermediate messaging system.

## Components

1. **Kafka**: Apache Kafka is used as the messaging system for data transfer between components. It provides scalable and fault-tolerant messaging capabilities.

2. **PySpark**: PySpark is the Python API for Apache Spark, a distributed processing framework. PySpark is used to consume data from Kafka, process it, and save it to the local file system.

3. **Cassandra Database**: Cassandra is a NoSQL database known for its scalability and high availability. In this demonstration, we'll be fetching data from Cassandra to transfer it via Kafka.
   
4. **ZooKeeper**: ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and group services. It is used for coordination and management of Kafka brokers within the Kafka cluster.

5. **Docker**: Docker is used to create a containerized environment for hosting all the components. Docker Compose is utilized for managing the Docker containers.

## Setup Instructions

1. Clone the repository, it contains the producer and consumer codes and Docker compose file.
2. Docker compose up (check for containers as per docker-compose file)
3. Configure cassandra database
4. Run CQL code
5. Spark submit the producer and consumer as below:
Launch producer script
```
spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.0.1,com.datastax.spark:spark-cassandra-connector_2.12:3.0.0  producer.py 
```

Launch consumer script
```
spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.0.1 consumer.py 
```
