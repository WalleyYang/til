#### Get Kafka Running
```
# Start Zookeeper
$ bin/zookeeper-server-start.sh config/zookeeper.properties

# Start Kafka Server
$ bin/kafka-server-start.sh config/server.properties
```

#### Topics
```
# Create a Topic
$ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test

# List topics
$ bin/kafka-topics.sh --list --zookeeper localhost:2181
```

#### Sending and Receiving messages
```
# Use in producer and consumer on separate terminals

# Run producer
$ bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test

# Run consumer
$ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```

#### Setup Multi-broker Cluster
```
# Copy the server.properties and rename it
# Example using two new config files
$ cp config/server.properties config/server1.properties
$ cp config/server.properties config/server2.properties

# Update the below for the new files

# server1.properties
broker.id=1
listeners=PLAINTEXT://:9093
log.dirs=/tmp/kafka-logs-1

# server1.properties
broker.id=2
listeners=PLAINTEXT://:9094
log.dirs=/tmp/kafka-logs-2
```

#### Import/Export Data
```
# Create test file in kafka directory
$ echo -e "hello\nworld" > test.txt

# Setup standalone connector
$ bin/connect-standalone.sh config/connect-standalone.properties config/connect-file-source.properties config/connect-file-sink.properties

# Verify content is in sink file
$ cat test.sink.txt

# Verify content in consumer
$ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic connect-test --from-beginning
```
