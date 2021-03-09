#### start zookeeper
zookeeper-server-start /usr/local/etc/kafka/zookeeper.properties

#### start kafka server
kafka-server-start /usr/local/etc/kafka/server.properties

#### create topic with name "test" and 1 partition
kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test

#### initialize the Kafka producer console, which will listen to localhost at port 9092 at topic test
kafka-console-producer --broker-list localhost:9092 --topic test

#### initialize the Kafka consumer console, which will listen to bootstrap server localhost at port 9092 at topic test from beginning
kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning


#### list all topics
kafka-topics --list --zookeeper localhost:2181   

#### delete a topic
kafka-topics --delete --zookeeper localhost:2181 --topic test