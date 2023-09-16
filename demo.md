*31/7*
# summary 21/7 ---------------> roles , MFA , policies

> policy ----inline policies[you can find this in add permissions]
inline policies are made by user but if we delete the user the inline policies will also be delete
inline policies are attacted to the user Identity


### MFA --------  methods 
 1. virtual  authentication app 
 2.hardware token
 3. security keys

To access some service via cli on aws we need private key and secret key 
AWS CLI uses these two credentials for accessing services
We have three types of Keys:
Access Key ID - A unique identifier that is used with your Access Key Secret to authenticate requests you make
ACCESS KEY ID AND SECRET ACCESS KEY (for programmatic access)
IAM USER NAME AND PASSWORD(for console login )
SSH KEYS FOR EC2 INSTANCES
If you want to restrict a specific IAM User from logging into your account, use an Access Key
instead of their password. This way they cannot log in using any other method or tool besides
the ones provided through the API/CLI tools that require them. To create new users with limited privileges
and without needing passwords, set up MFA as well so even those who know the usernames may
not easily gain unauthorized access.

 AWS PUBLIC 
 CLIENT PRIVATE 

roles in aws 
- predefined roles - created by amazon itself which has certain permission sets assigned to it like ec2 admin
role etc..these pre defined roles can only perform actions allowed under its scope .we don't get
option to modify role definition after creation unless we go for custom role creation process where we define our own


action > security >modify iam roles

summary 21/7 ---------------> roles , MFA , policies

principle action resources
>identity_base_polices  resources_base_polices

role 
less human interaction 
temp access
communication between 2 services



--------------------------------------------------------------------------------------
24/07
# s3 in aws
[global service]
> scalable
> high available
> durable

### S3 is used for
>- storing static website hosting (html+css+js), media storage & distribution, backups, archivals, log collection, application development artifacts like jars or war files, mobile app deploys and other similar types of assets required by your applications

region ---> geolocation data centre
availability zone ------> group of racks located within region
bucket name must be unique globally across all regions

object --> data + metadata
s3 use object

## bucket
bucket name must be unique globally across all regions
s3 url >bucket url
copy url > object url

transfer acceleration 
(speeding up uploads and downloads)---> for large files over slow internet connections
CDN 
(content delivery network )---> distributes content around worldwide edge locations
### versioning
keep multiple versions of an object. when you update a file, the previous version is saved as
well so that if there's any problem with new updates we have older copies still intact.



--------------------------------------------------------------------------------------------------------------------

bucket policies
: allows fine-grained control to users who are allowed or denied actions on specific buckets or objects

type of bucket policies:
           principle -> user
                             action -> read only
                             resource-> bucketname/*
:resource base  resource->action

identity  base   policies:
s3 resource
action 
principle -> user

resource base :
princple ->user arn 
action 
resource -> bucket

---------------------------------------------------------------------------------------------------------------------
# 27/7

### lifecycle rule of s3
--------------------------------------------------------------------------------------------------------------------------
# 28/7

## EC2 -- Elastic compute cloud -----availibility specfic

>to get access of instance via ssh 
`` ssh  -i <key_name> ec2-user@<ip>  ``

type of instance 
1. general instance (balance memory & CPU)
* t2 micro 
* m5a.large
* c4.xlarge
2. Compute optimized instances (CPU)   (more cpu than RAM)
* C5
* M6g
* R5d
3. Memory Optimized Instances(RAM) (More RAM)
* r5ad, x1e
* i3en
* z1d
4. Accelerated computing instances for graphics and video processing workloads like DLAMI's from
Nvidia (Graphic optimised)

5.Storage optimised
* IOPS intensive applications such as databases or big data analytics

6. HPC optimised
* High performance computing clusters with high core counts

-----------------------------------------------------------------------------------------------------------------------



## General purpose
 instances provide a balance of compute, memory, and networking resources. You can use them for a variety of workloads, such as:

application servers
gaming servers
backend servers for enterprise applications
small and medium databases
Suppose that you have an application in which the resource needs for compute, memory, and networking are roughly equivalent. You might consider running it on a general purpose instance because the application does not require optimization in any single resource area.

## Compute optimized 
instances are ideal for compute-bound applications that benefit from high-performance processors. Like general purpose instances, you can use compute optimized instances for workloads such as web, application, and gaming servers.

However, the difference is compute optimized applications are ideal for high-performance web servers, compute-intensive applications servers, and dedicated gaming servers. You can also use compute optimized instances for batch processing workloads that require processing many transactions in a single group.

## Memory optimized 
instances are designed to deliver fast performance for workloads that process large datasets in memory. In computing, memory is a temporary storage area. It holds all the data and instructions that a central processing unit (CPU) needs to be able to complete actions. Before a computer program or application is able to run, it is loaded from storage into memory. This preloading process gives the CPU direct access to the computer program.

Suppose that you have a workload that requires large amounts of data to be preloaded before running an application. This scenario might be a high-performance database or a workload that involves performing real-time processing of a large amount of unstructured data. In these types of use cases, consider using a memory optimized instance. Memory optimized instances enable you to run workloads with high memory needs and receive great performance.

## Accelerated computing instances
 use hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs. Examples of these functions include floating-point number calculations, graphics processing, and data pattern matching.

In computing, a hardware accelerator is a component that can expedite data processing. Accelerated computing instances are ideal for workloads such as graphics applications, game streaming, and application streaming.

## Storage optimized instances
 are designed for workloads that require high, sequential read and write access to large datasets on local storage. Examples of workloads suitable for storage optimized instances include distributed file systems, data warehousing applications, and high-frequency online transaction processing (OLTP) systems.

In computing, the term input/output operations per second (IOPS) is a metric that measures the performance of a storage device. It indicates how many different input or output operations a device can perform in one second. Storage optimized instances are designed to deliver tens of thousands of low-latency, random IOPS to applications. 

You can think of input operations as data put into a system, such as records entered into a database. An output operation is data generated by a server. An example of output might be the analytics performed on the records in a database. If you have an application that has a high IOPS requirement, a storage optimized instance can provide better performance over other instance types not optimized for this kind of use case.


# EC2 pricing

### On-Demand Instances 
>are ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use.

Sample use cases for On-Demand Instances include developing and testing applications and running applications that have unpredictable usage patterns. On-Demand Instances are not recommended for workloads that last a year or longer because these workloads can experience greater cost savings using Reserved Instances.

### Reserved Instances 
>are a billing discount applied to the use of On-Demand Instances in your account. There are two available types of Reserved Instances:

- Standard Reserved Instances
- Convertible Reserved Instances

You can purchase Standard Reserved and Convertible Reserved Instances for a 1-year or 3-year term. You realize greater cost savings with the 3-year option. 



**Standard Reserved Instances**: This option is a good fit if you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them. Reserved Instances require you to state the following qualifications:

- Instance type and size: For example, m5.xlarge
- Platform description (operating system): For example, Microsoft Windows Server or Red Hat Enterprise Linux
- Tenancy: Default tenancy or dedicated tenancy
You have the option to specify an Availability Zone for your EC2 Reserved Instances. If you make this specification, you get EC2 capacity reservation. This ensures that your desired amount of EC2 instances will be available when you need them. 

**Convertible Reserved Instances**: If you need to run your EC2 instances in different Availability Zones or different instance types, then Convertible Reserved Instances might be right for you. Note: You trade in a deeper discount when you require flexibility to run your EC2 instances.

At the end of a Reserved Instance term, you can continue using the Amazon EC2 instance without interruption. However, you are charged On-Demand rates until you do one of the following:

Terminate the instance.
Purchase a new Reserved Instance that matches the instance attributes (instance family and size, Region, platform, and tenancy).

### Spot Instances 
>are ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.

Suppose that you have a background processing job that can start and stop as needed (such as the data processing job for a customer survey). You want to start and stop the processing job without affecting the overall operations of your business. If you make a Spot request and Amazon EC2 capacity is available, your Spot Instance launches. However, if you make a Spot request and Amazon EC2 capacity is unavailable, the request is not successful until capacity becomes available. The unavailable capacity might delay the launch of your background processing job.

After you have launched a Spot Instance, if capacity is no longer available or demand for Spot Instances increases, your instance may be interrupted. This might not pose any issues for your background processing job. However, in the earlier example of developing and testing applications, you would most likely want to avoid unexpected interruptions. Therefore, choose a different EC2 instance type that is ideal for those tasks.

### Dedicated Hosts 
>are physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. 

You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance. You can purchase On-Demand Dedicated Hosts and Dedicated Hosts Reservations. Of all the Amazon EC2 options that were covered, Dedicated Hosts are the most expensive.

### EC2 insatnce saving plan
AWS offers Savings Plans for a few compute services, including Amazon EC2. EC2 Instance Savings Plans reduce your EC2 instance costs when you make an hourly spend commitment to an instance family and Region for a 1-year or 3-year term. This term commitment results in savings of up to 72 percent compared to On-Demand rates. Any usage up to the commitment is charged at the discounted Savings Plans rate (for example, $10 per hour). Any usage beyond the commitment is charged at regular On-Demand rates.



The EC2 Instance Savings Plans are a good option if you need flexibility in your Amazon EC2 usage over the duration of the commitment term. You have the benefit of saving costs on running any EC2 instance within an EC2 instance family in a chosen Region (for example, M5 usage in N. Virginia) regardless of Availability Zone, instance size, OS, or tenancy. The savings with EC2 Instance Savings Plans are similar to the savings provided by Standard Reserved Instances.



Unlike Reserved Instances, however, you don't need to specify up front what EC2 instance type and size (for example, m5.xlarge), OS, and tenancy to get a discount. Further, you don't need to commit to a certain number of EC2 instances over a 1-year or 3-year term. Additionally, the EC2 Instance Savings Plans don't include an EC2 capacity reservation option.



Later in this course, you'll review AWS Cost Explorer, which you can use to visualize, understand, and manage your AWS costs and usage over time. If you're considering your options for Savings Plans, you can use AWS Cost Explorer to analyze your Amazon EC2 usage over the past 7, 30, or 60 days. AWS Cost Explorer also provides customized recommendations for Savings Plans. These recommendations estimate how much you could save on your monthly Amazon EC2 costs, based on previous Amazon EC2 usage and the hourly commitment amount in a 1-year or 3-year Savings Plan.




-----------------------------------------------------------------------------------------------------------------------
type of boot



t2 t3 unlimated bottomneck , active director



==========================================================================================================================

# 02/8

## AMI 

Amazon Machine Image is a template that contains the software configuration to launch an Amazon EC2 Instance


# EBS Volume types

![EBS Image](https://i.ytimg.com/vi/Z7ORHz1AUMI/maxresdefault.jpg)


## General purpose SSD (gp2)

- GP2 is the default EBS Volume type for the amazon EC2 Instance
- GP2 Volumes are backed by SSDs
- General purpose , balances both price and performance
- Ratio of 3 IOPS/GB with upto 10,000 IOPS {input/output Per Second}
- Boot Volume having low latency
  Volume size - 1GB-16TB

======================================================================================================================

# 05/8

## EFS > port(2049)

storage type > standard and one zone


lifecycle management
transition into IA 

=======================================================================================================================
# 07/8

## security group > region specific 
>security group is attact to NIC
-Security Group acts as a virtual firewall in AWS
-Security Group controls the traffic for one or more instances
-Security Group only contains allow rules
-Security Group is stateful
-Security Group evaluate all rules before deciding whether to allow traffic
-Security Group can be attached to multiple instances
-Security Group can be attached to multiple ENI's
-Security Group can be attached to multiple ELB's

## NACL > subnet specific
>Network Access Control List is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets
-NACLs are stateless
-NACLs rules are evaluated in order
-NACLs have separate inbound and outbound rules
-NACLs can have allow and deny rules

## Networking interfence
-ENI > elastic network interface
-Elastic Network Interface is a logical networking component in a VPC that represents a virtual network card
-ENI can be created independently and attached to an EC2 Instance in the same AZ
-ENI can be moved from one EC2 Instance to another EC2 Instance
-ENI can be moved from one AZ to another AZ

## elastic ip 
-Elastic IP is a static public IPv4 address designed for dynamic cloud computing
-Elastic IP is associated with your AWS account
-Elastic IP can be associated with one EC2 Instance at a time
-Elastic IP can be moved from one EC2 Instance to another EC2 Instance
-Elastic IP can be moved from one AZ to another AZ
-Elastic IP can be moved from one VPC to another VPC
-Elastic IP can be moved from one AWS account to another AWS account

## NIC 
Network Interface Card is a hardware component that is installed in a computer so that it can be connected to a network
NIC is a physical networking component
NIC is a hardware component

## name base hosting vs ip base hosting
name base hosting > domain name
ip base hosting > ip address


=========================================================================================================================
# 09/8

## load balancer
>load balancer is a device that acts as a reverse proxy and distributes network or application traffic across a number of servers
-Load Balancer is a device that distributes network or application traffic across a number of servers

types of load balancer
1. Application Load Balancer
2. Network Load Balancer  
3. Classic Load Balancer     ----> round robin format
4. Gateway load balancer

==========================================================================================================================
# 10/8


## application load balancer
-Application Load Balancer is best suited for load balancing of HTTP and HTTPS traffic
-Application Load Balancer operates at Layer 7 of the OSI model
-Application Load Balancer supports path-based routing
-Application Load Balancer supports host-based routing
-Application Load Balancer supports containerized applications
-Application Load Balancer supports Lambda functions
-Application Load Balancer supports WebSockets

## target group
-Target Group is a logical grouping of targets (EC2 Instances, ECS Tasks, Lambda Functions) that you register with a load balancer


---------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------


HTTP status codes are three-digit numbers returned by a web server to indicate the status of a client's request. These codes are grouped into different classes, each with its own meaning. Here are some common HTTP status codes along with their meanings:

### 1xx Informational

- **100 Continue:** The server has received the request headers and the client should proceed to send the request body.

### 2xx Success

- **200 OK:** The request has succeeded. The information returned with the response depends on the method used in the request.
- **201 Created:** The request has been fulfilled, and a new resource has been created as a result.
- **204 No Content:** The server successfully processed the request, but there is no content to send in the response.

### 3xx Redirection

- **301 Moved Permanently:** The requested page has been permanently moved to a new location.
- **302 Found (or Moved Temporarily):** The requested page has been temporarily moved to a new location.
- **304 Not Modified:** The client's cached version of the requested page is up to date, so the server responds with this status and no content.

### 4xx Client Errors

- **400 Bad Request:** The server cannot understand the request due to a client error (e.g., malformed request syntax).
- **401 Unauthorized:** The request requires authentication, and the client hasn't provided valid credentials.
- **403 Forbidden:** The client does not have permission to access the requested resource.
- **404 Not Found:** The server could not find the requested resource.
- **405 Method Not Allowed:** The method specified in the request (e.g., GET, POST) is not allowed for the resource.
- **409 Conflict:** The request could not be completed due to a conflict with the current state of the target resource.

### 5xx Server Errors

- **500 Internal Server Error:** The server encountered an unexpected condition that prevented it from fulfilling the request.
- **502 Bad Gateway:** The server, while acting as a gateway or proxy, received an invalid response from the upstream server it accessed.
- **503 Service Unavailable:** The server is currently unable to handle the request due to temporary overloading or maintenance of the server.

Please note that this is not an exhaustive list, and there are additional HTTP status codes beyond these examples. The codes listed above are some of the most common ones you might encounter.

To interpret HTTP status codes accurately, it's important to refer to the official HTTP specification (RFC 7231) or relevant documentation for the specific service you are working with, as their meanings can sometimes vary slightly depending on the context.

======================================================================================================================
# 11/8

## auto scaling 
>auto scaling is a service that automatically adjusts the capacity of your EC2 fleet according to the conditions you define 
### horizontal auto scale
>horizontal auto scale is a type of auto scaling that adds or removes EC2 instances to match the desired capacity, based on a metric that measures the average CPU utilization of the instances in the group
### vertical auto scale
>vertical auto scale is a type of auto scaling that adjusts the size of the EC2 instances in the group to match the desired capacity, based on a metric that measures the average CPU utilization of the instances in the group

types of vertical auto scaling
1.static 
2.dynamic
3.scheduled

------------------------------------------------------------------------------------------------------------------
 ### 2 step to launch autoscaling
1 launch template
2 ASG

### autoscaling group 
>autoscaling group is a logical grouping of EC2 instances that share similar characteristics and are treated as a logical grouping for the purposes of scaling and management
group capacity ---> 1 mininum 2.maximun  3.desired

average scaling policy  

conditon   ---- 50 >

action  increase and decrease instance

condition alarm action



---------------------------------------------
to add stress 

yum install stress 
stress --help

yes > /dev/null &


-------------------------------------------------------------------------------------------------
==============================================================================================================================================================

# 17/08

# 28/08
 
 ## carier gateway
  >carrier gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between instances in your VPC and other AWS services without imposing availability risks or bandwidth constraints on your network traffic

  ## ldap
  >Lightweight Directory Access Protocol is an open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an Internet Protocol (IP) network

  ## active directory 
  >Active Directory is a directory service that Microsoft developed for Windows domain networks. It is included in most Windows Server operating systems as a set of processes and services


  # vpn
  >Virtual Private Network is a service that allows you to securely connect to a private network from a remote location, typically over the Internet

  1. network id 
  2. gateway
  3. public  



  # traffic mirrioring
  >traffic mirroring is a feature that you can use to copy network traffic from an elastic network interface of Amazon EC2 instances

## 09/09
### cloudwatch
>CloudWatch is a monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers. CloudWatch provides you with data and actionable insights to monitor your applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health

### alarms
>CloudWatch alarm watches a single metric over a time period that you specify, and performs one or more actions based on the value of the metric relative to a given threshold over a number of time periods
### logs
>CloudWatch Logs is a service for ingesting, storing, and accessing your log files from Amazon EC2 instances, AWS CloudTrail, Route 53, and other sources
### dashboards
>CloudWatch Dashboards is a service that you can use to create customized dashboards that you can use to monitor your AWS resources in a single view
### metrics
>CloudWatch Metrics is a service that you can use to collect data from your AWS resources and applications
### events
>CloudWatch Events is a service that you can use to route events from your AWS services to targets to automate actions
### insights
>CloudWatch Logs Insights is a service that you can use to interactively search and analyze your log data in Amazon CloudWatch Logs

### how to send logs of service via cloudagent
1.install cloudagent
2.configure it
<mark> configuration file of aws: /var/awslogs/etc/awslogs.conf </mark>
3.add role so that instance can access the cloudwatch
4.restart the service
5.check the logs in cloudwatch
6.create log group for each application

## 11/09
### RDS
defination:
- database as a service
- managed relational databases
- fully compatible with SQL standard
- scales automatically, up or down based on demand
- supports multi AZ deployment
- backup & restore
- read replicas
- encryption at rest (in transit)
- security features like IAM authentication, SSL connections etc...
#### types
##### single db
- provisioned IOPS SSD storage
- automated backups
- automatic failover
- scaling options
##### Multi DB
- shared storage
- manual backups
- cross region replication
- point in time recovery
- enhanced monitoring
- auditing
- read replicas
##### Aurora
- MySQL compatible engine
- auto scaling
- serverless architecture
- global deployments
- read replicas
- zero downtime migration
- encrypted storage
- VPC only
- multimaster
- parallel query execution
- high availability and durability
- enterprise grade performance
- support for PostgreSQL
- data API
- Amazon S3 integration
- AWS PrivateLink
- Oracle compatibility
- native JSON support
- built-in machine learning
- local caching of frequently accessed data

### rds proxy
- secure access to your DBs from anywhere using the internet.
- no need to open ports 5432/60017
- can be used by multiple applications running on different EC2 instances without having to configure each application individually.
### reverse proxy
- a webserver that sits between clients and servers and forwards requests to them as appropriate.


# 12/09
## route53
- DNS service 
### SOA
- start of authority
- contains information about the domain
- name of the server that supplied the data for the zone
- administrator of the zone
- current version of the data file
### NS
- name server
- contains a list of the authoritative name servers for the domain
### A
- address record
- maps a hostname to a 32-bit IPv4 address
### AAAA
- IPv6 address record
- maps a hostname to a 128-bit IPv6 address
### CNAME
- canonical name record
- maps an alias name to a true or canonical domain name
### MX
- mail exchange record
- maps a domain name to a list of mail exchange servers for that domain
### PTR
- pointer record
- maps an IPv4 address to the canonical name for that host
### SRV
- service locator
- specifies the location of services
### TXT
- text record
- originally for arbitrary human-readable text in a DNS record
### SPF
- sender policy framework
- specifies which hosts are allowed to send mail from a given domain name

## routing policy
### simple routing policy
- use when you have a single resource that performs a given function for your domain
### weighted routing policy
- use when you want to distribute traffic across multiple resources based on weights assigned to each resource
### latency routing policy
- use when you have resources in multiple AWS Regions and you want to route traffic to the region that provides the best latency
### failover routing policy
- use when you want to configure active-passive failover
### geolocation routing policy
- use when you want to route traffic based on the location of your users
### geoproximity routing policy
- use when you want to route traffic based on the location of your resources and, optionally, shift traffic from resources in one location to resources in another
### multivalue answer routing policy
- use when you want Route 53 to respond to DNS queries with up to eight healthy records selected at random
### ip based routing policy
- use when you have resources in multiple AWS Regions and you want to route traffic to the region that provides the best latency for your users


## 13/09

### added certificate to website (SSL) via ACM
- AWS Certificate Manager is a service that lets you easily provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources
- SSL/TLS certificates provisioned through AWS Certificate Manager are free

## 14/09
### cloudfront
- Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment
- CloudFront is integrated with AWS – both physical locations that are directly connected to the AWS global infrastructure, as well as other AWS services
- CloudFront works seamlessly with services including AWS Shield for DDoS mitigation, Amazon S3, Elastic Load Balancing or Amazon EC2 as origins for your applications, and Lambda@Edge to run custom code closer to customers’ users and to customize the user experience

cloudfront


## http method and their definations
| Method | Description                                                  |
| ------ | ------------------------------------------------------------ |
| GET    | The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data. |
| HEAD   | The `HEAD` method asks for a response identical to that of a `GET` request, but without the response body. |
| POST   | The `POST` method is used to submit an entity to the specified resource, often causing a change in state or side effects on the server. |
| PUT    | The `PUT` method replaces all current representations of the target resource with the request payload. |
| DELETE | The `DELETE` method deletes the specified resource.          |
| CONNECT | The `CONNECT` method establishes a tunnel to the server identified by the target resource. |
| OPTIONS | The `OPTIONS` method is used to describe the communication options for the target resource. |

## Amazon Redshift

Amazon Redshift(opens in a new tab) is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data

# 6 strategies for migration

When migrating applications to the cloud, six of the most common migration strategies(opens in a new tab) that you can implement are:

### Rehosting
>Rehosting also known as “lift-and-shift” involves moving applications without changes. 
In the scenario of a large legacy migration, in which the company is looking to implement its migration and scale quickly to meet a business case, the majority of applications are rehosted.
### Replatforming
>Replatforming, also known as “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit. Optimization is achieved without changing the core architecture of the application.
### Refactoring/re-architecting
>Refactoring (also known as re-architecting) involves reimagining how an application is architected and developed by using cloud-native features. Refactoring is driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.  
### Repurchasing
>Repurchasing involves moving from a traditional license to a software-as-a-service model. 
For example, a business might choose to implement the repurchasing strategy by migrating from a customer relationship management (CRM) system to Salesforce.com.
### Retaining
>Retaining consists of keeping applications that are critical for the business in the source environment. This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.
### Retiring
>Retiring is the process of removing applications that are no longer needed.



# The six pillars of the AWS Well-Architected Framework:
1. Operational excellence
2. Security
3. Reliability
4. Performance efficiency
5. Cost optimization
6. Sustainability
# Six advantages of cloud computing:
-Trade upfront expense for variable expense.
- Benefit from massive economies of scale.
- Stop guessing capacity.
- Increase speed and agility.
- Stop spending money running and maintaining data centers.
-   Go global in minutes.

# AWS Elastic Beanstalk
> AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.

## usecase
1. Quickly launch web applications
> Deploy scalable web applications in minutes without the complexity of provisioning and managing underlying infrastructure.
2.Create mobile API backends for your applications
>Use your favorite programming language to build mobile API backends, and Elastic Beanstalk will manage patches and updates.
3. Replatform critical business applications
>Migrate stateful applications off legacy infrastructure to Elastic Beanstalk and connect securely to your private network.



### deployment strategy
**All at Once Deployments**
Elastic Beanstalk environment uses all-at-once deployments if it is created with a different client (API, SDK, or AWS CLI).
All at Once deployments perform an in-place deployment on all instances at the same time.
All at Once deployments are simple and fast, however, it would lead to downtime and the rollback would take time in case of any issues.
**Rolling Deployments**
Elastic Beanstalk environment uses rolling deployments if it is created with console or EB CLI.
Elastic Beanstalk splits the environment’s EC2 instances into batches and deploys the new version of the application on the existing instance one batch at a time, leaving the rest of the instances in the environment running the old version.
During a rolling deployment, part of the instances serves requests with the old version of the application, while instances in completed batches serve other requests with the new version.
Elastic Beanstalk performs the rolling deployments as
When processing a batch, detaches all instances in the batch from the load balancer, deploys the new application version, and then reattaches the instances.
To avoid any connection issues when the instances are detached, connection draining can be enabled on the load balancer
After reattaching the instances in a batch to the load balancer, ELB waits until they pass a minimum number of health checks (the Healthy check count threshold value), and then starts routing traffic to them.
Elastic Beanstalk waits until all instances in a batch are healthy before moving on to the next batch.
When all instances in the batch pass enough health checks to be considered healthy by ELB, the batch is complete.
If a batch of instances does not become healthy within the command timeout, the deployment fails.
If a deployment fails after one or more batches are completed successfully, the completed batches run the new version of the application while any pending batches continue to run the old version.
If the instances are terminated from the failed deployment, Elastic Beanstalk replaces them with instances running the application version from the most recent successful deployment.
**Rolling with Additional Batch Deployments**
Rolling with Additional Batch deployments is helpful when you need to maintain full capacity during deployments.
This deployment is similar to Rolling deployments, except they do not do an in-place deployment but a disposable one, launching a new batch of instances prior to taking any instances out of service
When the deployment completes, Elastic Beanstalk terminates the additional batch of instances.
Rolling with additional batch deployment does not impact the capacity and ensures full capacity during the deployment process.
**Immutable Deployments**
All at Once and Rolling deployment method updates existing instances.
If you need to ensure the application source is always deployed to new instances, instead of updating existing instances, the environment can be configured to use immutable updates for deployments.
Immutable updates are performed by launching a second Auto Scaling group is launched in the environment and the new version serves traffic alongside the old version until the new instances pass health checks.
Immutable deployments can prevent issues caused by partially completed rolling deployments. If the new instances don’t pass health checks, Elastic Beanstalk terminates them, leaving the original instances untouched.
**Blue Green Deployments**
Elastic Beanstalk performs an in-place update when application versions are updated, which may result in the application becoming unavailable to users for a short period of time.
Blue Green approach is suitable for deployments that depend on incompatible resource configuration changes or a new version that can’t run alongside the old version.
Elastic Beanstalk enables the Blue Green deployment through the Swap Environment URLs feature.
Blue Green deployment provides an almost zero downtime solution, where a new version is deployed to a separate environment, and then CNAMEs of the two environments are swapped to redirect traffic to the new version.
Blue/green deployments require that the environment runs independently of the production database i.e. not maintained by Elastic Beanstalk if your application uses one. Because if the environment has an RDS DB instance attached to it, the data will not transfer over to the second environment and will be lost if the original environment is terminated
Blue Green deployment entails a DNS change; hence, do not terminate the old environment until the DNS changes have been propagated and the old DNS records expire.
DNS servers do not necessarily clear old records from their cache based on the time to live (TTL) you set on the DNS records.


`hi`