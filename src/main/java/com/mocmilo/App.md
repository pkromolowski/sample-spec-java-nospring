## Documentation of `App.java`

**Overview:**

This Java application demonstrates a simple producer-consumer pattern using Apache Kafka. It provides two modes of operation:

* **Producer Mode (`-p`):** Generates a list of `Person` objects and publishes them to a Kafka topic named "ExampleTopic".
* **Consumer Mode (`-c`):** Subscribes to the "ExampleTopic" and consumes the published messages, displaying the person's information.

**Detailed Explanation:**

* **`main(String[] args)`**: This method is the entry point of the application. It checks for command-line arguments to determine the mode of operation.

    * **`if (args.length > 0 && args[0].equals("-p"))`**: If the argument is "-p", it calls the `produceMessage()` method.
    * **`else if (args.length > 0 && args[0].equals("-c"))`**: If the argument is "-c", it calls the `receiveMessages()` method.
    * **`else`**: If no argument is provided or an invalid argument is given, it prints a welcome message and instructions.

* **`receiveMessages()`**: This method sets up a Kafka consumer to subscribe to the "ExampleTopic" and consume messages.

    * **`try (Consumer<String, Person> consumer = new KafkaConsumer<>(KafkaProperties.get()))`**: Creates a Kafka consumer using the properties defined in `KafkaProperties`.

    * **`consumer.subscribe(Arrays.asList("ExampleTopic"))`**: Subscribes the consumer to the specified topic.

    * **`while (true)`**: Continuously polls for messages from the topic.
        * **`ConsumerRecords<String, Person> consumerRecords = consumer.poll(1000)`**: Polls for messages with a timeout of 1000 milliseconds.
        * **`if (consumerRecords.count() == 0)`**: If no messages are received, it increments a counter and checks if it exceeds a predefined threshold (`giveUp`). If it does, the loop breaks.
        * **`consumerRecords.forEach(record -> ...)`**: Iterates through each received record and prints its key, value (person object), partition, and offset.

    * **`consumer.commitAsync()`**: Commits the offsets of the consumed messages to ensure they are not processed again.

* **`produceMessage()`**: This method creates a list of `Person` objects and publishes them to the "ExampleTopic".

    * **`try (Producer<String, Person> producer = new KafkaProducer<>(KafkaProperties.get()))`**: Creates a Kafka producer using the properties defined in `KafkaProperties`.

    * **`List<Person> people = new ContainerBuilder().build().getPeopleList()`**: Constructs a list of `Person` objects using a `ContainerBuilder`.

    * **`int i = 0; for (Person person : people)`**: Iterates through each person object.
        * **`String key = KEY + i++;`**: Generates a unique key for each message.
        * **`ProducerRecord<String, Person> record = new ProducerRecord<>(TOPIC, key, person)`**: Creates a producer record with the topic, key, and person object as value.
        * **`producer.send(record)`**: Sends the record to the Kafka topic.
        * **`System.out.println("record send: " + person.getName())`**: Prints a message indicating the message was sent.

**Dependencies:**

* **Apache Kafka:** Provides the Kafka client libraries for both producer and consumer functionalities.
* **Jackson:** Used for serialization and deserialization of `Person` objects.
* **JUnit:** For testing purposes.



**Pseudo Code:**

```
// Main Program

IF command line argument is "-p" THEN
    PRODUCE_MESSAGES()
ELSE IF command line argument is "-c" THEN
    RECEIVE_MESSAGES()
ELSE
    PRINT WELCOME MESSAGE AND INSTRUCTIONS

// PRODUCE_MESSAGES()

    CREATE LIST OF PERSON OBJECTS
    FOR EACH PERSON OBJECT
        CREATE UNIQUE KEY
        CREATE PRODUCER RECORD WITH TOPIC, KEY, AND PERSON OBJECT
        SEND RECORD TO KAFKA TOPIC
        PRINT MESSAGE INDICATING MESSAGE WAS SENT

// RECEIVE_MESSAGES()

    CREATE KAFKA CONSUMER
    SUBSCRIBE TO KAFKA TOPIC
    WHILE TRUE
        POLL FOR MESSAGES FROM KAFKA TOPIC
        IF MESSAGES RECEIVED
            FOR EACH MESSAGE
                PRINT MESSAGE DATA (KEY, PERSON OBJECT, PARTITION, OFFSET)
        ELSE
            INCREMENT NO RECORDS COUNT
            IF NO RECORDS COUNT EXCEEDS THRESHOLD
                BREAK LOOP
        COMMIT OFFSETS OF CONSUMED MESSAGES



```

**Error Handling:**

The `try-catch` blocks in both `produceMessage()` and `receiveMessages()` handle potential exceptions during Kafka operations. 



