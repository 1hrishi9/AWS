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

type of bucket policies
:           principle -> user
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