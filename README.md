# Aplicatii Distribuite Avansate
# Lab1
A fast implementation process using TPL (OpenMP) and AKKA.NET (OpenMPI). During the paper a parallel was made between 2 methodologies. Tests with Sleepy Fibonacci and Busy Fibonacci were also applied.

# TPL sleepy
![image](https://user-images.githubusercontent.com/26895687/84590177-f2066e80-ae3c-11ea-8e37-6074b6ef6d3a.png)

# TPL busy
![image](https://user-images.githubusercontent.com/26895687/84590191-15311e00-ae3d-11ea-9018-b04e8ed19d26.png)

It is noticed that when we run Bussy Fibonacci with more threads - the execution time increases faster than when we use sleepy Fibonacci. This is because busy Fibonacci will consume processor resources more drastically than sleepy Fibonacci. Sleepy fibonacci involves putting the thread to sleep, thus reducing consumption.

# AKKA.Net sleepy
![image](https://user-images.githubusercontent.com/26895687/84590225-693c0280-ae3d-11ea-9d6e-4ed427700866.png)

# AKKA.Net busy
![image](https://user-images.githubusercontent.com/26895687/84590237-7c4ed280-ae3d-11ea-8a2c-9b604395733e.png)

# TPL vs AKKA
![image](https://user-images.githubusercontent.com/26895687/84590250-97214700-ae3d-11ea-85e1-018c4015af18.png)

# Conclusion
If we compare this two approaches: The execution time in the case of TPL is a little shorter. This is due to the fact that there is no need to synchronize the actors and send messages to the actors, but at the same time AKKA.NET allows a more efficient decoupling. In addition, AKKA.NET allows the encapsulation of this competition process. We have no business with threads, each actor runs on his thread and is asleep as long as he does not receive messages. With the help of AKKA.NET it is very efficient to ensure communication between remote applications and message processing. When the number of threads exceeds the number of threads of the processor, the execution time increases.

# Lab2
RabbitMQ was used in this paper. A message queue that can be used by several processes / applications. With the help of RabbitMQ we can ensure communication between several processes regardless of the programming language in which these applications (processes) were written. C # and JavaScript (Node JS) languages were used in this lab.

![image](https://user-images.githubusercontent.com/26895687/84590317-30e8f400-ae3e-11ea-8161-a1193a8f2851.png)

Here it is reflected how a Publisher sends messages, and 4 Receivers receive these messages. (2 NodeJS and 2 C #) A balanced degree of message distribution is observed. Each application receives an approximate number of messages. Thus RabbitMQ is a very effective tool in cases when we have applications that perform the same thing but are written in different languages. With its help we can distribute some work jobs between these applications.

# RabbitMQ vs AKKA.NET (Open MPI)
Additions to the implementation through RabbitMQ: + There are durable queues, the messages are persistent in case of need. + We can perform an acknowledgment mechanism / Guarantee of message delivery. + Decoupling of programming languages. + Messages are distributed automatically.

The pluses of implementing through AKKA.NET: + In a process there are several actors (threads). Whereas in the case of RabbitMQ a process processes a message at a certain point in time. + Actors are very cheap to create. + However, it was easier to synchronize the actors than the applications in the case of RabbitMQ + It is easier to scale
