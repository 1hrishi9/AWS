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