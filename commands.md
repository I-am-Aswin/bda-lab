# Big data Analytics Laboratory

Setup docker and docker compose before hand using these commands

## Initial Setup


### Folder Creation

> mkdir hadoop_datanode1 hadoop_datanode2 hadoop_datanode3 hadoop_metastore hadoop_namenode hadoop_postgres

#### Load Docker Images

> docker load -i hadoop_images.tar


## Cluster Management 

### Start the Hadoop Cluster

> docker-compose up -d

### Stop the Haddop Cluster

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
