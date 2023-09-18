# Questions

### TCP vs UDP for Interview Purpose

TCP and UDP are two different transport layer protocols that are used to transmit data over a network. TCP is a connection-oriented protocol, while UDP is a connectionless protocol.

**Connection-Oriented**

A connection-oriented protocol establishes a connection between the sender and receiver before sending any data. This connection is used to ensure that all data is delivered in the correct order and that no data is lost.

**Connectionless**

A connectionless protocol does not establish a connection between the sender and receiver before sending any data. This makes UDP faster and more efficient than TCP, but it also makes it less reliable.

Here is a table that summarizes the key differences between TCP and UDP:

| Feature | TCP | UDP |
|---|---|---|
| Connection-oriented | Yes | No |
| Reliable | Yes | No |
| Ordered delivery | Yes | No |
| Congestion control | Yes | No |
| Flow control | Yes | No |
| Overhead | High | Low |
| Speed | Slow | Fast |

**Use Cases**

TCP is typically used for applications where reliability and ordered delivery are important, such as file transfers, email, and web browsing. UDP is typically used for applications where speed and low latency are more important than reliability, such as online gaming, VoIP, and streaming video.

**Interview Questions**

Here are some interview questions that you may be asked about TCP and UDP:

* What are the key differences between TCP and UDP?
* When would you use TCP?
* When would you use UDP?
* What are the advantages and disadvantages of TCP?
* What are the advantages and disadvantages of UDP?

**Example Answers**

* **Key differences between TCP and UDP:** TCP is a connection-oriented protocol, while UDP is a connectionless protocol. TCP is reliable and ordered delivery, while UDP is unreliable and unordered delivery. TCP has high overhead, while UDP has low overhead. TCP is slow, while UDP is fast.
* **When to use TCP:** When reliability and ordered delivery are important, such as file transfers, email, and web browsing.
* **When to use UDP:** When speed and low latency are more important than reliability, such as online gaming, VoIP, and streaming video.
* **Advantages of TCP:** Reliability, ordered delivery, congestion control, and flow control.
* **Disadvantages of TCP:** High overhead and slow speed.
* **Advantages of UDP:** Low overhead and fast speed.
* **Disadvantages of UDP:** Unreliable and unordered delivery.



# Question

## PUBLIC SUBNET VS PRIVATE SUBNET

### Difference between Private and Public Subnet in AWS

**Private Subnet:**

* A private subnet is a subnet that does not have a direct route to the internet.
* Resources in a private subnet cannot be accessed directly from the internet.
* To access the internet, resources in a private subnet must use a NAT gateway or a bastion host.
* Private subnets are typically used for resources that do not need to be publicly accessible, such as database servers and application servers.

**Public Subnet:**

* A public subnet is a subnet that has a direct route to the internet.
* Resources in a public subnet can be accessed directly from the internet.
* Public subnets are typically used for resources that need to be publicly accessible, such as web servers and load balancers.

**Interview Point of View:**

When answering an interview question about the difference between private and public subnets in AWS, you should be able to clearly explain the following:

* **What is a subnet?**
* **What is the difference between a public subnet and a private subnet?**
* **What are the benefits of using private and public subnets?**
* **When should you use a private subnet and when should you use a public subnet?**

Here is an example of how you could answer an interview question about the difference between private and public subnets in AWS:

> **Interviewer:** What is the difference between a private subnet and a public subnet in AWS?

> **Candidate:** A private subnet is a subnet that does not have a direct route to the internet. Resources in a private subnet cannot be accessed directly from the internet. To access the internet, resources in a private subnet must use a NAT gateway or a bastion host. Private subnets are typically used for resources that do not need to be publicly accessible, such as database servers and application servers.

> A public subnet is a subnet that has a direct route to the internet. Resources in a public subnet can be accessed directly from the internet. Public subnets are typically used for resources that need to be publicly accessible, such as web servers and load balancers.

> **Interviewer:** What are the benefits of using private and public subnets?

> **Candidate:** Private subnets provide better security for resources that do not need to be publicly accessible. By placing resources in a private subnet, you can help to protect them from unauthorized access and attacks.

> Public subnets provide better performance for resources that need to be accessed from the internet. By placing resources in a public subnet, you can reduce latency and improve throughput.

> **Interviewer:** When should you use a private subnet and when should you use a public subnet?

> **Candidate:** You should use a private subnet for resources that do not need to be publicly accessible, such as database servers and application servers. You should use a public subnet for resources that need to be publicly accessible, such as web servers and load balancers.

**Additional Tips:**

* Be prepared to discuss the different ways to access the internet from resources in a private subnet.
* Be prepared to discuss the different security considerations for public and private subnets.
* Be prepared to provide examples of how you have used public and private subnets in the past.

## most asked
==========================================================================================================================

 
1) difference between ext2 , ext3 and ext4
2
## linux 

## services
## networking

## AWS