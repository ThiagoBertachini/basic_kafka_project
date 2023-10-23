# basic_kafka_project to produce and consume topics with java

- InstalL JDK
- Instal Apache Kafka
  - At kafka repository, you may create a new repository for logs saving:
    - Create /data and inside create /kafka and /zookeeper
    - At kafka/config edit server.properties and zookeeper.properties:
      - server.properties: Change log.dirs="", to your new repository /data/kafka
      - zookeeper.properties: Change dataDir="", to your new repository /data/zookeeper

- Starting servers
  - Execute first zookeeper-server-start.bat \path_to\zookeeper.properties
  - Then Execute  kafka-server-start.bat \path_to\server.properties