# Advprog Tutorial 9 - Subscriber
## Priscilla Natanael Surjanto - 2306152153

### Understanding subscriber and message broker
#### 1. What is amqp?
AMQP (Advanced Message Queuing Protocol) is an open standard for messaging that enables reliable, asynchronous communication between different software systems. It utilizes message queues to send and receive messages, ensuring decoupled, flexible, and fault-tolerant communication. AMQP also supports features like message acknowledgment, durable queues, and secure communication through SSL/TLS. It is commonly used in microservices, real-time systems, and task queues.  Popular implementations include RabbitMQ and Apache Qpid. AMQP allows systems, often with different technologies, to communicate efficiently and reliably.

####  2. What does it mean? `guest:guest@localhost:5672`, what is the first guest, and what is the second guest, and what is localhost:5672 is for?
The connection string `guest:guest@localhost:5672` is used to connect to a message broker like RabbitMQ. The first `guest` is the username and the second `guest` is the password. `localhost:5672` specifies that the broker is running on the local machine (localhost) and listening on port 5672, which is the default for AMQP connections.