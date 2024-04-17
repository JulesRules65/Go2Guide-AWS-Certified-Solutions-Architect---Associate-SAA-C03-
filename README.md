# Go2Guide-AWS-Certified-Solutions-Architect--Associate-SAA-C03
Explore the ultimate companion for achieving your AWS Certified Solutions Architect Certification. This comprehensive guide is your go-to resource, meticulously curated with vital links to whitepapers, essential services, and handy cheat sheets tailored to each exam topic. Additionally, uncover invaluable exam tips meticulously crafted for mastering each service with confidence.

I'd like to start with some motivation: [Don't Shave That Yak!](https://seths.blog/2005/03/dont_shave_that/)
Don't give up when you don't understand a concept perfectly .. remember, doing it well now is much better than doing it perfectly later.


## Study Materials
[Udemy Course ($$$)](https://www.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03)

[Udemy Practice Exams ($$$)](https://www.udemy.com/course/practice-exams-aws-certified-solutions-architect-associate)

[Cloud Guru Course with Hands-On labs ($$$)](https://learn.acloud.guru/course/certified-solutions-architect-associate/overview )

[3D-Role-Playing-Game ($$$)](https://aws.amazon.com/training/digital/aws-cloud-quest)

[AWS Training live on Twitch (free)](https://aws.amazon.com/training/twitch/)

Good old Youtube (free):
- https://www.youtube.com/@CloudVikings
- https://www.youtube.com/@BeABetterDev
- https://www.youtube.com/@GoCloudArchitects


## Important links
[Exam Guide + Sample Questions](https://aws.amazon.com/certification/certified-solutions-architect-associate)

[AWS Certification Paths](https://d1.awsstatic.com/training-and-certification/docs/AWS_certification_paths.pdf)

[AWS Whitepaper & Guides](https://aws.amazon.com/whitepapers)

[AWS Architecture Center](https://aws.amazon.com/architecture)

[AWS Well-Architected Framework](https://docs.aws.amazon.com/pdfs/wellarchitected/latest/framework/wellarchitected-framework.pdf)

[AWS Global Infrastructure](https://aws.amazon.com/de/about-aws/global-infrastructure)

[Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model)

[Serverless on AWS](https://aws.amazon.com/serverless)

[AWS Support Plans](https://aws.amazon.com/premiumsupport/plans)

[AWS Saving Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)

[Comparison of AWS Services](https://tutorialsdojo.com/comparison-of-aws-services/)

[AWS Services Cheat Sheet](https://digitalcloud.training/category/aws-cheat-sheets/aws-solutions-architect-associate)

[AWS Networking Fundamentals](https://www.youtube.com/watch?v=hiKPPy584Mg&ab_channel=AmazonWebServices)


## Get an extra 30 minutes for AWS Certification exams
A 30-minute exam extension is available upon request to non-native English speakers when taking an exam in English. 
The accommodation, “ESL +30,” only needs to be requested once, prior to registering for an exam. It will apply to all future exam registrations with all test delivery providers. To request this accommodation, follow these steps:

- Sign in to https://aws.training/Certification
- Select the **Go to your Account** button. 
- Select the **Request Exam Accommodations** button, followed by **Request Accommodation**.
- Using the Accommodation Type dropdown, **select ESL +30 MINUTES**.
- Select the **Create** button.


## Rules/Tips for Remote AWS Exams
[Pearson Vue System Test](https://home.pearsonvue.com/Clients/Amazon-Web-Services/Online-Proctored.aspx)
- You can't wear hats or hoodies
- Stay within webcam view
- It's not allowed to enter or leave the testing environment
- Don't mumble, talk around, or mouth anything as you take the exam
- Drinks (better in an unlabeled container) are allowed, but no food or smoking etc.
- Clean up your desk - only laptop, power cable, maybe a mouse and your water bottle is okay .. that's it

## Some Notes and common Exam Scenarios
you should be able to differentiate services that belong to one category from another. Common comparisons include:
- EC2 vs ECS vs Lambda
- S3 vs EBS vs EFS
- CloudFormation vs OpsWorks vs Elastic Beanstalk
- SQS vs SNS vs SES vs MQ
- Security Group vs nACLs
- The different S3 storage types vs Glacier
- RDS vs DynamoDB vs Elasticache
- RDS engines vs Aurora

**Domain 1: Design Resilient Architectures**
| Scenario | Solution |
| -------- | -------- |
| Set up asynchronous data replication to another RDS DB instance hosted in another AWS Region | Create a Read Replica |
| A parallel file system for “hot” (frequently accessed) data | Amazon FSx For Lustre |
| Implement synchronous data replication across Availability Zones with automatic failover in Amazon RDS. | Enable Multi-AZ deployment in Amazon RDS. |
| Needs a storage service to host “cold” (infrequently accessed) data | Amazon S3 Glacier |
| Set up a relational database and a disaster recovery plan with an RPO of 1 second and RTO of less than 1 minute. | Use Amazon Aurora Global Database. |
| Monitor database metrics and send email notifications if a specific threshold has been breached. | Create an SNS topic and add the topic in the CloudWatch alarm. |
| Set up a DNS failover to a static website. | Use Route 53 with the failover option to a static S3 website bucket or CloudFront distribution. |
| Implement an automated backup for all the EBS Volumes. | Use Amazon Data Lifecycle Manager to automate the creation of EBS snapshots. |
| Monitor the available swap space of your EC2 instances | Install the CloudWatch agent and monitor the SwapUtilization metric. |
| Implement a 90-day backup retention policy on Amazon Aurora. | Use AWS Backup |

**Domain 2: Design High-Performing Architectures**
| Scenario | Solution |
| -------- | -------- |
| Implement a fanout messaging. | Create an SNS topic with a message filtering policy and configure multiple SQS queues to subscribe to the topic. |
| A database that has a read replication latency of less than 1 second. | Use Amazon Aurora with cross-region replicas. |
| A specific type of Elastic Load Balancer that uses UDP as the protocol for communication between clients and thousands of game servers around the world. | Use Network Load Balancer for TCP/UDP protocols. |
| Monitor the memory and disk space utilization of an EC2 instance. | Install Amazon CloudWatch agent on the instance. |
| Retrieve a subset of data from a large CSV file stored in the S3 bucket. | Perform an S3 Select operation based on the bucket’s name and object’s key. |
| Upload 1 TB file to an S3 bucket. | Use Amazon S3 multipart upload API to upload large objects in parts. |
| Improve the performance of the application by reducing the response times from milliseconds to microseconds. | Use Amazon DynamoDB Accelerator (DAX) |
| Retrieve the instance ID, public keys, and public IP address of an EC2 instance. | Access the URL: http://169.254.169.254/latest/meta-data/ using the EC2 instance. |
| Route the internet traffic to the resources based on the location of the user. | Use Route 53 Geolocation Routing policy. |
| A fully managed ETL (extract, transform, and load) service provided by Amazon Web Services. | AWS Glue |
| A fully managed, petabyte-scale data warehouse service. | Amazon Redshift |

**Domain 3: Design Secure Applications and Architectures**
| Scenario | Solution |
| -------- | -------- |
| Encrypt EBS volumes restored from the unencrypted EBS snapshots | Copy the snapshot and enable encryption with a new symmetric CMK while creating an EBS volume using the snapshot. |
| Limit the maximum number of requests from a single IP address. | Create a rate-based rule in AWS WAF and set the rate limit. |
| Grant the bucket owner full access to all uploaded objects in the S3 bucket. | Create a bucket policy that requires users to set the object’s ACL to bucket-owner-full-control. |
| Protect objects in the S3 bucket from accidental deletion or overwrite. | Enable versioning and MFA delete. |
| Access resources on both on-premises and AWS using on-premises credentials that are stored in Active Directory. | Set up SAML 2.0-Based Federation by using a Microsoft Active Directory Federation Service. |
| Secure the sensitive data stored in EBS volumes | Enable EBS Encryption |
| Ensure that the data-in-transit and data-at-rest of the Amazon S3 bucket is always encrypted | Enable Amazon S3 Server-Side or use Client-Side Encryption |
| Secure the web application by allowing multiple domains to serve SSL traffic over the same IP address. | Use AWS Certificate Manager to generate an SSL certificate. Associate the certificate to the CloudFront distribution and enable Server Name Indication (SNI). |
| Control the access for several S3 buckets by using a gateway endpoint to allow access to trusted buckets. | Create an endpoint policy for trusted S3 buckets. |
| Enforce strict compliance by tracking all the configuration changes made to any AWS services. | Set up a rule in AWS Config to identify compliant and non-compliant services. |
| Provide short-lived access tokens that act as temporary security credentials to allow access to AWS resources. | Use AWS Security Token Service |
| Encrypt and rotate all the database credentials, API keys, and other secrets on a regular basis. | Use AWS Secrets Manager and enable automatic rotation of credentials. |

**Domain 4: Design Cost-Optimized Architectures**
| Scenario | Solution |
| -------- | -------- |
| A cost-effective solution for over-provisioning of resources. | Configure a target tracking scaling in ASG. |
| The application data is stored in a tape backup solution. The backup data must be preserved for up to 10 years. | Use AWS Storage Gateway to backup the data directly to Amazon S3 Glacier Deep Archive. |
| Accelerate the transfer of historical records from on-premises to AWS over the Internet in a cost-effective manner. | Use AWS DataSync and select Amazon S3 Glacier Deep Archive as the destination. |
| Globally deliver the static contents and media files to customers around the world with low latency. | Store the files in Amazon S3 and create a CloudFront distribution. Select the S3 bucket as the origin. |
| An application must be hosted to two EC2 instances and should continuously run for three years. The CPU utilization of the EC2 instances is expected to be stable and predictable. | Deploy the application to a Reserved instance. |
| Implement a cost-effective solution for S3 objects that are accessed less frequently. | Create an Amazon S3 lifecyle policy to move the objects to Amazon S3 Standard-IA. |
| Minimize the data transfer costs between two EC2 instances. | Deploy the EC2 instances in the same Region. |
| Import the SSL/TLS certificate of the application. | Import the certificate into AWS Certificate Manager or upload it to AWS IAM. |


## In-Scope AWS Services
This list is non-exhaustive and is subject to change. AWS offerings appear in categories that align with the offerings’ primary functions
**Analytics:**
- Amazon Athena
- AWS Data Exchange
- AWS Data Pipeline
- Amazon EMR
- AWS Glue
- Amazon Kinesis
- AWS Lake Formation
- Amazon Managed Streaming for Apache Kafka (Amazon MSK)
- Amazon OpenSearch Service
- Amazon QuickSight
- Amazon Redshift

**Application Integration:**
- Amazon AppFlow
- AWS AppSync
- Amazon EventBridge
- Amazon MQ
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)
- AWS Step Functions

**AWS Cost Management:**
- AWS Budgets
- AWS Cost and Usage Report
- AWS Cost Explorer
- Savings Plans

**Compute:**
- AWS Batch
- Amazon EC2
- Amazon EC2 Auto Scaling
- AWS Elastic Beanstalk
- AWS Outposts
- AWS Serverless Application Repository
- VMware Cloud on AWS
- AWS Wavelength

**Containers:**
- Amazon ECS Anywhere
- Amazon EKS Anywhere
- Amazon EKS Distro
- Amazon Elastic Container Registry (Amazon ECR)
- Amazon Elastic Container Service (Amazon ECS)
- Amazon Elastic Kubernetes Service (Amazon EKS)

**Database:**
- Amazon Aurora
- Amazon Aurora Serverless
- Amazon DocumentDB (with MongoDB compatibility)
- Amazon DynamoDB
- Amazon ElastiCache
- Amazon Keyspaces (for Apache Cassandra)
- Amazon Neptune
- Amazon Quantum Ledger Database (Amazon QLDB)
- Amazon RDS
- Amazon Redshift

**Developer Tools:**
- AWS X-Ray

**Front-End Web and Mobile:**
- AWS Amplify
- Amazon API Gateway
- AWS Device Farm
- Amazon Pinpoint

**Machine Learning:**
- Amazon Comprehend
- Amazon Forecast
- Amazon Fraud Detector
- Amazon Kendra
- Amazon Lex
- Amazon Polly
- Amazon Rekognition
- Amazon SageMaker
- Amazon Textract
- Amazon Transcribe
- Amazon Translate

**Management and Governance:**
- AWS Auto Scaling
- AWS CloudFormation
- AWS CloudTrail
- Amazon CloudWatch
- AWS Command Line Interface (AWS CLI)
- AWS Compute Optimizer
- AWS Config
- AWS Control Tower
- AWS Health Dashboard
- AWS License Manager
- Amazon Managed Grafana
- Amazon Managed Service for Prometheus
- AWS Management Console
- AWS Organizations
- AWS Proton
- AWS Service Catalog
- AWS Systems Manager
- AWS Trusted Advisor
- AWS Well-Architected Tool

**Media Services:**
- Amazon Elastic Transcoder
- Amazon Kinesis Video Streams

**Migration and Transfer:**
- AWS Application Discovery Service
- AWS Application Migration Service
- AWS Database Migration Service (AWS DMS)
- AWS DataSync
- AWS Migration Hub
- AWS Snow Family
- AWS Transfer Family

**Networking and Content Delivery:**
- AWS Client VPN
- Amazon CloudFront
- AWS Direct Connect
- Elastic Load Balancing (ELB)
- AWS Global Accelerator
- AWS PrivateLink
- Amazon Route 53
- AWS Site-to-Site VPN
- AWS Transit Gateway
- Amazon VPC

**Security, Identity, and Compliance:**
- AWS Artifact
- AWS Audit Manager
- AWS Certificate Manager (ACM)
- AWS CloudHSM
- Amazon Cognito
- Amazon Detective
- AWS Directory Service
- AWS Firewall Manager
- Amazon GuardDuty
- AWS IAM Identity Center (AWS Single Sign-On)
- AWS Identity and Access Management (IAM)
- Amazon Inspector
- AWS Key Management Service (AWS KMS)
- Amazon Macie
- AWS Network Firewall
- AWS Resource Access Manager (AWS RAM)
- AWS Secrets Manager
- AWS Security Hub
- AWS Shield
- AWS WAF

**Serverless:**
- AWS AppSync
- AWS Fargate
- AWS Lambda

**Storage:**
- AWS Backup
- Amazon Elastic Block Store (Amazon EBS)
- Amazon Elastic File System (Amazon EFS)
- Amazon FSx (for all types)
- Amazon S3
- Amazon S3 Glacier
- AWS Storage Gateway

## Exam Tips

### AWS Fundamentals
#### Building Blocks of AWS
- **A Region** is a physical location in the world that consists of two or more Availability Zones (AZs)
- **An AZ** is one or more discrete data centers - each with redundant power, networking, and connectivity - housed in seperate facilities
- **Edge locations** are endpoints for AWS that are used for caching content. Typically, this consists of CloudFront, Amazon's content delivery network (CDN)

#### Who Owns What in the Cloud?
- Can you do this yourself in the AWS Management Console?
  - **If yes, you are likely responsible** - Security Groups, IAM users, patching EC2 operating systems, patching databases running on EC2 ...
  - **If not, AWS is likely responsible** - Management of data centers, security cameras, cabling, patching RDS operating systems ...
  - **Encryption is a shared responsibility**

#### Compute, Storage, Databases, and Networking
- **Compute:** EC2, Lambda, Elastic Beanstalk
- **Storage:** S3, EBS, EFS, FSx, Storage Gateway
- **Databases:** RDS, DynamoDB, Redshift
- **Networking:** VPCs, Direct Connect, Route 53, API Gateway, AWS Global Accelerator


### Identity and Access Management (IAM)
#### Securing the Root Account
- **Enable multi-factor authentication** on the root account and avoid using it for administrative tasks
- **Create an admin group** for your administrators & assign appropriate permissions to this group using IAM Policy Documents.
- Finally **add specific users to admin group**

#### IAM Policy in JSON format
You might give some users administrative permissions to perform all actions in IAM, including managing passwords, access keys, MFA devices, and user certificates. The following example policy grants these permissions.
```
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "iam:*",
    "Resource": "*"
  }
}
```

#### Permanent IAM Credentials
- **IAM is universal/global:** It does'nt apply to regions at this time
- **The Root Account:** This is the account created when you first set up ypur AWS account and it has complete admin access - **do not** use it to log in day to day
- **New Users:** No Permission when first created
- **Access key ID and secret access keys are not the same as usernames and passwords:** Use them to access AWS via the APIs and Command Line
  - **You only get to view these once:** If you lose them, you have to regenerate them - save them in a secure location
- **Always set up password rotations:** Create and customize your own password rotation policies
- **IAM Federation:** When you log on to your PC (usually using Microsoft AD [now Entra ID]), you can use the same credentials to log in to AWS. Uses the SAML standard, which is Active Directory

#### Short-term security credentials
- **AWS Security Token Service (STS)** provides a mechanism for issuing existing users with temporary credentials that grant access to additional resources.
- STS credentials are typically used to delegate access to the IAM roles in your AWS account

### Simple Storage Service (S3)
- **Object based storage:** Allows you to upload files (objects)
- **Files can be from 0 bytes to 5 TB**
- **Only up to 160 GB using AWS Console:** To upload files in excess of this requires the use of S3 multipart upload or via CLI
- **Not OS or DB Storage:** Not suitable to install an os or run a database on
- **Unlimited Storage:** The total volume of data and the number of objects you can store is unlimited

#### Files Stored in Buckets
- S3 is a **universal namespace:** You are not allowed to have the same bucket name as other people
```
https://bucket-name.s3.Region.amazonaws.com/key-name
```
- Note: Successful CLI or API object uploads will generate an HTTP 200 status code

#### S3 Object Tips
- **Key:** The object name (e.g. test.png)
- **Value:** The data itself, which is made up of a sequence of bytes
- **Version ID:** Allows you to store multiple versions of the same object
- **Metadata:** Data about the data you are storing (e.g. content-type, last-modified)
- The **S3 sync command** uses the CopyObject APIs to copy objects between Amazon S3 buckets
  - The sync command on a versioned bucket copies only the current version of the object

#### Securing Your Bucket with S3
- **Buckets are private by default:** On creation the bucket is private including all objects within it. You need to specifically allow public access on both the bucket **and** its objects
- **Object Access Control List's (ACLs):** To make individual objects public
- **Bucket policies:** make entire buckets public using bucket policies (Best Practice)

#### Hosting a Static Website
- You can use s3 to host **static content only** (not dynamic)
- **Automatic scaling:** S3 scales automatically with demand

#### Versioning Objects
- All Versions of an object are stored in S3. This includes all writes and even if you delete an objects
- Can be a great backup tool
- Once enbaled, versioning cannot be disabled - only suspended
- Can be integrated with lifecycle rules
- Can support MFA

#### Storage Classes
- Head over to [S3 Storage Classes](https://aws.amazon.com/de/s3/storage-classes/)

#### Lifecycle Management with S3
An S3 Lifecycle configuration is an XML file that consists of a set of rules with predefined actions that you want Amazon S3 to perform on objects during their lifetime.
- [Supported lifecycle transitions](https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-transition-general-considerations.html) between storage classes 
- Automates moving your objects between different storage tiers
- Can be used in conjunction with versioning
- Can be applied to current versions and previous versions

#### S3 Object Lock and Glacier Vault Lock
- Use **S3 Object Lock** to store objects using a write once, read many (WORM) model
  - Object Lock can be on **individual objects** or **applied across the bucket** as a whole
  - Object Lock comes in two modes: **governance mode** and **compliance mode**
    - governance mode: users can't overwrite or delete an object version or alter its lock settings unless they have special permissions
    - compliance mode: a protected object version can't be overwritten or deleted by any user, including the root user in your AWS account
- **S3 Glacier Vault Lock** allows you to easily deploy and enforce compliance controls for individual S3 Glacier vaults with a vault lock policy
  - Specify controls, such as WORM, in a vault lock policy and lock the policy from future edits
  - Once locked, the policy can no longer be changed

#### Encrypting S3 Objects
- **Encryption in Transit** (Sending the data to S3)
  - SSL/TLS
  - HTTPS
- **Encryption at Rest** (Server-side-encryption)
  - all new object uploads to Amazon S3 are automatically encrypted at no additional cost and with no impact on performance
  - SSE-S3 (AES 256-bit)
  - SSE-KMS
    - This offers more control and audit trails over the keys used to encrypt your data. With SSE-KMS, you can either use a default service-managed key for encryption or specify a customer-managed key
  - SSE-C
- **Client-Side Encryption**
  - You encrypt the files yourself before you upload them to S3
- **Enforcing Encryption with a Bucket Policy**
  - A bucket policy can deny all PUT requests that don't include the **x-amz-server-side-encryption** parameter in the request header

#### Optimizing S3 Performance
- **Prefix:** e.g. mybucketname/folder1/subfolder1/myfile.jpg >>> /folder1/subfolder1 is prefix
- You can achieve a high number of requests: **3.500 PUT/COPY/POST/DELETE** and **5.500 GET/HEAD** requests per second, per prefix
- Get better performance by spreading your reads across **different prefixes**
  - There are no limits to the number of prefixes in a bucket. You can increase your read or write performance by using parallelization.
    - For example, if you create 10 prefixes in an Amazon S3 bucket to parallelize reads, you could scale your read performance to 55,000 read requests per second.
    - Similarly, you can scale write operations by writing to multiple prefixes.
- **SSE-KMS built-in limits**
  - Region-specific, however it's either 5.500, 10.000 or 30.000 requests per second
  - Uploading/downloading will count toward the KMS quota
  - Currently you cannot request a quota increasy for KMS
- Use **multipart uploads** to increase performance when uploading files to S3 (for any file over 100 MB)
- Use **S3 byte-range fetches** to increase performance when downloading files to S3
- Use **Transfer Acceleration** to transfer from gigabytes to terabytes of data on a regular basis across continents
  - you pay only for transfers that are accelerated

#### Backing up Data with S3 Replication
- You can replicate objects from one bucket to another
- Objects in an existing bucket are not replicated automatically
- Delete markers are not replicated by default


### Elastic Compute Cloud (EC2)
EC2 is like a VM, hosted in AWS instead of your own data center
- Select capacity you need **right now**
- Grow and shrink when you need
- Pay for what you use
- Wait minutes, not months

#### EC2 Instance Pricing Options
**On-Demand**
- Pay by the hour or the second, depending on the type of instance you run
- Great for flexibility
  
**Spot**
- Purchase unused capacity at a discount of up to 90% compared to On-Demand pricing
- Prices fluctate with supply and demand.
- Great for workloads that can be interrupted and where you don't need persistent storage
- You can block instances from terminating by using **Spot block**
- A **Spot Fleet** is a collection of Spot Instances, and optionally, On-Demand Instances

**Reserved**
- Reserved capacity for 1 **or** 3 years
- Up to 72% discount on the hourly charge.
- Great if you have known, fixed requirements
- to stop incurring charges and save money on the EC2 instances you can sell the reserved instances on the Reserved Instance Marketplace.

**Dedicated Host**
- Most expensive option
- A physical EC2 server dedicated for your use
- Great if you have serverbound licenses to reuse or compliance requirements
- Note: Any question that talks about special licensing requirements

#### EC2 Instance Store
- Provides temporary block-level storage for your instance
- This storage is located on disks that are physically attached to the host computer

#### AWS Command Line Interface (CLI)
- **Least Privilege:** Always give your users the minimum amount of access required to do their job
- **Use Groups:** Create IAM Groups and assign your users to groups. Group permissions are assigned using Policiy documents and users of that group will automatically inherit the permissions of the group
- **Secret Access Key:** Each developer should have their own access key ID and secret access key. Just like passwords, they should not be shared
- **Supports Linux, Windows, and macOS:** You can install the CLI on Mac, Linux, or Windows. You can also use it on EC2 instances

#### Using Roles
- Roles are the preferred Option from a security perspective
- Roles provide access without the use of access key IDs and secret access keys
- Policies control a role's permissions
- Updating a policy attached to a role will take immediate effect
- Attach and detach roles to running EC2 instances without having to stop or terminate these instances

#### Security Groups
You can change the security groups for an instance when the instance is in the running or stopped state
- Changes to security groups take effect immediately
- You can have any number of EC2 instances within a security group
- You can have multiple security groups attached to EC2 instances (up to 5)
- ALL inbound traffic is blocked by default
- All outbound traffic is allowed

#### User Data and Metadata
- User data are simply bootstrap scripts: **a script that runs when the EC2-Instance first runs**
  - It passes user data to the instance and can be used to install applications (like web servers and databases), as well as do updates and more
  - By default, user data **runs only during the boot cycle** when you first launch an instance
  - By default, scripts entered as user data are **executed with root user** privileges
- Metadata is data about your EC2 instances
  - You can use bootstrap scripts (user data) to access metadata

Bootstrap script example:
```
#!/bin/bash
yum update -y
amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
yum install -y httpd mariadb-server
systemctl start httpd
systemctl enable httpd
usermod -a -G apache ec2-user
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
```

#### EC2 Network Cards
- **Elastic Network Interface (ENI)** is a logical networking component in a VPC that represents a virtual network card
  - For basic networking
- **Elastic Network Adaptor (ENA)** is a custom network interface optimized to deliver high throughput and packet per second (PPS) performance, and consistently low latencies on EC2 instances
  - For when you need speeds between 10 Gbps and 100 Gbps
  - Anywhere you need reliable, high throughput
- **Elastic Fabric Adapter (EFA)** is a network device that you can attach to your Amazon EC2 instance to accelerate High Performance Computing (HPC) and machine learning applications
  - Or if you need to do an OS-bypass.
  - Choose EFA if you see a scenario question mentioning HPC or ML

#### EC2 Fleet
- EC2 Fleet is a powerful service that simplifies the process of provisioning and managing multiple EC2 instances
- The fleet request must include a launch template that defines the information that the fleet needs to launch an instance
- In a single API call, a fleet can launch multiple instance types across multiple AZs, using the Spot Instance, On-Demand Instance, Reserved Instance, and Savings Plan purchasing options together

#### Types of Placement Groups
To meet the needs of your workload, you can launch a group of interdependent EC2 instances into a placement group to influence their placement
- **Cluster Placement Groups**
  - Low network latency, high network throughput
  - **can't** span multiple AZs
  - AWS recommends homogenous instances
- **Spread Placement Groups**
  - Individual critical EC2 instances
  - can span multiple AZs
- **Partition Placement Groups**
  - Multiple EC2 instances: HDFS, HBase, and Cassandra
  - can span multiple AZs
  - can't be merged
- Only certain types of instances can be launched in a placement group (compute, GPU, memory and storage optimized)
- You can move an existing instance into a placement group
  - instance must be stopped
  - move or remove via CLI or SDK, but you can't do it via the console yet

#### VMware Cloud (Deploy vCenter on AWS)
- this is basically the perfect solution for extending your private VMware cloud onto the AWS public cloud
- E.g. cloud migration or doing disaster recovery using AWS with all the native tools that come with VMware and within vCenter itself

#### AWS Outposts
With that you can extend AWS to your data center - just think of AWS Outposts as bringing AWS to you
- **AWS Outpost racks**
  - this is for large deployments, so these are 42U form factor racks that will go inside a data center
- **AWS Outpost servers**
  - for smaller deployments, so this will be things like putting in a 1U server inside a retail shop, for example

#### Amazon Machine Images (AMI):
- An AMI is just a blueprint for an EC2 instance and provides the information required to launch an instance
- Launch multiple instances from one AMI when you need same configuration
- You can copy an AMI within the same AWS Region or to different AWS Regions
  - create EBS Snapshot from instance >> create AMI from Snapshot >> copy AMI into preferred AWS Region
    - When the new AMI is copied from Region A into Region B, it automatically creates a snapshot in Region B because AMIs are based on the underlying snapshots. Further, an instance is created from this AMI in Region B. Hence, **we have 1 Amazon EC2 instance, 1 AMI and 1 snapshot in Region B**

### Elastic Block Storage (EBS)
- Provides scalable, high-performance block storage resources that can be used with Amazon EC2 instances.
- You can use **Amazon Data Lifecycle Manager** to automate the creation, retention, and deletion of EBS snapshots and EBS-backed AMIs.
  
#### SSD Volumes
- gp2: General purpose SSD
  - for boot disks and general applications
  - up to 16.000 IOPS per volume
    
- gp3: Provisioned IOPS SSD
  - for high performance applications
  - predictable 3.000 IOPS baseline performance and 125 MiB/s regardless of volume size
    
- io1: Provisioned IOPS SSD
  - for OLTP and latency-sensitive applications
  - 50 IOPS/GiB
  - up to 64.000 IOPS per volume
  - high performance
    
- io2: Provisioned IOPS SSD
  - for OLTP and latency-sensitive applications
  - 500 IOPS/GiB
  - up to 64.000 IOPS per volume
  - high performance and most expensive
    
- io2 Block Express:
  - is the highest-performance SSD volume
  - designed for business-critical latency-sensitive transactional workloads.

#### HDD Volumes
- st1: Throughput Optimized HDD
  - for big data, data warehouse, ETL
  - max throughput is 500 MB/s per volume
  - not a boot volume
    
- sc1: Cold HDD
  - for less frequently accessed data
  - max throughput of 250 MB/s per volume
  - not a boot volume
  - lowest cost

#### Volumes and Snapshots
- Volumes exist on EBS, whereas snapshots are stored in S3 Buckets
- Snapshots are point-in-time photographs of volumes and are incremental in nature
- Snapshots will take some time to create - for consistent snapshots, stop the instance and detach the volume
- Snapshots can be shared between AWS accounts as well as between regions - first you need to copy that snapshot to the target region
- Resize EBS Volumes on the fly as well as changing the volume types

#### Protecting EBS Volumes with encryption
- **Data at rest** is encrypted inside the volume
- All snapshots are encrypted
- All the data **in flight** moving between the instance and the volume is encrypted
- All volumes created from the snapshot are encrypted
- To encrypt volumes:
  - **Create a snapshot** of the uncrypted root device volume
  - **Create a copy** of the snapshot and select the encrypt option
  - **Create an AMI** from the encrypted snapshot
  - Use that AMI to **launch new encrypted instances**

#### EC2 Hibernation
- Preserves the in-memory RAM on persistent storage (EBS)
- **Much faster to boot up** because you do not need to reload the operating system
- Instance RAM must be less than 150 GB
- Instance families include C3, C4, C5, M3, M4, M5, R3, R4 and R5
- Available for Windows, Amazon Linux 2 AMI, and Ubuntu
- Instances can't be hibernated for more than **60 days**
- Available for On-Demand instances and Reserved Instances

#### EBS vs. Instance Store
- Instance store volumes are sometimes called ephemeral/short-lived storage
- Instance store volumes cannot be stopped. If underlying host fails you will loose your data
- EBS-backed instances can be stoppped. You will not loose data
- both EBS and instance store can be rebooted without loosing data
- By default both root volumes will be deleted on termination
  - with EBS volumes you can tell AWS to keep the root device volume


### Elastic File System (EFS)
Highly scalable shared storage using Network File Sharing. Distributed, highly resilient storage for Linux instances and Linux-based applications
- Supports the Network File System version 4 (NFSv4) protocol
- Only pay for the storage you use (no pre-provisioning required)
- Can scale up to petabytes
- Can support thousands of concurrent NFS connections
- Data is stored across multiple AZs within a region
- Read-after-write consistency

#### EFS Performance modes
- **General Purpose mode** has the lowest per-operation latency and is the default performance mode for file systems
- **Max I/O mode** is a previous generation performance type that is designed for highly parallelized workloads
- Note: Due to the higher per-operation latencies with Max I/O, **it`s recommend using General Purpose performance mode for all file systems**

#### FSx
- Amazon FSx for Windows: When you need centralized storage for Windows-based applications, such as SharePoint, Microsoft SQL Server, Workspaces or any other native Microsoft application
- Amazon FSx for Lustre: When you need high-speed, high-capacity distributed storage. For applications that do high performance computing (HPC), financial modeling, etc. Remember that FSx for Lustre can store data directly on S3
  - FSx Lustre Scratch volumes are designed for immediate, high-speed data processing
  - FSx Lustre Persistent volumes ensure long-term data durability and accessibility

### Comparing all Storage Options
- S3: Used for serverless object storage
- Glacier: Used for archiving objects
- EFS: Network File System for Linux instances. Centralized storage solution across multiple Azs
- EBS Volumes: Persistent storage for EC2 instances
- Instance Store: Ephemeral storage for EC2 instances
- FSx for Windows: For Windows Instances - centralized storage solution across multiple AZs
- FSx for Lustre: File storage for high perfromance computing Linux file systems

### AWS Backup
- Consolidation: Use AWS Backup to back up AWS services such as EC2, EBS, EFS, Amazon FSx for Lustre, Amazon FSx for Windows File Server, and AWS Storage Gateway
- Organizations: You can use AWS Organizations in conjunction with AWS Backup to back up your different AWS services across multiple AWS accounts
- Benefits: Backup gives you centralized control, letting you automate your backups and define lifecycle policies for your data. You get better compliance, as you can enforce your backup policies, ensure your backups are encrypted, and audit them once complete


### Databases
####  Amazon Relational Database Service (RDS)
- **Database Types:** SQL Server, Oracle, MySQL, PostgreSQL, MariaDB, and Amazon Aurora
- RDS is for online transaction processing workloads: small transactions, like customer orders, banking transactions, booking systems
- RDS is not suitable for online analytics processing: better use Redshift for tasks like analyzing large amounts of data
- With **IAM database authentication**, you use an authentication token when you connect to your DB instance - by using a token, you can avoid placing a password in your code
- **Amazon RDS Proxy** effectively manages and optimizes database connections - It can enhance database scalability, reduce the load on the database, and mitigate performance issues during traffic spikes
- **Amazon RDS Custom for Oracle:** customers can customize their database server host and operating system and apply special patches or change database software settings

#### Read Replicas
- **Scaling read performance:** used for scaling and not for disaster recovery
- **Requires automatic backup:** automatic backup must be anabled in order to deploy a read replica
- **Multiple read replicas supported:** 5 read replicas for each DB instance allowed (MySQL, MariaDB, PostgreSQL, Oracle, SQL Server)

#### Multi-AZ vs. Read Replicas
**Multi-AZ follows synchronous replication** and spans at least two AZs within a single region. **Read replicas follow asynchronous replication** and can be within an AZ, Cross-AZ, or Cross-Region
- Multi-AZ
  - Exact copy of your production database in another AZ
  - Used for disaster recovery
  - In the event of a failure, RDS for MySQL will automatically failover to the standby instance in a different AZ
    - Amazon RDS simply flips the canonical name record (CNAME) for your DB instance to point at the standby, which is in turn promoted to become the new primary.
- Read Replica
  - A read only copy of your primary database in the same AZ, cross AZ or cross region
  - Used to increase or scale read performance
  - Great for read heavy workloads and takes the load off your primary database

#### Amazon Aurora DB Cluster
- Compatible with MySQL, PostgreSQL
- 2 copies of your data are contained in each AZ, with a minimum of 3 AZs >> 6 copies of your data
- Share Aurora snapshots with other aws accounts
- Aurora has automated backups turned on by default
- 3 types or read replicas: Aurora replicas (automated failover available), MySQL replicas, and PostgreSQL replicas
  - each Read Replica is associated with a priority tier (0-15)
  - In the event of a failover, Aurora will promote the Read Replica that has the highest priority (the lowest numbered tier)
  - If two or more Aurora Replicas share the same priority, then Amazon RDS promotes the replica that is largest in size (e.g.: Tier-1 (32 terabytes))

##### Auroroa Serverless
- Provides a relatively, simple, cost-effective option for infrequent, intermittent, or unpredictable workloads
- Think of Aurora Serverless in a scenario question where it's talking about setting up a serverless database

#### DynamoDB
- non-relational database, also known as NoSQL database, that uses a simple **key-value method** to store data
- Stored on SSD storage
- Spread across 3 geographically distinct data centers
- Eventually consistent reads (default)
- Strongly consistent reads
- Difference between eventually & strongly
  - Eventually: Consistency across all copies of data is usually reached within seconds. Best read perfromance
  - Strongly: returns a result that reflects all writes that received a successful response prior to the read

##### DynamoDB as a document database?
- A key-value store holds for each key a single value. Arguably, if the value can be an entire document, you can call this database a "document store".
- >> In this sense, DynamoDB is a document store

##### DynamoDB Transactions
- Provides ACID across one or more tables within a single AWS account and region
- Multiple "all-or-nothing" operations
- Financial transactions
- Fulfilling orders
- 3 options for reads: eventual consistency, strong consistency, and transactional
- 2 options for writes: standard and transactional
- up to 100 actions per transaction or 4MB of data

##### DynamoDB On-Demand Backup and Restore
- Full backups at any time
- Zero impact on table performance or availability
- Consistent within seconds and retained until deleted
- Operates within same region as the source table

##### DynamoDB Point-in-time Recovery (PITR)
- Protects against accidental writes or deletes
- Restore to any point in the last 35 days
- Incremental backup
- Not enabled by default
- Latest rstorable: 5 minutes in the past

##### DynamoDB Streams
- Time-ordered sequence of item-level changes in a table
- Stored for 24 hours
- Inserts, updates, and deletes
- combine with lambda functions for functionality like stored procedures

##### Global Tables (redundancy for DynamoDB)
- Globally distributed applications
- Based on DynamoDB streams (needs to be enabled before using global tables)
- Multi-region redundancy for disaster recovery or high availability
- No application rewrites
- replication latency under one second

#### Amazon DocumentDB
- Is the MongoDB-compatible database
- think Amazon DocumentDB when they talk about migrating MongoDB from on-premise to AWS

#### AWS Keyspaces
- For Cassandra cluster
- think AWS Keyspaces when they talk about migrating a big data Cassandra cluster to AWS

#### Neptune
- Is a graph database and handles graph queries
- think Neptune when they talk about graph database

#### Quantum ledger database
- is a fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log

#### Timestream
- stores a large amount of time-series data for analysis
- e.g. temperature sensors collecting temperature every second across thousands of locations


### Virtual Private Cloud (VPC) Networking
- Think of a VPC as a logical data center
- Consists of internet gateways, route tables, network access control lists, subnets, and security groups
- Includes a default security group >> **You can't delete this group**, however, you can change the group's rules
- To use private hosted zones in a VPC, you must set the following settings to true:
  - enableDnsHostnames
  - enableDnsSupport

#### VPC Sharing
- allows multiple AWS accounts to create their application resources into shared and centrally-managed Amazon VPCs
- the account that owns the VPC (owner) shares one or more subnets with other accounts (participants) that belong to the same organization from AWS Organizations
- Participants cannot view, modify, or delete resources that belong to other participants or the VPC owner
- This reduces the number of VPCs that you create and manage while using separate accounts for billing and access control

#### Subnet basics
- 1 subnet is always in 1 AZ
- Public subnet – The subnet has a direct route to an internet gateway. Resources in a public subnet can access the public internet
- Private subnet – The subnet does not have a direct route to an internet gateway. Resources in a private subnet require a NAT device to access the public internet
- Each subnet must be associated with a route table, which specifies the allowed routes for outbound traffic leaving the subnet
- Every subnet that you create is automatically associated with the main route table for the VPC

#### NAT Gateways
- Redundant inside the AZ
- Starts at 5 Gbps and scales currently to 45 Gbps
- No need to patch
- Not associated with Security Groups
- Automatically assigned a public IP address
- If resources in multiple Azs share a NAT gateway and one AZ is down, the respurces in the other AZ lose internet access
  - solve problem: one NAT gateway for each AZ - configure routing to ensure resources use the NAT in the same AZ

#### Security Groups
- Operates at instance level
- SG are stateful - if you send a request from your instance, the response traffic for that request is allowed to flow in regardless of inbound security group rules
  - responses to allowed inbound traffic are allowed to flow out, regardless of outbound rules
- Remember you can't delete default security group, however, you can change the group's rules

#### Network ACL
- Operates at subnet level
- Default Network ACLs: coming automatically with VPC - by default all outbound and inbound traffic **is allowed**
- Create custom network ACLs - by default all outbound and inbound traffic **is denied**
- Unlike SGs Network ACLs are stateless, responses to allowed inbound traffic are subject to the rules for outbound traffic (and vice versa)
- Each subnet in VPC must be associated with a network ACL - if not the subnet will automatically use default network ACL
- Block IP addresses using network ACLs, not Security groups
- You can associate a network ACL with multiple subnets; but a subnet with only one network ACL
- NACLs contain a numbered list of rules that are evaluated in order, starting with the lowest numbered rule
  - seperate inbound and outbound rules, each rule can either allow or deny traffic
- Each NACL also includes a rule whose rule number is an asterisk (*)
  - This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied
  - You can't modify or remove this rule.

NACL with asterix example
```
100 All Traffic Allow
200 All Traffic Deny
* All Traffic Deny
```

Good to know which common ports are used
| Port Number  | Usage |
| ------------- | ------------- |
| 20  | File Transfer Protocol (FTP)-Data Transfer  |
| 21  | File Transfer Protocol (FTP)-Command Control |
| 22  | Secure Shell (SSH)  |
| 25  | Simple Mail Transfer Protocol (SMTP) E-mail Routing  |
| 53  | Domain Name System (DNS) service  |
| 80  | Hypertext Transfer Protocol (HTTP)  |
| 443  | HTTP Secure (HTTPS) - HTTP over TLS/SSL  |

#### Direct Connect
- establish a dedicated network connection from your premises to AWS
- useful for high-throughput workloads (e.g. lots of network traffic)
- helpful when you need a stable and reliable secure connection
- **Use VPN** when you need to provide an **encrypted connection** between a data center and AWS Cloud
- To establish a private connection between your VPC and an API, you can create an **interface VPC endpoint**
  - Direct Connect provides three types of virtual interfaces: public, private, and transit

#### AWS Client VPN
- managed client-based VPN service that enables you to securely access your AWS resources or your on-premises network
- a secure and private connection with IPsec and TLS.

#### VPC Endpoints
- when you want to connect AWS services without leaving the Amazon internal network
- 2 types of VPC endpoints: Interface endpoints and gateway endpoints
- gateway endpoints: support s3 and DynamoDB

#### VPC Peering
- connect 1 VPC with another via a direct network route
- instances behave as if they were on the same private network
- peer VPC with other AWS accounts as well with other VPCs in the same account
- peering is in a star configuration (e.g. 1 central VPC peers with 4 others)
- you can peer between regions

#### AWS PrivateLink
- peering a vpc to hundreds, or thousands of customer VPCs
- Doesn't require VPC peering, no route tables, NAT gateways, internet gateways etc.
- Requires a Network Load Balancer on the service VPC and an ENI on the customer VPC

#### AWS Transit Gateway
- Connects your VPCs and on-premises networks through a central hub.
- Simplifying network topology
- Use route tables to limit how VPCs talk to one another
- Works with Direct Connect as well as VPN connections
- **Supports IP multicast** (not supported by any other service)

#### VPN Hub
- simplifying VPN network topology
- Use this approach if you have multiple branch offices and existing internet connections and would like to implement a convenient, potentially low-cost hub-and-spoke model for primary or backup connectivity between these remote offices

#### AWS Managed VPN
- lets you reuse existing VPN equipment and processes and also use existing internet connections

#### AWS Wavelength
- mobile edge computing
- 5G, increasing application speed at edge using mobile networks


### Route 53
- A reliable and cost-effective way to route end users to Internet applications
- difference between alias record and a CNAME
  - alias record: are unique to AWS. Translate your naked domain/subdomain name to a resource
  - CNAME: only allows you to translate a sub domain name from one to another
- always choose alias record over a CNAME when you see it in the exam

#### DNS Record Types
  - SOA Records
  - CNAME Records
  - NS Records
  - A Records

#### Routing Policies
- Simple Routing
  - you can only have one record with multiple IP addresses. And if you specify multiple values in a record, Route 53 returns all values to the user in a random order
  - not working with health checks
- Weighted Routing
  - If you see any scenario based questions that's talking about you want to direct a certain percentage of your traffic to a particular region or availability zone or whatever
- Latency-Based-Routing
  - if you see an exam question that's talking about latency
- Failover Routing
  - active passive setup. So our active might be in us-west-1 or us-west-2. And our passive setup might be an ap-souteast-2
  - And essentially fail over routing will have a health check on each region
  - And if we lose a region, it will switch from our active site to our passive site automatically
- Geolocation Routing
  - how can you make sure that a group of users in a particular location only go to a group of web servers in a particular location
- Geoproximity Routing
  - This basically lets Amazon Route 53 route your traffic to resources based on the geographic location of your users and resources
  - And to use geo proximity routing you must be using Route 53 Traffic Flow. Traffic Flow was that GUI where we can do all kinds of complicated routing architectures with Route 53
- Multivalue Answer Routing

#### Registering a Domain Name
- you can buy domain names directly with AWS
- can take up to 3 days to register

#### Health Checks
- You can set health checks on individual record sets
- If a record set fails a health check, it will be removed from route 53 unitl it passes the health check
- You can set SNS notifications to alert you about failed health checks


### Elastic Load Balencing (ELB)
- Elastic Load Balancing automatically distributes your incoming traffic across multiple targets
- You can use health checks to route your traffic to instances or targets that are healthy
- If you want your domain to point to a new ELB, then wait for the time-to-live (TTL) to expire. After that, the record will be updated and users get redirected to the new ELB
  - TTL: Your computer has cached the previous DNS request, but once the TTL has expired it will get the new address.

#### Application Load Balancer
- Layer 7
- intelligent load balencing
- Listeners: checks for connection requests from clients using the protocol and port you configure
- Rules: Determine how the load balancer routes requests to its registered targets. Consists of a priority, one or more actions, and one or more conditions
- Target Groups: each target group routes requests to one or more registered targets, such as EC2 instances, using the protocol and port number you specify
- Limitations: Application Load Balancers only support HTTP and HTTPS
- HTTPS: To use HTTPS listener, you must deploy at least one SSL/TLS server certificate.
- **Only** the ALB can support path-based and host-based routing

#### Network Load Balancer
- Layer 4
- use where you need extreme performance
- other use cases are where you need protocols not supported by ALB
- decrypt traffic, but you will need to install the certificate on the load balancer

#### Gateway Load Balancer
- Layer 3
- for inline virtual appliances

#### Classic Load Balancer
- Layer 4/7
- mostly used for test and dev
- 504 error means the gateway has timed out
- IPv4 address >> look for the X-Forwarded-For header

#### Sticky Sessions
- enable your users to stick to the same EC2 instance. Useful when storing information locally
- scenario-based question: you remove an EC2 instance from a pool. but the load balancer continues to direct traffic to that EC2 instance
  - solve this by disabling sticky sessions
- sticky sessions can be enabled for ALB as well but the traffic will be sent atthe target group level

#### Deregistration Delay/Connection Draining
- Enable Deregistration Delay
  - Keep existing connections open if the EC2 instance becomes unhealthy
- Disable Deregistration Delay
  - Do this if you want your LB to immediately close connections to the instances that are de.registering or have become unhealthy


### Monitoring
#### Cloud Watch
- is the main tool for anything alarm related
- Not everything should go through CloudWatch
- Know your intervals
  - standard metric is delivered every five minutes
  - detailed monitoring delivers data every one minute
- it's good to look up [available metrics(https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html)]

#### CloudWatch Logs
- is the place for logs. EC2, on-premise, RDS, Lambda and CloudTrail can all integrate with this service
- SQL and Logs >> CloudwatchLogs Insights
- Real time means Kinesis (big data section) >> dont pick CloudWatch Logs if it asks for a real-time logging service

#### Visualizing Data and Monitoring Containers at Scale
- **AWS Managed Grafana:** might be the best for visualization of container metrics
  - AWS-managed service for correlation and visualization of container or IoT metrics
- **AWS Managed Service for Prometheus**
  - use this service for any Kubernetes-based metrics monitoring at scale. Can be Amazon EKS cluster or self-managed cluster
- Both are managed services >> AWS handles scaling and high availability for you


### High Availability and Scaling
#### Auto Scaling
- is only for EC2
  - No other service can be scaled using Auto Scaling
- Whenever possible, **favor solutions that are predictive** rather than reactive or scheduled scaling
- Avoid long provisioning times by putting everything in an AMI (all dependencies and code). This is better than using user data whenever possible
  - good when you need those instances to respond to a workload that has just hit your architecture
- Make sure you're spreading your Auto Scaling groups over multiple AZs
- Steady state groups: is an auto scaling group that has min, max, and desired capacity. e.g. min 1, max 1, desired capacity 1. when the instance fails then auto scaling will automatically recover that architecture and provide a new instance
- Make sure you enable health checks from Load Balancers. If instances dont pass the health check they will be terminated by the auto scaling group. (that is not default behaviour)

##### Launch configuration
- Is an instance configuration template that an Auto Scaling group uses to launch Amazon EC2 instances
- If you only need to **launch a few instances with fixed settings**
- Include the ID of the AMI, the instance type, a key pair, one or more security groups, and a block device mapping
- It is **not possible** to modify a launch configuration once it is created

##### Launch template
- Is similar to a launch configuration, in that it specifies instance configuration information
- If you need to **launch an entire fleet of instances with consistent configurations**

##### Scaling strategies
**Dynamic Scaling:**
- Target Tracking Scaling — This automatically scales capacity to keep a metric like CPU utilization at or near a target value. This maintains optimal performance.
- Step Scaling — Increase or decrease capacity by a set amount based on CloudWatch alarms. For example, add 2 instances if CPU > 80% for 5 minutes.
- Simple/Step Scaling — Increase or decrease by a fixed number of instances. Simple but not as responsive as target tracking.

**Predictive Scaling:**
- Use machine learning to analyze historical data and forecast upcoming capacity needs. Scale ahead of predicted traffic changes.
- Great for cyclical changes like daily or seasonal patterns. Requires historical data.

**Scheduled Scaling:**
- Increase or decrease capacity on a set schedule, like weekdays vs weekends.
- Scale on a regular, fixed schedule for predictable fluctuations.

##### Auto Scaling Group cooldown
- After your Auto Scaling group launches or terminates instances, it waits for a cooldown period to end before any further scaling activities
- By default, this cooldown period is set to **300 seconds (5 minutes)**. If needed, you can update this after the group is created
- For the Default Termination Policy remember that the instance launched from the oldest launch configuration will be terminated first

#### Scaling Databases
- RDS has the most database scaling options
- Horizontal scaling is usually preferred over vertical
  - Read replicas are your friend >> especially for read-heavy workloads
- DynamoDB scaling comes down to access patterns
  - If we have that consistent access pattern, where it's predictable, where we gradually need to scale up and then scale those reads and writes back down, that's when we're going to want to select the auto scaling method
  - If we see a scenario given to us that has an unpredictable workload, where that access pattern spikes up and down and up and down, and we can't really predict what we need, then we want to pick that on-demand option


### Decoupling Workflows
#### Amazon SQS
- **SQS** can duplicate messages >> check for misconfigured visibility timeouts
- Queues aren't bi-directional: if you need communication to return to the instance that sent the message, you'll need a second queue
- It's important to understand the standard values for all of the SQS settings
- Messages stored in SQS can only persist **up to 14 days**
- If message ordering is important, make sure to select SQS FIFO queues
  - FIFO queues are designed to guarantee that messages are processed exactly once, in the exact order that they are sent
  - FIFO has a batch limit of 3,000 messages per second (300 API calls, each with a batch of 10 messages)
  - The name of a FIFO queue must end with the .fifo suffix

#### Amazon SNS
- proactive notifications: any time a question asks about email, text, or any type of push-based notification, think of SNS
- CloudWatch works perfectly with SNS: get notifications from a CloudWatch alarm via e-mail etc.

#### Amazon SES
- Simple Email Service is an Email platform that provides an easy, cost-effective way for you to send and receive email using your own email addresses and domains
- SES is NOT a supported destination for S3 event notifications

#### API Gateway
- throttles requests to your API using the token bucket algorithm, where a token counts for a request
- it acts as a secure front door to external communication coming into your environment

#### AWS Batch
- For long running, batched workloads: anything related to batch workloads that is > 15 minutes will likely involve AWS Batch
- Queued workloads: for any question about batch workloads requiring queues
- On-demand alternative to AWS Lambda: questions regarding an alternative solution to AWS Lambda due to runtime requirements

#### Amazon MQ
- Managed messaging broker: if there is any mention of a managed broker service
- RabbitMQ or ActiveMQ: when these two technologies are mentioned >> think Amazon MQ
- Specific messaging protocols: JMS, AMQP 0-9-1, AMQP 1.0, MQTT, OpenWire, or STOMP >> think Amazon MQ

#### Step Functions
- Serverless orchestration service
- Whenever the solution requires different states or logic during workflows (e.g. condition checks, failure catches, wait periods) >> Step Functions

Amazon App Flow
- AppFlow offers a fully managed service for easily automating the exchange of data between SaaS vendors and AWS services like Amazon S3. 
- You can transfer up to 100 gibibytes per flow
- Bi-directional: can be bi-directional in certain use cases (into or out of AWS services)
- good option to avoid the lambda timeouts (max execution timeout 15 min)


### Big Data
#### Redshift
- Redshift is a relational database, but no replacement for RDS in traditional applications
- Meant for large scale data warehousing and data analytics
- supports single-AZ and multi-AZs

#### Amazon Elastic MapReduce (Amazon EMR)
- managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark
- EMR also lets you transform and move large amounts of data into and out of other AWS data stores and databases, such as Amazon S3 and Amazon DynamoDB.
- is made up of EC2 instances: you can employ your standard EC2 instance cost-saving measures
- offers several built-in open-source tools to process vast amounts of big data

#### Amazon Kinesis
- only service with real-time response
- SQS and Kinesis can both be queues
  - SQS is easier and simpler
  - Kinesis is faster and can store data for up to a year
- understand the difference between Data Firehose and Data Streams
  - Data Firehose >> near realtime
  - Data Streams >> real-time
  - Video Streams >> more easily and securely stream video from connected devices to AWS for analytics, ML, playback, and other processing

#### Amazon Athena & AWS Glue
- Athena: Serverless SQL
  - makes it easy to analyze data directly in S3
  - build dashboards and visualizations for business intelligence needs using QuickSight
  - The Amazon Athena connector for Microsoft SQL Server enables Athena to run SQL queries on your data stored in Microsoft SQL Server using JDBC
- Glue: serverless ETL (Extract, transform, and load) service - can help create that schema for your data when paired with Athena
  - discover and connect to more than 70 diverse data sources and manage your data in a centralized data catalog
  - use AWS Glue to export the data from DynamoDB, transform the data, and then load the data back into DynamoDB


#### Quicksight
- QuickSight is your go-to tool for visualizing data
- It connects to your data in the cloud and combines data from many different sources

#### OpenSearch (ElasticSearch)
- OpenSearch is primarily used for analyzing log files and various documents, especially within an ETL process

#### Data Pipeline
- is a managed ETL service within AWS
- implement automated workflows for movement and transformation of your data
- integrates with storage services and compute services
- Data-driven and task-dependent ETL workloads are a perfect use case

#### Amazon Managed Streaming for Apache Kafka (MSK)
- Managed service for building and running Apache Kafka streaming applications
- The service handles control plane operations for you (creation, updating, and deletion)
- You manage data plane operations
- push broker logs to CloudWatch, S3, or Kinesis Data Firehose
- API calls are all logged to CloudTrail


### Serverless Architecture
An example for a serverless architecture would be: **API Gateway < Lambda < DynamoDB < S3**
#### AWS Lambda
- Credentials: ensure you're attaching a role to the function 
- Lambda triggers: S3, Kinesis, and EventBridge (formerly CloudWatch Events) are triggers
- Functions should be short. You can allocate up to 10 GB of RAM and 15 minutes of runtime
- AWS API call: Can be a trigger to kick off an EventBridge rule
  - faster than trying to scrape through CloudTrail

#### AWS Serverless Application Repository
- Is a managed repository for serverless applications and is deeply integrated with the AWS Lambda console
- It enables teams, organizations, and individual developers to find, deploy, publish, share, store, and easily assemble serverless architectures.

#### Containers and Images
- Amazon EKS or EKS Anywhere:
  - Kubernetes >> container management solution
  - can run in AWS and on-premises
  - open source
- AWS Fargate
  - Fargate is a technology that provides on-demand, right-sized compute capacity for containers
  - You don't have to provision, configure, or scale groups of virtual machines on your own to run containers
  - Can't work alone - you must be using Amazon ECS or EKS
- Amazon ECS
  - Container service
  - can encompass just about any workload
  - its preffered to use containers rather than EC2 on the exam
  - know the basics >> start with Dockerfile, build an image, upload that to a repo, and then run it on a host
- Amazon ECR
  - Is an AWS managed container image registry
  - image scanning helps in identifying software vulnerabilities in your container images

#### Amazon Aurora Serverless
- On-demand or auto scaling database 
- Variable traffic of workloads: good for unknown workloads or traffic spikes to the database
- Capacity plannig

#### AWS X-Ray
- gain application insights using requests and responses of services and functions at different points in an application flow
- watch out for words like: traces and downstream response times
- integrates natively with AWS Lambda or Amazon API Gateway to gain deeper insights
  - helps to understand your workload requests and responses

#### AWS AppSync
- best architecture for a managed GraphQL interface for any frontend application or developer
- connects applications and services to data and events with secure, serverless and high-performing GraphQL and Pub/Sub APIs


### Security
#### DDoS & AWS Shield
- Distributed Denial of Service (DDoS) attack attempts to make your website/app unavailable to your end users
  - Layer 4 attacks such as SYN floods or NTP aplification attacks
  - Layer 7 attacks include floods of GET/POST requests
- Use AWS Shield for protection against DDoS attacks
  - Layer 3 and Layer 4 protection
  - "Shield advanced" costs 3.000 USD a month >> gives you a dedicated 24/7 DDoS Response Team

#### CloudTrail
- is basically just CCTV for your AWS account
- logs all API calls made to your AWS account and stores these logs in S3
- After-the-fact incident investigation
- Near real-time intrusion detection
- Industry and regulatory compliance

#### AWS WAF
- Operates at Layer 7 (can block Layer 7 DDoS attacks)
- can even block SQL injections and cross-site scripting
- or block access to specific countries or IP addresses (e.g. IPs with more than 2.000 requests in 5 min >> create rate-based rule)
- allows 3 different behaviours
  - Allow all requests (except the ones you specify)
  - Block all requests (except the ones you specify)
  - Count the requests that match the properties you specify

#### AWS Firewall Manager
- With Firewall Manager, you set up your protections just once and the service automatically applies them across your accounts and resources, even as you add new accounts and resources.

#### GuardDuty
- Guards your Network andanalyzes tens of billions of events across multiple AWS data sources
  - such as AWS CloudTrail events, Amazon VPC Flow Logs, and DNS logs
- Alerts you of any abnormal or malicious behaviour (through AI)
- Updates a database of known malicious domains (through 3rd party feeds)
- Monitors CloudTrail logs, VPC Flow Logs, and DNS logs
- Findings appear in the GuardDuty dashboard
  - CloudWatch Events can be used to trigger a Lambda function to proactively address a threat

#### Macie
- Uses AI to analyze data in S3 and helps identify personal identifiable information, personal health information, and financial data
- Great for HIPAA and GDPR compliance as well as preventing identity theft
- Alerts can be sent to Amazon EventBridge and integrated with your event management system
- Automate remediation actions using services such as Step Functions

#### Amazon Inspector
- Continually scans AWS workloads for software vulnerabilities and unintended network exposure
- Perform vulnerability scans on both EC2 instances and VPCs (run once or weekly)
  - for EC2: host assessments
  - for VPC: network assessments 

#### KMS
- AWS Key Management Service 
  - managed service
  - makes it easy for you to create and control the encryption keys used to encrypt your data
  - start using service by requesting the creation of a customer master key (CMK)
    - You control the lifecycle of the CMK as well as who can use or manage it
  - Three ways to generate a CMK
    - AWS creates it. The key material for a CMK is generated within hardware security modules (HSMs)
    - Import key material from your own key management infrastructure
    - Have the key material generated and used in an AWS CloudHSM cluster as part of the custom key store feature in AWS KMS
  - Three ways to control permissions
    - Use the key policy: full scope of access defined in a single document
    - Use IAM policies in combination with the key policy: lets you manage all the permissions in IAM
    - Use grants in combination with the key policy: allow access to CMK in the key policy, as well as allow users to delegate their access to others
  - Deleting a key: AWS KMS enforces a waiting period. To delete a KMS key in AWS KMS you schedule key deletion (from 7 days up to 30 days (default))

#### KMS vs. CloudHSM
- KMS
  - Shared tenancy of underlying hardware
  - Automatic key rotation
  - Automatic key generation
- CloudHSM
  - Dedicated HSM to you (physical hardware device)
  - Full control of underlying hardware
  - Full control of users, groups, keys, etc.
  - No automatic key rotation

#### Secrets Manager
- can be used to securely store your application secrets: database credentials, API keys, SSH keys, passwords ...
- Applications use the Secrets Manager API
- Rotating credentials is easy
- When enabled, Secrets Manager will rotate credentials immediately
  - make sure all your application instances are configured to use SM BEFORE enabling credential rotation

#### Parameter Store
- universal key value storage
- CloudFormation can look up values that are stored in there

#### Parameter Store vs Secrets Manager
- If you are trying to minimize cost, choose Parameter Store
- If you need more than 10.000 parameters, key rotation, ability to generate passwords using CloudFormation, choose Secrets Manager

#### Presigned URLs
- used to share private files in your S3 buckets

#### Advanced IAM Policy Documents
- if something is not explicitly allowed >> implicity denied
- explicit deny > everything else
- only attached policies have effect. If you have multiple policies but haven't attached them to groups etc. they're not going to have an effect
- AWS joins all applicable policies >> remember that explicit deny will ailways beat that allow
- You got AWS managed policies and then you've got your customer managed policies as well

#### AWS Certificate Manager
- used to integrate SSl certificates
- AWS Certificate Manager integrates with Elastic Load Balancing, CloudFront, and API Gateway
- its a free service that saves time and money
  - automatically renew SSL certificates and rotate the old certificates with new certificates

#### AWS Audit Manager
- AWS Audit Manager helps you collect, review, and manage evidence to demonstrate that your usage of AWS services is in compliance
- continous auditing
- automating auditing reports
- HPAA or GDPR compliance

#### AWS Artifact
- AWS Artifact offers evidence to prove that the AWS Cloud infrastructure meets the compliance requirements
- see a scenario question asks about audits and the need for compliance reports

#### Amazon Cognito
- Easily add user sign-up and authentication to your mobile and web apps
- It also enables you to authenticate users through an external identity provider and provides temporary security credentials
- User pool: user directories that provide sign-up and sign-in options for users of your application
- Identity pool: allow your users access to other AWS services
- use both pools seperately or together
- Remember the chronological order of the way Cognito works
  - device connects to a user pool and authenticates and gets tokens
  - it then basically exchange those tokens with an identity pool and that will give it AWS credentials
  - access AWS services using credentials

#### Amazon Detective
- Operates accross multiple AWS services and analyzes the **root cause** of an event
- Do not confuse it with Inspector
  - Inspector is an automated vulnerability management service that continually scans EC2 and container workloads for software vulnerabilities and unintended network exposure

#### AWS Network Firewall
- Filters your network traffic before it reaches your internet gateway
- Or you require intrusion prevention systems
- Or any hardware firewall requirements
- AWS manage all the hardware for you

#### AWS Security Hub
- Is a Cloud Security Posture Management service (CSPM) that performs security best practice checks, aggregates alerts, and enables automated remediation
- single place to view all your security alerts across multiple AWS security services and AWS aacounts


### Automation
#### CloudFormation
- Create templates that describe all the AWS resources that you want >> CloudFormation takes care of provisioning and configuring those resources for you
- Understand what the parameters, mappings, and resource sections of the CloudFormation templates do
  - The optional Parameters enable you to input custom values to your template each time you create or update a stack.
  - The optional Mappings section matches a key to a corresponding set of named values >> if you want to set values based on a region, you can create a mapping that uses the region name as a key and contains the values you want to specify for each specific region
  - The required Resources section declares the AWS resources that you want to include in the stack
- Select answers that favor having resources that can be replaced at any time. Stateless is better than stateful
- Mappings and Parameter Store can be useful to help make your templates more flexible. >> we never want hardcoded IDs (like AMI or snapshot IDs)

#### Elastic Beanstalk
- A simple solution to bundle and deploy applications
- Quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure
- You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring

#### Systems Manager
- Secure end-to-end management solution for resources on AWS and in multicloud and hybrid environments
- AWS Systems Manager gives you visibility and control of your infrastructure on AWS
- Systems Manager provides a unified user interface so you can view operational data from multiple AWS services and enables you to automate operational tasks across your AWS resources
  - Session Manager: you can manage your(Amazon EC2 instances, edge devices, on-premises servers, and virtual machines (VMs)
  - You can use either an interactive one-click browser-based shell or the AWS Command Line Interface (AWS CLI)
- allows you to safely automate common and repetitive IT operations and management tasks across multiple accounts and AWS Regions


### Caching
#### CloudFront & Global Accelerator
- CloudFront improves performance for both cacheable content (such as images and videos) and dynamic content (such as API acceleration and dynamic site delivery)
  - CloudFront is the only option to add HTTPS to a static website being hosted in an S3 bucket
  - distribute private content to users with CloudFront Signed URL's
  - By design, delivering data out of Amazon CloudFront can be more cost-effective than delivering it from S3 directly to your users
- Global Accelerator improves performance for a wide range of applications over TCP or UDP by proxying packets at the edge to applications running in one or more AWS Regions
  - Gives you static IP addresses. Whenever the scenario talks about IP caching & reducing issues with customers caching old IP addresses >> think Global Accelerator
  - good fit for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice over IP

#### Amazon DynamoDB Accelerator (DAX)
- is a fully managed, highly available caching service built for Amazon DynamoDB
- Benefit from fast in-memory performance
- DAX is suitable for read-intensive workloads

#### Amazon ElastiCache
- Is a serverless, Redis- and Memcached-compatible caching service delivering real-time, cost-optimized performance for modern applications.
- Redis has more features than Memcached
  - Redis can be a persistent data store or as a cache, whereas Memcached is just a cache
  - Redis supports Backups


### Governance
#### AWS Organizations
- Centralized management of all of your AWS accounts
- Consolidated billing for all member accounts
- Meet your budgetary, security, or compliance needs
- Service control policies (SCPs) >> They are the only way to restrict what the root account can do
- Centralized logs >> CloudTrail offers support to log everything into a single AWS account
- Isolate workloads into seperate accounts >> more layers of security and controls

#### AWS Config
- Provides a detailed view of the configuration of AWS resources in your AWS account and how they were configured in the past
- You can see how the configurations and relationships change over time
- Need access to the historical configurations of your resources for compliance? >> provided by AWS Config
- Config offers the ability to automatically remediate problems using Automation documents

#### Authentication
- Make sure you're using AWS SSO for internal user management and Cognito for external
- Active Directory
  - If it's a lift and shift >> pick **Managed Microsoft AD**
  - If AD is staying on-premises, select **AD Connector**
- Cross-account role access is always a better solution than creating unnecessary IAM credentials

#### Cost Management
- Tracking costs >> you'll want to use a combination of tags, Cost Explorer, and AWS Budgets
- Create proactive alerts. When users get to the 80% threshold, tell someone via SNS
- Automate the response to spend less money. Always think about how you can remove the human interaction
- **AWS Cost and Usage Reports** or **Cost Explorer** for in-depth reporting purposes
  - They can also be set up to automatically store updated reports in Amazon S3 every 24 hours
- Use AWS Compute Optimizer ot generate recommendations on implementing more accurate compute sizes bases on your actual needs

#### Trusted Advisor
- Optimize costs, improve performance, and address security gaps
- Continuously evaluates your AWS environment using best practice checks across the categories of cost optimization, performance, resilience, security, operational excellence, and service limits
- Recommend actions to remediate any deviations from best practices
- For the exam: i's strictly an auditing tool and won't solve the problem for you
  - to automate it use EventBridge to kick off a Lambda function to solve the problem for you

#### AWS Control Tower
- Offers the easiest way to set up and govern a secure, compliant, multi-account AWS environment based on best practices established by working with thousands of enterprises
- Extends the capabilities of AWS Organizations. To help keep your organizations and accounts from drift, which is divergence from best practices, AWS Control Tower applies controls (sometimes called guardrails)
- AWS Control Tower can deploy a Log Archive account for centralized security logs and an Audit account for any SNS notifications around compliance violations.

#### AWS License Manager
- Makes it easier for you to manage your software licenses from software vendors centrally across AWS and your on-premises environments
- prevent license abuse and overcharges and reduce the risk of non-compliance and misreporting

#### AWS Service Catalog
- Centrally manage commonly deployed IT services, and helps organizations achieve consistent governance and meet compliance requirements
- End users can quickly deploy only the approved IT services they need, following the constraints set by your organization

#### AWS Proton
- Automated infrastructure as code provisioning and deployment of serverless and container-based applications
- As an administrator, you create versioned service templates that define standardized infrastructure and deployment tooling
- As an application developer, you can select from the available service templates to automate your application or service deployments

#### Well-Architected Tool
- Document architectural decisions and their measurements against well-established industry best practices
- The framework provides a consistent approach for measuring architectures and provides guidance for implementing designs that scale with your needs over time

#### AWS Health
- Dashboard and service meant to provide notifications of both public and account-specific events within AWS
- AWS Health provides ongoing visibility into your resource performance and the availability of your AWS services and accounts
- Questions about service alerts or notifications of EC2 hardware maintenance reboots will leverage AWS Health in some manner

#### AWS Personal Health Dashboard vs. Service Health Dashboard
- AWS Personal Health Dashboard provides alerts and guidance for AWS events that might affect your environment
- While the Service Health Dashboard shows the general status of AWS services, the Personal Health Dashboard provides proactive and transparent notifications about your specific AWS environment



### Migration
#### AWS Snow Family
- The AWS Snow Family helps customers who need to run operations in austere, non-data center environments, and in locations which lack consistent network connectivity
- Accelerate moving offline data or remote storage to the cloud

##### **AWS Snowmobile** 
- Is a standard 45-foot shipping container filled with mass-storage AWS Snowball devices, together storing up to 100 PB (petabytes)
- The container is pulled by a semi-trailer truck

##### **Snowball Edge Compute Optimized** or **Snowball Edge Storage Optimized**
- Accelerate application performance in disconnected, austere edge environments and run compute workloads with little or no connectivity
- Has no storage or processing power constraints, can be used to send terabytes of data to the cloud quickly

##### **AWS Snowcone**
- AWS Snowcone is the most compact and portable device
- Deploy ultra-portable data transfer and edge computing devices anywhere
- Collect and process data, transfer with AWS DataSync, or ship the device with data to AWS for offline transfer

#### Storage Gateway
- Gives your applications on-premises and in-cloud access to virtually unlimited cloud storage
- You can deploy Storage Gateway as a virtual machine (VM) within your VMware, Hyper-V, or Linux KVM virtual environment
- Or as an Amazon EC2 instance within your Amazon Virtual Private Cloud (Amazon VPC)
- **File Gateway** delivers on-premises file access to your Amazon S3 data (immediately retrievable)
- **Tape Gateway** virtualizes tape backup and archive workflows in AWS (not immediately retrievable)
- **Volume Gateway** expands on-premises block storage capacity

#### DataSync and Transfer Family
- DataSync is an agent-based solution that excels at one-time migrations of file shares into AWS
  - EFS and FSx are both viable locations for DataSync to transfer content into
- Transfer Family allows you to use legacy file transfer protocols to  give older applications the ability to read and write from S3

#### Migration Hub
- Is an organizational tool that gives you a way to organize all your steps
- Discover applications for migration and modernization and outline strategies for execution
- Utilizes guided migration templates and collaborative efforts across teams
- **Server Migration Service:** The tool you'll want to use to migrate out of the data center and into AWS

#### AWS Application Discovery Service
- Discover on-premises server inventory and behavior to plan cloud migrations
- Quickly migrate entire applications to the AWS Cloud
- Agentless discovery can be used via OVA file deployment to vSphere
- Agent-based discovery collects detailed information of VMs on both Linux and Windows OS

### AWS Database Migration Service (AWS DMS)
- Makes it possible to migrate relational databases, data warehouses, NoSQL databases, and other types of data stores.
- It works for on-premises to the cloud, or for moving data between different RDS databases
- for example: AWS DMS supports Amazon S3 as the source and Kinesis as the target, so data stored in an S3 bucket is streamed to Kinesis

#### AWS Application Migration Service (AWS MGN)
- Automated lift-and-shift service for migrating infrastructure to AWS (MGN should be used instead of Server Migration Service)
- Replicates sorce servers into AWS for non-disruptive cutovers
- it automatically converts and launches your servers on AWS
- RTO of minutes and RPO of sub-seconds
  - Recovery Time Objective (RTO)
  - Recovery Point Objective (RPO)



### Front-End Web and Mobile
#### AWS Amplify
- Build full-stack web and mobile apps in hours
- Focus on coding and not the infrastructure
- Add features like auth and storage, connect to real-time data sources, deploy, and scale to millions of users
- Server-side rendering support

#### AWS Device Farm
- Is an application testing service that lets you improve the quality of your web and mobile apps by testing them across an extensive range of desktop browsers and real mobile devices >> without having to provision and manage any testing infrastructure

#### Pinpoint
- Is an AWS service that you can use to engage with your customers across multiple messaging channels
- You can use Amazon Pinpoint to send push notifications, in-app notifications, emails, text messages, voice messages, and messages over custom channels
- It includes segmentation, campaign, and journey features that help you send the right message to the right customer at the right time over the right channel
- Leverage machine learning models to predict engagement interactions



### Machine Learning
#### Amazon Rekognition
- Makes it simple to join your application’s image analysis and video analysis by using deep learning, highly scalable, and proven technology without having the ML tool
- Content moderation using AI/ML

#### Amazon SageMaker
- Empowers developers and data scientists to create, train, and deploy ML models into a production-ready hosted environment within a single platform.
- Notebooks: access a managed Jupyter Notebook environment
- Set up and manage labeling jobs for training datasets using active learning and human labeling
- Stages: Create a Model >> Create an Endpoint Configuration >> Create an Endpoint
- SageMaker Neo: automatically optimizes machine learning models for inference on cloud instances and edge devices to run faster with no loss in accuracy.
- Reducing cost: Elastic inference
- Savings Plans offer a flexible usage-based pricing model for Amazon SageMaker, 

#### Comprehend
- Uses natural language processing (NLP) to extract insights about the content of documents
- For example, using Amazon Comprehend you can search social networking feeds for mentions of products or scan an entire document repository for key phrases.
- Sentiment analysis

#### Forecast
- Designed to automate the data, detect the key attributes, and pick suitable algorithms to produce an accurate time-series forecast
- Analyze time-series data and make predictions based on that analysis

#### Fraud Detector
- Is a highly specialized AI tool built to **quickly identify potentially fraudulent activities** such as stolen debit cards, credit cards, and fake registrations

#### Kendra
- Amazon Kendra is an **intelligent search service** that uses natural language to find results accurately for your application and websites based on customer queries

#### Lex
- Permits developers to publish text chatbots or voice across multiple platforms like chat services, web apps, and mobile devices
- This is the service that powers the logic behind A-Lex-a

#### Amazon Polly
- Is an advanced Text-to-Speech service that converts text into human-like text-to-speech voices
- Moreover, it offers lifelike voice outputs across Japanese, Korean, and Chinese languages
- This allows users to develop automated responses in the languages of their choice and convenience
- Polly allows Alexa to speak back to you

#### Transcribe
- Is an automatic speech-to-text solution platform that uses ML models to convert audio to text and produce a review or read transcripts

#### Textract
- Is a deep learning-based service that automatically extracts text and handwriting, detecting data from scanned copies

#### Translate
- Is a neural machine translation service that allows you to translate a bulk amount of text from one language to another. It supports 75 languages



### Media
- **Elastic Transcoder:** convert your media files into an optimized format of a particular device
  - You simply create a transcoding “job” specifying the location of your source media file and how you want it transcoded
- **Amazon Kinesis Video Streams:** video streaming at scale from millions of devices >> e.g. Ring (doorbell camera)
  - It durably stores, encrypts, and indexes video data in your streams, and allows you to access your data through easy-to-use APIs



    
