POC Kafka message chunking and assembly

This project demonstrates handling of BIG files in Kafka.

Kafka's default message size is 1 MB. This is suitable for most of the use cases but it might not be suitable for all the cases.

For handling big messages one option can be to increase topic's message size but it comes with it's own set of challenges.

There are two approaches to solve it : 
1) Chunk big messages into smaller chunks and then assemble at the consumer side
2) Store chunks in the data store and then refer it in message in topic which consumers can consume and then readback from the store directly. 

In this project, we try to solve it in first approach.

We have a producer app (web application) which will chunk the messages and then publish to the topic. The consumer will then read all the messages and then assemble the final message and show.

![image](https://user-images.githubusercontent.com/103200610/223117290-388c29e9-16c2-4441-a19f-baa67308bd0f.png)
