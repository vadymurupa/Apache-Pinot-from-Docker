# Apache Pinot
 
original source:

https://www.youtube.com/watch?v=cNnwMF0pOJ8&list=PLihIrF0tCXdeimVCZwuejXb7FkjsyN9_k&index=8

https://github.com/npawar/pinot-tutorial

This repository is created to build and gether all services in one docker-compose file.

Apache Pinot is a real-time OLAP data store that can provide ultra low latency even at high throughput. It can ingest data from batch data sources such as Hadoop, S3, Azure and Google cloud storage or from streaming data sources such as Kafka, EventHub, Kinesis.

## How to setup a Pinot cluster
In the tutorial, we will setup a Pinot cluster with the following components
* 1 zookeeper
* 3 controllers
* 2 brokers
* 2 servers
Once the cluster is up and running, we see how to load data into Pinot and query it.
At the end, we show how Pinot is resilient to failures


sudo docker-compose exec pinot-controller-1 bin/pinot-admin.sh AddTable -tableConfigFile /rawData/transcript-table-offline.json -schemaFile /rawData/transcript-schema.json -controllerHost pinot-controller-1 -controllerPort 9001 -exec


Here -controllerHost pinot-controller-1 indicates that the command should access the pinot-controller-1 service, which is one of the services defined in your docker-compose.yml file.

This command will start the process of adding the table and schema to Pinot using the files located in the mounted /rawData folder inside the container.






