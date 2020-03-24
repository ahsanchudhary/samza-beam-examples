Steps followed:
===============
$ git clone https://github.com/apache/samza-beam-examples.git
$ cd samza-beam-examples
$ scripts/grid bootstrap
$ scripts/grid standalone
$ ./deploy/kafka/bin/kafka-topics.sh  --zookeeper localhost:2181 --create --topic input-text --partitions 10 --replication-factor 1
$ ./deploy/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic word-count --property print.key=true
$ ./deploy/kafka/bin/kafka-console-producer.sh --topic input-text --broker-list localhost:9092
Add --runner=SamzaRunner to the program arguments in intellij run configuration and then run the application
Go to the kafka-producer window and type a sentence/paragraph and the results should show up in the consumer window.
