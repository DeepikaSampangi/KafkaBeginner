# KafkaBeginner
Apache Kafka Exploration and learning

# start zookeeper
bin/zookeeper-server-start.sh config/zookeeper.properties &

# start a server 1
By configuring log path and broker id 0
bin/zookeeper-server-start.sh config/zookeeper.properties &

# start a server 2
By configuring log path and broker id 1 and change port
bin/zookeeper-server-start.sh config/zookeeper.properties &

# Create a Topic
 bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic first --partitions 2 --replication-factor 2

# For Topic details
bin/kafka-topics.sh --zookeeper localhost:2181 --describe topic first

# Start Producer to push messages
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic first

# Start consumer to pull messages
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic first