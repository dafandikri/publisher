# Software Architectures Tutorial Reflection

This document reflects on Software Architectures

## Refelction 1

### a. How much data your publisher program will send to the message broker in one run?

In one run, the publisher sends 5 messages to the message broker. Each message is a serialized UserCreatedEventMessage struct, which contains a user_id and a user_name, both as strings. The total data sent is the sum of the serialized sizes of these 5 messages. The exact size depends on the string lengths and serialization overhead, but it is relatively small (a few hundred bytes in total).

### b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

This means both the publisher and subscriber are connecting to the same AMQP message broker instance, using the same credentials (username: guest, password: guest) and the same host (localhost) and port (5672). This allows them to communicate through the same broker, enabling message delivery from publisher to subscriber.

## Image of RabbitMQ running

![RabbitMQ running](/Screenshot%202025-05-16%20at%2018.38.01.png)

## Image of Processing Event

![RabbitMQ running](/Screenshot%202025-05-16%20at%2018.38.01.png)
