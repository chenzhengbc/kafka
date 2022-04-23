#Kafka Admin Client
adminClient.createTopics() is an async process when it comes to topic creation
To make it synchronized, assign the result to CreateTopicsResult, then call .all().get() method

#Kafka Producer
- Need bootstrap server
- need key serializer
- need value serializer 

#Kafka Consumer
- Need bootstrap server
- Key deserializer
- Value deserializer 
- Consumer Group
  - When working with consumer, it always comes in a group
  - need to first subscribe the topic(s)
    - consumer.subscribe(Pattern.compile("^topic.*"));
    - call consumer.poll(Duration.ofSeconds(1)) to get ConsumerRecords
    - if !consumerRecords.isEmpty(), then we can have record metadata
      - consumerRecord.topic()
      - consumerRecord.partition()
      - consumerRecord.offset()
      - consumerRecord.key()
      - consumerRecord.value()
      - consumerRecord.timestamp()
