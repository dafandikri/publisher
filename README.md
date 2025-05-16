# Software Architectures Tutorial Reflection

This document reflects on Software Architectures

## Reflection 1

### a. How much data your publisher program will send to the message broker in one run?

In one run, the publisher sends 5 messages to the message broker. Each message is a serialized `UserCreatedEventMessage` struct, which contains a `user_id` and a `user_name`, both as strings. The total data sent is the sum of the serialized sizes of these 5 messages. The exact size depends on the string lengths and serialization overhead, but it is relatively small (a few hundred bytes in total).

### b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

This means both the publisher and subscriber are connecting to the same AMQP message broker instance, using the same credentials (username: guest, password: guest) and the same host (localhost) and port (5672). This allows them to communicate through the same broker, enabling message delivery from publisher to subscriber.

## Screenshot: RabbitMQ Running

Below is a screenshot showing RabbitMQ running on the local machine. This confirms that the message broker is active and ready to process messages from the publisher.

![RabbitMQ running](/rabbitmq_run.png)

## Screenshot: Processing Event Console

This screenshot shows the console output while the publisher is running. It displays the process of sending messages to the broker and confirms that the events are being published successfully.

![Processing event console](/console_processing.png)

## Monitoring Chart on RabbitMQ Based on Publisher

The following image is a screenshot of the RabbitMQ management UI in the browser. It shows a spike in the message rate chart, which corresponds to the moment when the publisher sends multiple messages in a short period. This spike indicates increased activity as the publisher pushes events.

![Monitoring chart](/monitoring_chart_rabbitmq.png)

The spike in the monitoring chart directly relates to running the publisher. When the publisher sends its batch of messages, RabbitMQ receives them almost simultaneously, causing a visible increase (spike) in the message rate. This helps visualize the flow of messages and confirms that the publisher is working as expected.
