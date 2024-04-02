# Go2Guide-AWS-Certified-Solutions-Architect--Associate-SAA-C03
Explore the ultimate companion for achieving your AWS Certified Solutions Architect Certification. This comprehensive guide is your go-to resource, meticulously curated with vital links to whitepapers, essential services, and handy cheat sheets tailored to each exam topic. Additionally, uncover invaluable exam tips meticulously crafted for mastering each service with confidence.

I'd like to start with some motivation: [Don't Shave That Yak!](https://seths.blog/2005/03/dont_shave_that/)
Don't give up when you don't understand a concept perfectly .. remember, doing it well now is much better than doing it perfectly later.

## Where to study
Udemy Course ($$$):
https://nttdata.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03

Udemy Practice Exams ($$$):
https://nttdata.udemy.com/course/practice-exams-aws-certified-solutions-architect-associate

Cloud Guru course with Hands-On labs ($$$):
https://learn.acloud.guru/course/certified-solutions-architect-associate/overview 

3D-Role-Playing-Game ($$$):
https://aws.amazon.com/training/digital/aws-cloud-quest

AWS Traing live on Twitch (free):
https://aws.amazon.com/training/twitch/

Good old Youtube (free):
- https://www.youtube.com/@CloudVikings
- https://www.youtube.com/@BeABetterDev
- https://www.youtube.com/@GoCloudArchitects


## Important links
Exam Guide + Sample Questions:
https://aws.amazon.com/certification/certified-solutions-architect-associate

AWS Certification Paths:
https://d1.awsstatic.com/training-and-certification/docs/AWS_certification_paths.pdf

AWS Services Cheat Sheet:
https://digitalcloud.training/category/aws-cheat-sheets/aws-solutions-architect-associate

AWS Whitepaper & Guides:
https://aws.amazon.com/whitepapers

AWS Architecture Center:
https://aws.amazon.com/architecture

AWS Well-Architected Framework
https://docs.aws.amazon.com/pdfs/wellarchitected/latest/framework/wellarchitected-framework.pdf

AWS Global Infrastructure:
https://aws.amazon.com/de/about-aws/global-infrastructure

Shared Responsibility Model:
https://aws.amazon.com/compliance/shared-responsibility-model

Serverless on AWS:
https://aws.amazon.com/serverless

AWS Support Plans:
https://aws.amazon.com/premiumsupport/plans


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

#### Securing Your Bucket with S3
- **Buckets are private by default:** On creation the bucket is private including all objects within it. You need to specifically allow public access on both the bucket **and** its objects
- **Object Access Control List's (ACLs):** To make individual objects public
- **Bucket policies:** make entire buckets public using bucket policies (Best Practice)

#### Hosting a Static Website
- You can use s3 to host **static content only** (not dynamic)
- **Automatic scaling:** S3 scales automatically with demand

#### Versioning Objects
- **All Versions:** All Versions of an object are stored in S3. This includes all writes and even if you delete an objects
- **Backup:** Can be a great backup tool
- **Cannot be disabled:** Once enbaled, versioning cannot be disabled - only suspended
- **Lifecycle Rules:** Can be integrated with lifecycle rules
- **Supports MFA:** Can support MFA

#### Storage Classes
Head over to [S3 Storage Classes](https://aws.amazon.com/de/s3/storage-classes/)

#### Lifecycle Management with S3
An S3 Lifecycle configuration is an XML file that consists of a set of rules with predefined actions that you want Amazon S3 to perform on objects during their lifetime.
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
  - There are no limits to the number of prefixes in a bucket. You can increase your read or write performance by using parallelization. For example, if you create 10 prefixes in an Amazon S3 bucket to parallelize reads, you could scale your read performance to 55,000 read requests per second. Similarly, you can scale write operations by writing to multiple prefixes.
- **SSE-KMS built-in limits**
  - Region-specific, however it's either 5.500, 10.000 or 30.000 requests per second
  - Uploading/downloading will count toward the KMS quota
  - Currently you cannot request a quota increasy for KMS
- Use **multipart uploads** to increase performance when uploading files to S3 (for any file over 100 MB)
- Use **S3 byte-range fetches** to increase performance when downloading files to S3

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

**Dedicated Host**
- Most expensive option
- A physical EC2 server dedicated for your use
- Great if you have serverbound licenses to reuse or compliance requirements
- Note: Any question that talks about special licensing requirements

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
- You can have multiple security groups attached to EC2 instances
- ALL inbound traffic is blocked by default
- All outbound traffic is allowed

#### User Data and Metadata
- User data are simply bootstrap scripts: **a script that runs when the EC2-Instance first runs**
  - It passes user data to the instance and can be used to install applications (like web servers and databases), as well as do updates and more
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

#### Types of Placement Groups
To meet the needs of your workload, you can launch a group of interdependent EC2 instances into a placement group to influence their placement.
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

#### Deploy vCenter on AWS using VMware
this is basically the perfect solution for extending your private VMware cloud onto the AWS public cloud.
E.g. things like cloud migration or just basically doing disaster recovery using AWS, but you want all the native tools that come with VMware and within vCenter itself.

#### AWS Outposts
With that you can extend AWS to your data center - just think of AWS Outposts as bringing AWS to you.
- **AWS Outpost racks**
  - this is for large deployments, so these are 42U form factor racks that will go inside a data center.
- **AWS Outpost servers**
  - for smaller deployments, so this will be things like putting in a 1U server inside a retail shop, for example.

### Elastic Block Storage (EBS) and Elastic File System (EFS)


### Databases


### Virtual Private Cloud (VPC) Networking


### Route 53


### Elastic Load Balencing (ELB)


### Monitoring


### High Availability and Scaling


### Decoupling Workflows


### Big Data


### Serverless Architecture


### Security


### Automation


### Caching


### Governance


### Migration


### Front-End Web and Mobile

### Machine Learning

### Media
