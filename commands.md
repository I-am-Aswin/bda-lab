# Big data Analytics Laboratory

Setup docker and docker compose before hand using these commands

## Initial Setup

#### Load Docker Images

> docker load -i hadoop_images.tar


## Cluster Management 

### Command to Start the Hadoop Cluster

> docker-compose up -d

### Command to Stop the Haddop Cluster

> docker-compose down


## Hadoop Commands

### Command to Reach Hadoop Namenode terminal

> docker exec -it namenode bash

### Command to Reach Hive Server Terminal

> docker exec -it hive-server2 bash

### Command to get directly into Hive Beeline Environment

> docker exec -it hive-server2 beeline -u jdbc:hive2://localhost:10000

### Command to work with hdfs

> docker exec -it namenode bash
> hdfs <commands>

### Command to directly get dfs admin report

> docker exec namenode hdfs dfsadmin -report



### Basic Table Creation

> CREATE EXTERNAL TABLE books_data (
  Title STRING,
  description STRING,
  authors STRING,
  image STRING,
  previewLink STRING,
  pubisher STRING,
  publishedDate DATE,
  infoLink STRING,
  categories STRING,
  ratingsCount INT
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE
LOCATION 'hdfs://namenode:9000/user/hive/warehouse/books_data';