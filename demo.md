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


