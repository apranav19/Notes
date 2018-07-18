Kafka Commands
---------------------

`docker run --rm -it -p 2181:2181 -p 3030:3030 -p 8081:8081 -p 8082:8082 -p 8083:8083 -p 9092:9092 -e ADV_HOST=127.0.0.1 landoop/fast-data-dev`

Login to Kafka Box
-------------------
```
docker run --rm -it --net=host landoop/fast-data-dev bash
```

Create a topic
---------------
`kafka-topics --zookeeper 127.0.0.1:2181 --create --topic first_topic --partitions 3 --replication-factor 1`

List a topic
------------
`kafka-topics --zookeeper 127.0.0.1:2181 -list`

Produce data to topic
---------------------
```
kafka-console-producer --broker-list 127.0.0.1:9092 --topic first_topic
```

Consuming data from a topic using console
------------------------------------------

This will print out data to the console as it's fed by the producer

```
kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic first_topic
```