- A bottom up approach to picking a broker!
- A top down approach would start with the features/ functionality and then figure out the tool.
- The naming and comparison are slightly messy currently, but the table tries to provide an overview
- **Terms**
    - [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) - flow controlled, message-oriented communication with message-delivery guarantees such as __at-most-once__ (where each message is delivered once or never), __at-least-once__ (where each message is certain to be delivered, but may do so multiple times) and __exactly-once__ (where the message will always certainly arrive and do so only once), and authentication and/or encryption based on [SASL](https://en.wikipedia.org/wiki/Simple_Authentication_and_Security_Layer) and/or [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security). It assumes an underlying reliable transport layer protocol such as [Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) (TCP).
    - [Stream Processing](https://en.wikipedia.org/wiki/Stream_processing) - Given a sequence of data (a __stream__), a series of __operations__ is applied to each element in the stream. __Operations__ are usually pipelined, and optimal local on-chip memory reuse is attempted, in order to minimize the loss in bandwidth, associated with external memory interaction. __Uniform streaming__, where one operation is applied to all elements in the stream, is typical. 
    - [Message Queue](https://en.wikipedia.org/wiki/Message_queue) - Message queues implement an asynchronous communication pattern between two or more processes/threads whereby the sending and receiving party do not need to interact with the message queue at the same time. Messages placed onto the queue are stored until the recipient retrieves them.  Message queues have implicit or explicit limits on the size of data that may be transmitted in a single message and the number of messages that may remain outstanding on the queue
- **Comparison**

| Attributes | Description | RabbitMQ | Amazon SQS | Apache Kafka | Apache Pulsar |    NATS    | NATS Streaming | Redis   |   ZeroMQ    |   Pravega   |
|:-----------|:------------|:---------|:-----------|:-------------|:--------------|:-----------|:------------|:-----------|:------------|:------------|
| Category   | AMQP/Stream/MQ | AMQP  |     MQ     |    Stream    |    Stream     |     MQ     |    Stream   |  Stream   |      MQ      |    Stream   |
| Throughput | Transfer per second (size) | 100 MB/s  |     NA    |    600 MB/s   |  300 MB/s  |      NA     |    NA     |      NA      |   NA   |
| Latency    |  |   |          |        |         |          |      |     |            |       |
| Delivery Guarantees | Semantics  | At most once, at least once | NA | At least once, exactly once | At most once, at least once, exactly once (JetStream) | At most once, at least once, exactly once  (JetStream) | NA | NA | NA |
| Reliability |
| Ordering |
| Durability | Message Persistence | Before | No | Always | Always | No | Always | Possible | No | Always |
| Error Handling |
| Multi-tenancy |
| AuthN |
| AuthZ |
| Monitoring |
| Priority Scheduling |
| Retry Mechanism |
| High Availability and Fault Tolerance |
| Persistence |
| Integrations |
| License | Software access | Mozilla Public License | Proprietary | Apache 2.0 | Apache 2.0 | Apache 2.0 | Apache 2.0 | BSD 3 Clause | LGPLv3+ | Apache 2.0 |

- **References**
    - Benchmarks - https://www.confluent.io/blog/kafka-fastest-messaging-system/
