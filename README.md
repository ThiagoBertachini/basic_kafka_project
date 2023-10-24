# basic_kafka_project to produce and consume topics with java

- InstalL JDK
- Instal Apache Kafka
  - At kafka repository, you may create a new repository for logs saving:
    - Create /data and inside create /kafka and /zookeeper.
    - At kafka/config edit server.properties and zookeeper.properties:
      - server.properties: Change log.dirs="", to your new repository /data/kafka.
      - zookeeper.properties: Change dataDir="", to your new repository /data/zookeeper.


- Starting servers
  - Execute first zookeeper-server-start.bat \path_to\zookeeper.properties.
  - Then Execute  kafka-server-start.bat \path_to\server.properties.


- Topics Configuration (CLI)
  - To create a topic, use 'kafka-topics --bootstrap-server localhost:9092 --create --topic topicName' --partitions partitionsNumer.
  - To log your topics list, use 'kafka-topics --bootstrap-server localhost:9092 --list'.
  - To produce for topics, use 'kafka-console-producer --broker-list localhost:9092 --topic topicName'.
  - To consume from topics, use 'kafka-console-consumer --bootstrap-server localhost:9092 --topic topicName' --group groupName --from-beginning. 
(If there is a topic with 4 partitions, and  5 consumers, 1 consumer will be waiting a new partition).
  - To produce for topics with key and value, use 'kafka-console-producer --broker-list localhost:9092 --topic topicName --property "parse.key=true" --property "key.separater=,"'.
  - To consume for topics with key and value, use 'kafka-console-consumer --bootstrap-server localhost:9092 --topic topicName --property "print.key=true" --property "key.separater=," --group groupName'.


- Conduktor
  - Conduktor is a graphical interface tool for create and consume topics

- Replication Factor
  - It is recommended to create more than one instance for brokers in case of a broker failure
  - 