# SCALING

## <ins>INTRODUCTION
Scaling is selecting the required level of data detail, project control discipline and range of project control practices to match a project's characteristics. Scaling issue occurs when the existing hardware and software infrastructure can't handle an increased volume of transactions. Cloud computing is one of the area where scaling problem occurs due to the increase in number of servers. We can use **load balancers** for understanding **vertical** or **horizontal** scaling solutions.
***

## <ins>SCALABILITY

The **Scalability** of an application can be measured by the number of requests it can effectively support simultaneously. The point at which an application can no longer handle additional requests effectively is the limit of its Scalability. This limit is reached when a critical hardware resource runs out, requiring different or more machines. Scaling these resources can include any combination of adjustments to CPU and physical memory, hard disk and the network bandwidth.
***

## <ins>LOAD BALANCING

Load balancing is the process of distributing a set of tasks over a set of resources, with the aim of making their overall processing more efficient. It can optimize the response time and avoid unevenly overloading some compute nodes while other compute nodes are left idle. A load balancer serves as the single point of contact for clients. The load balancer distributes incoming application traffic across multiple targets in multiple availability zones. This increases the availability of the application. A load balancer can have one or more listeners.
 A **listener** checks for connection requests from clients, using the protocol and port that we configure. The rules that we define for a listener determines how the load balancer routes requests to its registered targets. Each rule have a priority, one or more actions and one or more conditions. When the conditions for a rule are met, then its actions are performed. We must define a default rule for each listener. Each target group routes requests to one or more registered targets using the protocol and port number that we specify. We can register a target with multiple target groups. We can configure health checks on a per target group basis. Health checks are performed on all targets registered to a target group that is specified in a listener rule for our load balancer.
 ***

## <ins>SCALING TYPES

1. **HORIZONTAL SCALING**

2. **VERTICAL SCALING**
***

## <ins>HORIZONTAL SCALING

Horizontal scaling means scaling by adding more machines to our pool of resources. It is also described as **Scaling out**. It requires breaking a sequential piece of logic into smaller pieces so that they can be executed in parallel across multiple machines. In a database world, horizontal scaling is usually based on the partitioning of the data. In distributed computing, the lack of a shared address space makes data sharing more complex. It also makes the process of sharing, passing or updating data more costly since you have to pass copies of the data. Scaling out allows to combine the power of multiple machines into a single virtual machine with the combined power of all of them. That is, we are not limited to the capacity of a single unit. It also offers built-in redundancy.
eg: Cassandra,MongoDB,Google Cloud Spanner
***

## <ins>VERTICAL SCALING

Vertical scaling refers to scaling by adding more power to an existing machine using additional processors and memory units. It is also termed as **Scaling up**. In many aspects, vertical scaling is easier because the logic really doesn't need to change.Unlike Horizontal scaling, here we are running the same code on higher machines. Here the data lives on a single node and scaling is done through multi-core like spreading the load between the CPU and RAM resouces of the machine. But it is limited to the capacity of one machine, scaling beyond that capacity can involve downtime. Concurrent programming on multi-core machines is performed via multi-threading and in-process message passing. In a multi-threaded scenario, we can assume the existence of a shared address space, so data sharing and message passing can be done by passing a reference.It is cost effective. But here there is only a single point of failure.
eg: MySQL, Amazon RDS
***

   * Moving between the two models is a better choice than sticking only into a particular one. For instance, in storage, we often want to switch between a single local disk to a distributed storage system. Building flexibility into the system, where some layers of the application run on vertically scaled machines and other layers on horizontally scaled infrastructure remains a matter of designing for parallelization. This can be achieved in two ways.

1. Design it from the outset as a decoupled set of services, making the code easier to move, meaning we can add more resources when needed without breaking the ties between the code sets.
2. Partition the application and data model so the parallel units don't share anything.

## <ins>REFERENCES<ins>

* www.section.io

* docs.aws.amazon.com