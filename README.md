# Advprog Tutorial 9 - Subscriber
## Priscilla Natanael Surjanto - 2306152153

### Understanding subscriber and message broker
#### 1. What is amqp?
AMQP (Advanced Message Queuing Protocol) is an open standard for messaging that enables reliable, asynchronous communication between different software systems. It utilizes message queues to send and receive messages, ensuring decoupled, flexible, and fault-tolerant communication. AMQP also supports features like message acknowledgment, durable queues, and secure communication through SSL/TLS. It is commonly used in microservices, real-time systems, and task queues.  Popular implementations include RabbitMQ and Apache Qpid. AMQP allows systems, often with different technologies, to communicate efficiently and reliably.

####  2. What does it mean? `guest:guest@localhost:5672`, what is the first guest, and what is the second guest, and what is localhost:5672 is for?
The connection string `guest:guest@localhost:5672` is used to connect to a message broker like RabbitMQ. The first `guest` is the username and the second `guest` is the password. `localhost:5672` specifies that the broker is running on the local machine (localhost) and listening on port 5672, which is the default for AMQP connections.

### Simulation slow subscriber
There are up to 26 queues in my computer. I ran the publisher for about 10 times, and messages were being published too fast that the subscriber couldn't keep up receiving because of the sleep. So, RabbitMQ put those messages in the queue.
![image](https://github.com/user-attachments/assets/6faa51be-d38a-47e8-a7ab-02cdaf934b60)

### Reflection and Running at least three subscribers
I tried running three subscriber instances at once, and they were competing to receive the messages. By default, RabbitMQ uses a round-robin method, so each subscriber receives approximately one-third of the messages. This parallel processing allows all three subscribers to handle messages simultaneously, causing the queue to empty more quickly. But, this causes an issue when we want all subscribers to receive the same amount of messages. To do this, we can change the code from using the round-robin method to using fanout method.
![Screenshot (255)](https://github.com/user-attachments/assets/d7bca5cd-a5b5-41f9-8168-14a3a2109a7e) 
