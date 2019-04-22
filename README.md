# Analsys Data from Twitter using KSQL

In this demo, tweets are going to be analyzed using Confluent Platform, specially KSQL to create streams and aggregations ( based on rmoff's KSQL example https://www.confluent.io/blog/using-ksql-to-analyse-query-and-transform-data-in-kafka )

# Instructions:

1. Download and Install Confluent Platform 
https://www.confluent.io/download/

2. Once Confluent platform is up and running, clone the Twitter connector from git repo or Confluence Hub, then 
  Edit ```etc/schema-registry/connect-avro-distributed.properties```, adding to it:
  ```plugin.path=share/java,/PATH/kafka-connect-twitter/``` Restart Confluent
  
3. Create properties file with the proper twitter app credentials.

4. Load the connector
```confluent load twitter-source -d twitter-source.json```

5. Check the kafka consumer

```kafka-console-consumer --bootstrap-server localhost:9092 --from-beginning --topic twitter-source | jq```
  
