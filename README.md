### NOTE
Please read with attention, in case of any doubt don't hesitate to contact us.

# kafka-challenge
This repository aims to present a challenge that will need to be implemented.  


# SCENARIO
Your company is developing a new application that integrates with multiple external systems. The application needs to consume messages from an Apache Kafka topic, process them, and then send them to another Kafka topic. The application must be built using Quarkus and Apache Camel.

# Requirements
The application should consume messages from an Apache Kafka topic named "mySourceTopic".
The application should process the messages by converting them from JSON to a Java object and then transforming the object into a different format (for example, converting fields or adding additional data).
The transformed messages should be sent to another Kafka topic named "myDestinationTopic".
The application should use Quarkus and Apache Camel to implement the message consuming, processing, and sending logic.
The application should be designed in a way that allows for easy scalability and maintenance.

# Test Instructions
Create a new Quarkus project using the Maven archetype "quarkus-kafka".
Add the necessary dependencies for Apache Camel and Kafka integration.
Implement the Camel routes to consume messages from Kafka, process them, and send them to another Kafka topic.
Write unit tests to verify the message processing and sending logic.
Document your code and provide a README file with instructions on how to build and run the application.

# Environments Instructions
Download Kafka from the Apache Kafka website: https://kafka.apache.org/downloads

Extract the Kafka package to a directory on your computer.

Open a terminal window and navigate to the directory where you extracted Kafka.

Start ZooKeeper by running the following command:
```console
bash
Copy code
bin/zookeeper-server-start.sh config/zookeeper.properties
Open a new terminal window and navigate to the Kafka directory.
Start the Kafka server by running the following command:

bash
Copy code
bin/kafka-server-start.sh config/server.properties
Create the input and output Kafka topics by running the following commands:

bash
Copy code
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic mySourceTopic
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic myDestinationTopic
Verify that the Kafka topics were created by running the following command:

css
Copy code
bin/kafka-topics.sh --list --bootstrap-server localhost:9092
Update the application.properties file in your Quarkus project to include the following configuration:

makefile
Copy code
kafka.bootstrap.servers=localhost:9092
Run your Quarkus project using the following command:

bash
Copy code
./mvnw quarkus:dev
```
