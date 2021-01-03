# Tracking User Activity at EdTech Co

## Problem Statement

### Situation

EdTech Co has a service that delivers assessments from customers like Pearson to end-users. EdTech Co wants to share back with its customers data about the users activity in its platform. This may be valuable data to its clients, potentially informing several business decisions.

### Complication

Data is currently stored in a nested JSON file with many levels. EdTech Co needs to unwrap it carefully to understand what's there and what from there may be valuable to share back with its clients. Moreover it needs to prepare the proper infrastructure to land the data in a format and structure that it will be easier for clients to handle and query the data.

### Objetive

Prepare the infrastructure to land the data in the form and structure it needs to be to be queried.
This will require:

- Publish and consume messages with Kafka
- Use Spark to transform the messages 
- Land the data into HDFS

## Dataset

The data is available at https://goo.gl/ME6hjp. It contains 3,280 assessments stored in a JSON file with many layers. Not all of the fields will be of interest of our clients to receive. Part of project's objective is to figure out which of the fileds are of most interest, or what type of queries our clients may want to answer with this data. 

## Tools

- This project will be done entirely on Google Cloud Platform (GCP).
- This project will make use of the following tools:
    * Docker-compose (to set-up the cluster of containers)
    * Kafka (to publish and consume messages)
    * Zookeeper (broker)
    * Spark/pyspark (to transform the messages)
    * Cloudera/HDFS (to store final data)
    * Jupyter Notebook using Python 3 Kernel (to track pipeline set-up steps and report results)
    * Linux Bash (to run commands through CLI)
    * Python 3 json package (to unwrap JSON file)
    
## Repo structure

- The project repo contains the following files (all under the code folder):
    * docker-compose.yml (docker-compose file used to spin up the cluster used in the project)
    * project-2-notebook_1.ipynb (jupyter notebook describing the step-by-step procedures used to set-up the pipeline, publish messages in kafta, and launch spark)
    * project-2-notebook_2.ipynb (jupyter notebook describing the step-by-step procedures to consume messages in spark, run the transformations and load the data into HDFS)
    * jupyter@w205-01-history.txt (bash history file)
    
## Full Report - Table of Contents

- [1. JSON file data structure](./code/project-2-notebook_1.ipynb#json_file_data_structure)
- [2. Publish and consume messages with Kafka](./code/project-2-notebook_1.ipynb#publish_and_consume_messages_with_kafka)
- [3. Launch Spark](./code/project-2-notebook_1.ipynb#launch_spark)
- [4. Use Spark to transform the messages](./code/project-2-notebook_2.ipynb#use_spark_to_transform_the_messages)
- [5. Query the data using Spark SQL](./code/project-2-notebook_2.ipynb#query_the_data_using_spark_sql)
- [6. Land transformed data into HDFS](./code/project-2-notebook_2.ipynb#land_transformed_data_into_HDFS)