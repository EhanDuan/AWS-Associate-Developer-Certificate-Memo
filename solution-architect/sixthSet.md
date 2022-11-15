# Solution Architect Exam#6 Practice Set
A multinational corporate and investment bank is regularly processing steady workloads of accruals, loan interests, and other critical financial calculations every night from 10 PM to 3 AM on their on-premises data center for their corporate clients. Once the process is done, the results are then uploaded to the Oracle General Ledger which means that the processing should not be delayed or interrupted. The CTO has decided to move its IT infrastructure to AWS to save costs. The company needs to reserve compute capacity in a specific Availability Zone to properly run their workloads.

As the Senior Solutions Architect, how can you implement a cost-effective architecture in AWS for their financial system?

+ Use On-Demand EC2 instances which allows you to pay for the instances that you launch and use by the second. Reserve compute capacity in a specific Availability Zone to avoid any interruption.
+ Use Regional Reserved Instances to reserve capacity on a specific Availability Zone and lower down the operating cost through its billing discounts.
+ Use On-Demand Capacity Reservations, which provide compute capacity that is always available on the specified recurring schedule.
+ Use Dedicated Hosts which provide a physical host that is fully dedicated to running your instances, and bring your existing per-socket, per-core, or per-VM software licenses to reduce costs.


<details close>
<summary>Answer</summary>
c
</details>

<br>


<details close>
<summary>Note</summary>
On-Demand Capacity Reservations enable you to reserve compute capacity for your Amazon EC2 instances in a specific Availability Zone for any duration. This gives you the ability to create and manage Capacity Reservations independently from the billing discounts offered by Savings Plans or Regional Reserved Instances.

Using Regional Reserved Instances to reserve capacity on a specific Availability Zone and lower down the operating cost through its billing discounts is incorrect because this feature is available in Zonal Reserved Instances only and not on Regional Reserved Instances.
</details>

<br>

---

A company plans to host a movie streaming app in AWS. The chief information officer (CIO) wants to ensure that the application is highly available and scalable. The application is deployed to an Auto Scaling group of EC2 instances on multiple AZs. A load balancer must be configured to distribute incoming requests evenly to all EC2 instances across multiple Availability Zones.

Which of the following features should the Solutions Architect use to satisfy these criteria?

+ Amazon VPC IP Address Manager (IPAM)
+ Path-based Routing
+ Cross-zone load balancing
+ AWS Direct Connect SiteLink

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An online stock trading system is hosted in AWS and uses an Auto Scaling group of EC2 instances, an RDS database, and an Amazon ElastiCache for Redis. You need to improve the data security of your in-memory data store by requiring the user to enter a password before they are granted permission to execute Redis commands.   

Which of the following should you do to meet the above requirement?
+ Enable the in-transit encryption for Redis replication groups.
+ Create a new Redis replication group and set the `AtRestEncryptionEnabled` parameter to `true`
+ Authenticate the users using Redis AUTH by creating a new Redis Cluster with both the  `--transit-encryption-enabled` and `--auth-token` parameters enabled.
+ Do nothing. This feature is already enabled by default.
+ None of the above. 

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
Using Redis AUTH command can improve data security by requiring the user to enter a password before they are granted permission to execute Redis commands on a password-protected Redis server.
</details>

<br>

---

A disaster recovery team is planning to back up on-premises records to a local file server share through SMB protocol. To meet the company’s business continuity plan, the team must ensure that a copy of data from 48 hours ago is available for immediate access. Accessing older records with delay is tolerable.

Which should the DR team implement to meet the objective with the LEAST amount of configuration effort?
+ Use an AWS Storage File gateway with enough storage to keep data from the last 48 hours. Send the backups to an SMB share mounted as a local disk.
+ Create an SMB file share in Amazon FSx for Windows File Server that has enough storage to store all backups. Access the file share from on-premises.
+ Mount an Amazon EFS file system on the on-premises client and copy all backups to an NFS share.
+ Create an AWS Backup plan to copy data backups to a local SMB share every 48 hours.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---
A fast food company is using AWS to host their online ordering system which uses an Auto Scaling group of EC2 instances deployed across multiple Availability Zones with an Application Load Balancer in front. To better handle the incoming traffic from various digital devices, you are planning to implement a new routing system where requests which have a URL of `<server>/api/android` are forwarded to one specific target group named "Android-Target-Group". Conversely, requests which have a URL of `<server>/api/ios` are forwarded to another separate target group named "iOS-Target-Group".   

How can you implement this change in AWS?
+ Use host conditions to define rules that forward requests to different target groups based on the hostname in the host header. This enables you to support multiple domains using a single load balancer.
+ Replace your ALB with a Gateway Load Balancer then use path conditions to define rules that forward requests to different target groups based on the URL in the request.
+ Use path conditions to define rules that forward requests to different target groups based on the URL in the request.
+ Replace your ALB with a Network Load Balancer then use host conditions to define rules that forward requests to different target groups based on the URL in the request.


<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company has an application architecture that stores both the access key ID and the secret access key in a plain text file on a custom Amazon Machine Image (AMI). The EC2 instances, which are created by using this AMI, are using the stored access keys to connect to a DynamoDB table.

What should the Solutions Architect do to make the current architecture more secure?
+ Put the access keys in Amazon Glacier instead.
+ Put the access keys in an Amazon S3 bucket instead.
+ Remove the stored access keys in the AMI. Create a new IAM role with permissions to access the DynamoDB table and assign it to the EC2 instances.
+ Do nothing. The architecture is already secure because the access keys are already in the Amazon Machine Image.
<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A Solutions Architect needs to set up the required compute resources for the application which have workloads that require high, sequential read and write access to very large data sets on local storage.

Which of the following instance type is the most suitable one to use in this scenario?
+ Storage Optimized Instances
+ Memory Optimized Instances
+ Compute Optimized Instances
+ General Purpose Instances

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

An application is using a Lambda function to process complex financial data that run for 15 minutes on average. Most invocations were successfully processed. However, you noticed that there are a few terminated invocations throughout the day, which caused data discrepancy in the application.

Which of the following is the most likely cause of this issue?

+ The failed Lambda functions have been running for over 15 minutes and reached the maximum execution time.
+ The concurrent execution limit has been reached.
+ The Lambda function contains a recursive code and has been running for over 15 minutes.
+ The failed Lambda Invocations contain a `ServiceException` error which means that the AWS Lambda service encountered an internal error.

<details close>
<summary>Answer</summary>
a
</details>

<br>


<details close>
<summary>Note</summary>
You pay for the AWS resources that are used to run your Lambda function. To prevent your Lambda function from running indefinitely, you specify a timeout. When the specified timeout is reached, AWS Lambda terminates execution of your Lambda function. It is recommended that you set this value based on your expected execution time. The default timeout is 3 seconds, and the maximum execution duration per request in AWS Lambda is 900 seconds, which is equivalent to 15 minutes.


</details>

<br>

---

A Solutions Architect is trying to enable Cross-Region Replication to an S3 bucket but this option is disabled. Which of the following options is a valid reason for this?
+ The Cross-Region Replication feature is only available for Amazon S3 - One Zone-IA
+ This is a premium feature which is only for AWS Enterprise accounts.
+ In order to use the Cross-Region Replication feature in S3, you need to first enable versioning on the bucket.
+ The Cross-Region Replication feature is only available for Amazon S3 - Infrequent Access.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company is designing a customized text messaging service that targets its mobile app users. As part of its multi-engagement marketing campaign, a company needs to send a one-time confirmation message to all of its subscribers using Short Message Service (SMS). The solutions architect must design the system to allow a subscriber to reply to the SMS messages.

The customer responses must be kept for an entire year for analysis and targeted sale promotions. In addition, the SMS responses must also be collected, processed, and analyzed in near-real-time.

Which solution will meet these requirements with the LEAST operational overhead?
+ Create a new topic in Amazon Simple Notification Service (Amazon SNS) and an Amazon Kinesis data stream configured with all its default settings. Send SMS messages using Amazon SNS. Integrate the Kinesis data stream to the SNS topic for data collection, archiving, and analysis.
+ Launch a new Amazon Simple Queue Service (Amazon SQS) queue to send out SMS messages. Use AWS Step Functions and AWS Lambda to collect, process, and analyze responses. Store the data to Amazon S3 Glacier Instant Retrieval.
+ Create an Amazon Pinpoint journey for the multi-engagement SMS marketing campaign and an Amazon Kinesis Data Stream for analysis. Configure Amazon Pinpoint to send events to the Kinesis data stream for collection, processing, and analysis. Set the retention period of the Kinesis data stream to 365 days.
+ Set up an Amazon Connect contact flow to send the confirmation SMS messages to the mobile app users. Deploy an AWS Lambda function to process and analyze the responses. Store the data to Amazon S3 Glacier Flexible Retrieval

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
In Amazon Pinpoint, an event is an action that occurs when a user interacts with one of your applications, when you send a message from a campaign or journey, or when you send a transactional SMS or email message. For example, if you send an email message, several events occur:

- When you send the message, a send event occurs.

- When the message reaches the recipient's inbox, a delivered event occurs.

- When the recipient opens the message, an open event occurs.

You can configure Amazon Pinpoint to send information about events to Amazon Kinesis. The Kinesis platform offers services that you can use to collect, process, and analyze data from AWS services in real time.
</details>

<br>

---

A Python application running on VMware Cloud on AWS must connect to an Amazon DynamoDB table called `tutorialsdojo`. Considering the principle of least privilege access, a solutions architect must form an IAM policy that allows the application to read, write, update and delete items from the `tutorialsdojo` table only.

Which IAM policy would satisfy the requirements?

```json
{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": [
"dynamodb:PutItem",
"dynamodb:DeleteItem",
"dynamodb:GetItem",
"dynamodb:UpdateItem"
],
"Resource": "arn:aws:dynamodb:us-east-2:123456789012:table/tutorialsdojo"
}
]
}
```

```json
{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": [
"dynamodb:Put*",
"dynamodb:Delete*",
"dynamodb:Get*",
"dynamodb:Update*"
],
"Resource": "arn:aws:dynamodb:us-east-2:123456789012:table/tutorialsdojo"
}
]
}
```

```json
{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": [
"dynamodb:PutItem",
"dynamodb:DeleteItem",
"dynamodb:GetItem",
"dynamodb:UpdateItem"
],
"Resource": "arn:aws:dynamodb:us-east-2:123456789012:table/*"
}
]
}
```

```json
{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": "*",
"Resource": "arn:aws:dynamodb:us-east-2:123456789012:table/tutorialsdojo"
}
]
}
```

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A web application, which is hosted in your on-premises data center and uses a MySQL database, must be migrated to AWS Cloud. You need to ensure that the network traffic to and from your RDS database instance is encrypted using SSL. For improved security, you have to use the profile credentials specific to your EC2 instance to access your database, instead of a password.   

Which of the following should you do to meet the above requirement?

+ Launch a new RDS database instance with the Backtrack feature enabled.
+ Configure your RDS database to enable encryption.
+ Set up an RDS database and enable the IAM DB Authentication.
+ Launch the mysql client using the `--ssl-ca` parameter when connecting to the database.
<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company is using Amazon S3 to store frequently accessed data. The S3 bucket is shared with external users that will upload files regularly. A Solutions Architect needs to implement a solution that will grant the bucket owner full access to all uploaded objects in the S3 bucket.

What action should be done to achieve this task?

+ Enable the Requester Pays feature in the Amazon S3 bucket.
+ Create a CORS configuration in the S3 bucket.
+ Create a bucket policy that will require the users to set the object's ACL to `bucket-owner-full-control`.
+ Enable server access logging and set up an IAM policy that will require the users to set the object's ACL to `bucket-owner-full-control`.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A manufacturing company launched a new type of IoT sensor. The sensor will be used to collect large streams of data records. You need to create a solution that can ingest and analyze the data in real-time with millisecond response times.

Which of the following is the best option that you should implement in this scenario?
+ Ingest the data using Amazon Kinesis Data Streams and create an AWS Lambda function to store the data in Amazon Redshift.
+ Ingest the data using Amazon Kinesis Data Firehose and create an AWS Lambda function to store the data in Amazon DynamoDB.
+ Ingest the data using Amazon Simple Queue Service and create an AWS Lambda function to store the data in Amazon Redshift.
+ Ingest the data using Amazon Kinesis Data Streams and create an AWS Lambda function to store the data in Amazon DynamoDB.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A multinational manufacturing company has multiple accounts in AWS to separate their various departments such as finance, human resources, engineering and many others. There is a requirement to ensure that certain access to services and actions are properly controlled to comply with the security policy of the company.

As the Solutions Architect, which is the most suitable way to set up the multi-account AWS environment of the company?
+ Set up a common IAM policy that can be applied across all AWS accounts.
+ Connect all departments by setting up a cross-account access to each of the AWS accounts of the company. Create and attach IAM policies to your resources based on their respective departments to control access.
+ Provide access to externally authenticated users via Identity Federation. Set up an IAM role to specify permissions for users from each department whose identity is federated from your organization or a third-party identity provider.
+ Provide access to externally authenticated users via Identity Federation. Set up an IAM role to specify permissions for users from each department whose identity is federated from your organization or a third-party identity provider.
+ Use AWS Organizations and Service Control Policies to control services on each account.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A global news network created a CloudFront distribution for their web application. However, you noticed that the application's origin server is being hit for each request instead of the AWS Edge locations, which serve the cached objects. The issue occurs even for the commonly requested objects.

What could be a possible cause of this issue?

+ An object is only cached by Cloudfront once a successful request has been made hence, the objects were not requested before, which is why the request is still directed to the origin server.
+ The file sizes of the cached objects are too large for CloudFront to handle.
+ The Cache-Control max-age directive is set to zero.
+ There are two primary origins configured in your Amazon CloudFront Origin Group.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A game development company operates several virtual reality (VR) and augmented reality (AR) games which use various RESTful web APIs hosted on their on-premises data center. Due to the unprecedented growth of their company, they decided to migrate their system to AWS Cloud to scale out their resources as well to minimize costs. 

Which of the following should you recommend as the most cost-effective and scalable solution to meet the above requirement?
+ Use AWS Lambda and Amazon API Gateway.
+ Set up a micro-service architecture with ECS, ECR, and Fargate.
+ Host the APIs in a static S3 web hosting bucket behind a CloudFront web distribution.
+ Use a Spot Fleet of Amazon EC2 instances, each with an Elastic Fabric Adapter (EFA) for more consistent latency and higher network throughput. Set up an Application Load Balancer to distribute traffic to the instances.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company deployed a fleet of Windows-based EC2 instances with IPv4 addresses launched in a private subnet. Several software installed in the EC2 instances are required to be updated via the Internet.

Which of the following services can provide the firm a highly available solution to safely allow the instances to fetch the software patches from the Internet but prevent outside network from initiating a connection?
+ Egress-Only Internet Gateway  
+ VPC Endpoint  
+ NAT Gateway
+ NAT Instance  
<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company developed a financial analytics web application hosted in a Docker container using MEAN (MongoDB, Express.js, AngularJS, and Node.js) stack. You want to easily port that web application to AWS Cloud which can automatically handle all the tasks such as balancing load, auto-scaling, monitoring, and placing your containers across your cluster.

Which of the following services can be used to fulfill this requirement?
+ AWS CloudFormation
+ AWS Compute Optimizer
+ Amazon Elastic Container Service (Amazon ECS)
+ AWS Elastic Beanstalk

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
Amazon Elastic Container Service (Amazon ECS) is incorrect. Although it also provides Service Auto Scaling, Service Load Balancing, and Monitoring with CloudWatch, these features are not automatically enabled by default unlike with Elastic Beanstalk. Take note that the scenario requires a service that will automatically handle all the tasks such as balancing load, auto-scaling, monitoring, and placing your containers across your cluster. You will have to manually configure these things if you wish to use ECS. With Elastic Beanstalk, you can manage your web application in an environment that supports the range of services easier.
</details>

<br>

---

Video uploads are taking longer than expected, which impacts the performance of your application.

Which method will help improve the performance of the application?
+ Enable Enhanced Networking with the Elastic Network Adapter (ENA) on your EC2 Instances.
+ Use Amazon S3 Multipart Upload API.
+ Leverage on Amazon CloudFront and use HTTP POST method to reduce latency.
+ Use Amazon Elastic Block Store Provisioned IOPS and an Amazon EBS-optimized instance.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has multiple AWS sandbox accounts that are used by its development team. All developers must be given access to the contents of one of the main account’s S3 buckets. For security purposes, any personally identifiable information (PII) or financial data uploaded in the bucket must be continuously monitored and removed.

How can this be done at the lowest possible cost and with the least amount of configuration effort?
+ Create an S3 bucket policy that grants access from the sandbox accounts. Use Amazon Macie to discover personally identifiable information (PII) or financial data.
+ Configure cross-account replication on the S3 bucket. Integrate AWS Audit Manager with the S3 bucket to discover any personally identifiable information (PII) or financial data.
+ Generate a pre-signed URL for the objects on the S3 bucket. Use the Amazon S3 Storage Lens to discover personally identifiable information (PII) or financial data.
+ Add S3 read permission to the IAM policy of each IAM user from the sandbox accounts. Use Amazon Detective to discover personally identifiable information (PII) or financial data.
<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A multinational company has been building its new data analytics platform with high-performance computing workloads (HPC) which requires a scalable, POSIX-compliant storage service. The data need to be stored redundantly across multiple AZs and allows concurrent connections from thousands of EC2 instances hosted on multiple Availability Zones.

Which of the following AWS storage service is the most suitable one to use in this scenario?
+ Amazon EBS Volumes
+ Amazon Elastic File System
+ Amazon S3
+ Amazon ElastiCache

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A tech company is having an issue whenever they try to connect to the newly created EC2 instance using a Remote Desktop connection from a computer. Upon checking, the Solutions Architect has verified that the instance has a public IP and the Internet gateway and route tables are in place.

What else should he do to resolve this issue?
+ Adjust the security group to allow inbound traffic on port 22 from the company’s IP address.
+ Adjust the security group to allow inbound traffic on port 3389 from the company’s IP address.
+ You should restart the EC2 instance since there might be some issue with the instance
+ You should create a new instance since there might be some issue with the instance

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A cryptocurrency company wants to go global with its international money transfer app. Your project is to make sure that the database of the app is highly available in multiple regions.

What are the benefits of adding Multi-AZ deployments in Amazon RDS? (Select TWO.)
+ Provides enhanced database durability in the event of a DB instance component failure or an Availability Zone outage.
+ Significantly increases the database performance.
+ Creates a primary DB Instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ) in a different region.
+ Increased database availability in the case of system upgrades like OS patching or DB Instance scaling.
+ Provides SQL optimization.

<details close>
<summary>Answer</summary>
a,d
</details>

<br>

---

A startup is building a microservices architecture in which the software is composed of small independent services that communicate over well-defined APIs. In building large-scale systems, fine-grained decoupling of microservices is a recommended practice to implement. The decoupled services should scale horizontally from each other to improve scalability.

What is the difference between Horizontal scaling and Vertical scaling?
+ Vertical scaling means running the same software on a fully serverless architecture using Lambda. Horizontal scaling means adding more servers to the existing pool and it doesn’t run into limitations of individual servers.
+ Horizontal scaling means running the same software on bigger machines which is limited by the capacity of individual servers. Vertical scaling is adding more servers to the existing pool and doesn’t run into limitations of individual servers.
+ Vertical scaling means running the same software on bigger machines which is limited by the capacity of the individual server. Horizontal scaling is adding more servers to the existing pool and doesn’t run into limitations of individual servers.
+ Horizontal scaling means running the same software on smaller containers such as Docker and Kubernetes using ECS or EKS. Vertical scaling is adding more servers to the existing pool and doesn’t run into limitations of individual servers.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A game company has a requirement of load balancing the incoming TCP traffic at the transport level (Layer 4) to their containerized gaming servers hosted in AWS Fargate. To maintain performance, it should handle millions of requests per second sent by gamers around the globe while maintaining ultra-low latencies.

Which of the following must be implemented in the current architecture to satisfy the new requirement?
+ Launch a new Network Load Balancer.
+ Launch a new Application Load Balancer.
+ Create a new record in Amazon Route 53 with Weighted Routing policy to load balance the incoming traffic.
+ Launch a new microservice in AWS Fargate that acts as a load balancer since using an ALB or NLB with Fargate is not possible.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A global medical research company has a molecular imaging system that provides each client with frequently updated images of what is happening inside the human body at the molecular and cellular levels. The system is hosted in AWS and the images are hosted in an S3 bucket behind a CloudFront web distribution. When a fresh batch of images is uploaded to S3, it is required to keep the previous ones in order to prevent them from being overwritten.

Which of the following is the most suitable solution to solve this issue?

+ Use versioned objects
+ Invalidate the files in your CloudFront web distribution
+ Add a separate cache behavior path for the content and configure a custom object caching with a Minimum TTL of 0
+ Add Cache-Control no-cache, no-store, or private directives in the S3 bucket


<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company plans to launch an application that tracks the GPS coordinates of delivery trucks in the country. The coordinates are transmitted from each delivery truck every five seconds. You need to design an architecture that will enable real-time processing of these coordinates from multiple consumers. The aggregated data will be analyzed in a separate reporting application.

Which AWS service should you use for this scenario?
+ Amazon Kinesis
+ AWS Data Pipeline
+ Amazon AppStream
+ Amazon Simple Queue Service

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company plans to implement a network monitoring system in AWS. The Solutions Architect launched an EC2 instance to host the monitoring system and used CloudWatch to monitor, store, and access the log files of the instance.

Which of the following provides an automated way to send log data to CloudWatch Logs from the Amazon EC2 instance?

+ CloudWatch Logs agent 
+ CloudTrail with log file validation
+ AWS Transfer for SFTP
+ CloudTrail Processing Library

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

An application is loading hundreds of JSON documents into an Amazon S3 bucket every hour which is registered in AWS Lake Formation as a data catalog. The Data Analytics team uses Amazon Athena to run analyses on these data, but due to the volume, most queries take a long time to complete.

What change should be made to improve the query performance while ensuring data security?
+ Convert the JSON documents into CSV format. Provide fine-grained named resource access control to specific databases or tables in AWS Lake Formation.
+ Transform the JSON data into Apache Parque format. Ensure that the user has an `lakeformation:GetDataAccess` IAM permission for underlying data access control.
+ Apply minification on the data and implement the Lake Formation tag-based access control (LF-TBAC) authorization strategy to ensure security.
+ Compress the data into GZIP format before storing it in the S3 bucket. Apply an IAM policy with `aws:SourceArn` and `aws:SourceAccount` global condition context keys in Lake Formation that prevents cross-service confused deputy problems and other security issues.

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
Apache Parquet is an open-source columnar storage format that is 2x faster to unload and takes up 6x less storage in Amazon S3 as compared to other text formats. One can COPY Apache Parquet and Apache ORC file formats from Amazon S3 to your Amazon Redshift cluster. Using AWS Glue, one can configure and run a job to transform CSV data to Parquet. Parquet is a columnar format that is well suited for AWS analytics services like Amazon Athena and Amazon Redshift Spectrum.
</details>

<br>

---

An online shopping platform has been deployed to AWS using Elastic Beanstalk. They simply uploaded their Node.js application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring. Since the entire deployment process is automated, the DevOps team is not sure where to get the application log files of their shopping platform. 

In Elastic Beanstalk, where does it store the application files and server log files?
+ Application files are stored in S3. The server log files can only be stored in the attached EBS volumes of the EC2 instances, which were launched by AWS Elastic Beanstalk.
+ Application files are stored in S3. The server log files can be stored directly in Glacier or in CloudWatch Logs.
+ Application files are stored in S3. The server log files can be optionally stored in CloudTrail or in CloudWatch Logs.
+ Application files are stored in S3. The server log files can also optionally be stored in S3 or in CloudWatch Logs.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---
A company requires corporate IT governance and cost oversight of all of its AWS resources across its divisions around the world. Their corporate divisions want to maintain administrative control of the discrete AWS resources they consume and ensure that those resources are separate from other divisions.

Which of the following options will support the autonomy of each corporate division while enabling the corporate IT to maintain governance and cost oversight? (Select TWO.)
+  Use AWS Trusted Advisor and AWS Resource Groups Tag Editor
+ Enable IAM cross-account access for all corporate IT administrators in each child account.
+ Create separate VPCs for each division within the corporate IT AWS account. Launch an AWS Transit Gateway with equal-cost multipath routing (ECMP) and VPN tunnels for intra-VPC communication.
+ Use AWS Consolidated Billing by creating AWS Organizations to link the divisions’ accounts to a parent corporate account.
+ Create separate Availability Zones for each division within the corporate IT AWS account. Improve communication between the two AZs using the AWS Global Accelerator.


<details close>
<summary>Answer</summary>
b,d
</details>

<br>

---

A Solutions Architect designed a real-time data analytics system based on Kinesis Data Stream and Lambda. A week after the system has been deployed, the users noticed that it performed slowly as the data rate increases. The Architect identified that the performance of the Kinesis Data Streams is causing this problem.

Which of the following should the Architect do to improve performance?
+ Increase the number of shards of the Kinesis stream by using the `UpdateShardCount` command.
+ Replace the data stream with Amazon Kinesis Data Firehose instead.
+ Improve the performance of the stream by decreasing the number of its shards using the `MergeShard` command.
+ Implement Step Scaling to the Kinesis Data Stream.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company has a VPC for its Human Resource department and another VPC located in different AWS regions for its Finance department. The Solutions Architect must redesign the architecture to allow the finance department to access all resources that are in the human resource department, and vice versa. An Intrusion Prevention System (IPS) must also be integrated for active traffic flow inspection and to block any vulnerability exploits.

Which network architecture design in AWS should the Solutions Architect set up to satisfy the above requirement?

+ Create a Traffic Policy in Amazon Route 53 to connect the two VPCs. Configure the Route 53 Resolver DNS Firewall to do active traffic flow inspection and block any vulnerability exploits.
+ Establish a secure connection between the two VPCs using a NAT Gateway. Manage user sessions via the AWS Systems Manager Session Manager service.
+ Create a Direct Connect Gateway and add VPC attachments to connect all departments. Configure AWS Security Hub to secure the application traffic travelling between the VPCs.
+ Launch an AWS Transit Gateway and add VPC attachments to connect all departments. Set up AWS Network Firewall to secure the application traffic travelling between the VPCs.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A top university has recently launched its online learning portal where the students can take e-learning courses from the comforts of their homes. The portal is on a large On-Demand EC2 instance with a single Amazon Aurora database.   

How can you improve the availability of your Aurora database to prevent any unnecessary downtime of the online portal?
+ Create Amazon Aurora Replicas.
+ Deploy Aurora to two Auto-Scaling groups of EC2 instances across two Availability Zones with an elastic load balancer which handles load balancing.
+ Enable Hash Joins to improve the database query performance.
+ Use an Asynchronous Key Prefetch in Amazon Aurora to improve the performance of queries that join tables across indexes.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A commercial bank has designed its next-generation online banking platform to use a distributed system architecture. As their Software Architect, you have to ensure that their architecture is highly scalable, yet still cost-effective. Which of the following will provide the most suitable solution for this scenario?
+ Launch multiple EC2 instances behind an Application Load Balancer to host your application services and SNS which will act as a highly-scalable buffer that stores messages as they travel between distributed applications.
+ Launch an Auto-Scaling group of EC2 instances to host your application services and an SQS queue. Include an Auto Scaling trigger to watch the SQS queue size which will either scale in or scale out the number of EC2 instances based on the queue.
+ Launch multiple EC2 instances behind an Application Load Balancer to host your application services, and SWF which will act as a highly-scalable buffer that stores messages as they travel between distributed applications.
+ Launch multiple On-Demand EC2 instances to host your application services and an SQS queue which will act as a highly-scalable buffer that stores messages as they travel between distributed applications.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company deployed a web application to an EC2 instance that adds a variety of photo effects to a picture uploaded by the users. The application will put the generated photos to an S3 bucket by sending PUT requests to the S3 API.

What is the best option for this scenario considering that you need to have API credentials to be able to send a request to the S3 API?
+ Encrypt the API credentials and store in any directory of the EC2 instance.
+ Create a role in IAM. Afterwards, assign this role to a new EC2 instance.
+ Store your API credentials in Amazon Glacier.
+ Store the API credentials in the root web application directory of the EC2 instance.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has several EC2 Reserved Instances in their account that need to be decommissioned and shut down since they are no longer used by the development team. However, the data is still required by the audit team for compliance purposes.

Which of the following steps can be taken in this scenario? (Select TWO.)

+ Convert the EC2 instance to On-Demand instances
+ You can opt to sell these EC2 instances on the AWS Reserved Instance Marketplace
+ Take snapshots of the EBS volumes and terminate the EC2 instances.
+ Convert the EC2 instances to Spot instances with a persistent Spot request type.
+ Stop all the running EC2 instances.

<details close>
<summary>Answer</summary>
b,c
</details>

<br>

---

A Solutions Architect is working for a weather station in Asia with a weather monitoring system that needs to be migrated to AWS. Since the monitoring system requires a low network latency and high network throughput, the Architect decided to launch the EC2 instances to a new cluster placement group. The system was working fine for a couple of weeks, however, when they try to add new instances to the placement group that already has running EC2 instances, they receive an 'insufficient capacity error'.

How will the Architect fix this issue?
+ Stop and restart the instances in the Placement Group and then try the launch again.
+ Create another Placement Group and launch the new instances in the new group.
+ Verify all running instances are of the same size and type and then try the launch again.
+ Submit a capacity increase request to AWS as you are initially limited to only 12 instances per Placement Group.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company is looking for a way to analyze the calls between customers and service agents. Each conversation is transcribed, JSON-formatted, and saved to an Amazon S3 bucket. The company’s solutions architect is tasked to design a solution for extracting and visualizing sentiments from the transcribed files.

Which solution meets the requirements while minimizing the amount of operational overhead?

+ Create an Amazon Comprehend analysis job. Index the sentiment along with the transcript to an Amazon OpenSearch cluster. Visualize the results using the OpenSearch Dashboard.
+ Analyze the JSON files with Amazon Textract. Index the sentiment along with the transcript to an Amazon OpenSearch cluster. Visualize the results using Amazon Managed Grafana.
+ Create an Amazon Comprehend analysis job. Index the sentiment along with the transcript to an Amazon OpenSearch cluster. Visualize the results using Amazon Managed Grafana.
+ Train a custom Natural Language Processing (NLP) model using Amazon SageMaker. Index the sentiment along with the transcript to an Amazon OpenSearch cluster. Visualize the results using the OpenSearch Dashboard.

<details close>
<summary>Answer</summary>
a
</details>

<br>


<details close>
<summary>Note</summary>
Amazon Comprehend uses machine learning to help you uncover the insights and relationships in your unstructured data. The service identifies the language of the text; extracts key phrases, places, people, brands, or events; understands how positive or negative the text is; analyzes text using tokenization and parts of speech, and automatically organizes a collection of text files by topic. You can also use AutoML capabilities in Amazon Comprehend to build a custom set of entities or text classification models that are tailored uniquely to your organization’s needs.

Amazon Textract is just an AI service used to extract text data from scanned documents in PNG, JPEG, TIFF, PDF formats and is not capable of running sentiment analysis. 

Furthermore, Grafana is more suited for the visualization of time-series data such as system metrics (CPU load, disk storage, memory utilization, temperature, etc)
</details>

---

An intelligence agency is currently hosting a learning and training portal in AWS. Your manager instructed you to launch a large EC2 instance with an attached EBS Volume and enable Enhanced Networking. What are the valid case scenarios in using Enhanced Networking? (Select TWO.)
+ When you need a higher packet per second (PPS) performance
+ When you need a low packet-per-second performance
+ When you need high latency networking
+ When you need a consistently lower inter-instance latencies
+ When you need a dedicated connection to your on-premises data center  

<details close>
<summary>Answer</summary>
a,d
</details>

<br>

---

There is a technical requirement by a financial firm that does online credit card processing to have a secure application environment on AWS. They are trying to decide on whether to use KMS or CloudHSM.

Which of the following statements is right when it comes to CloudHSM and KMS?
+ No major difference. They both do the same thing.
+ If you want a managed service for creating and controlling your encryption keys but don't want or need to operate your own HSM, consider using AWS CloudHSM.
+ You should consider using AWS CloudHSM over AWS KMS if you require your keys stored in dedicated, third-party validated hardware security modules under your exclusive control.
+ AWS CloudHSM should always be used for any payment transactions.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A Solutions Architect created a brand new IAM User with a default setting using AWS CLI. This is intended to be used to send API requests to Amazon S3, DynamoDB, Lambda, and other AWS resources of the company’s cloud infrastructure.

Which of the following must be done to allow the user to make API calls to the AWS resources?

+ Do nothing as the IAM User is already capable of sending API calls to your AWS resources.   
+ Enable Multi-Factor Authentication for the user.
+ Assign an IAM Policy to the user to allow it to send API calls.  
+ Create a set of Access Keys for the user and attach the necessary permissions.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A tech company is running two production web servers hosted on Reserved EC2 instances with EBS-backed root volumes. These instances have a consistent CPU load of 90%. Traffic is being distributed to these instances by an Elastic Load Balancer. In addition, they also have Multi-AZ RDS MySQL databases for their production, test, and development environments. 

What recommendation would you make to reduce cost in this AWS environment without affecting availability and performance of mission-critical systems? Choose the best answer.
+ Consider using On-demand instances instead of Reserved EC2 instances
+ Consider not using a Multi-AZ RDS deployment for the development and test database
+ Consider using Spot instances instead of reserved EC2 instances
+ Consider removing the Elastic Load Balancer

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company launched a cryptocurrency mining server on a Reserved EC2 instance in us-east-1 region's private subnet that uses IPv6. Due to the financial data that the server contains, the system should be secured to prevent any unauthorized access and to meet the regulatory compliance requirements.

In this scenario, which VPC feature allows the EC2 instance to communicate to the Internet but prevents inbound traffic?
+ NAT Gateway
+ NAT instances
+ Egress-only Internet gateway
+ Internet Gateway

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company is planning to deploy a High Performance Computing (HPC) cluster in its VPC that requires a scalable, high-performance file system. The storage service must be optimized for efficient workload processing, and the data must be accessible via a fast and scalable file system interface. It should also work natively with Amazon S3 that enables you to easily process your S3 data with a high-performance POSIX interface.

Which of the following is the MOST suitable service that you should use for this scenario?

+ Amazon Elastic File System (EFS)
+ Amazon FSx for Windows File Server
+ Amazon FSx for Lustre
+ Amazon Elastic Block Storage (EBS)

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
Amazon FSx for Lustre works natively with Amazon S3, making it easy for you to process cloud data sets with high-performance file systems.

Although the EFS service can be used for HPC applications, it doesn't natively work with Amazon S3. It doesn't have the capability to easily process your S3 data with a high-performance POSIX interface, unlike Amazon FSx for Lustre.
</details>

---

A company has a fleet of running Spot EC2 instances behind an Application Load Balancer. The incoming traffic comes from various users across multiple AWS regions and you would like to have the user's session shared among the fleet of instances. You are required to set up a distributed session management layer that will provide a scalable and shared data storage for the user sessions.

Which of the following would be the best choice to meet the requirement while still providing sub-millisecond latency for the users?

+ ELB sticky sessions
+ Multi-master DynamoDB
+ Multi-AZ RDS
+ ElastiCache in-memory caching

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A startup is building IoT devices and monitoring applications. They are using IoT sensors to monitor the traffic in real-time by using an Amazon Kinesis Stream that is configured with default settings. It then sends the data to an Amazon S3 bucket every 3 days. When you checked the data in S3 on the 3rd day, only the data for the last day is present and no data is present from 2 days ago.

Which of the following is the MOST likely cause of this issue?
+ Amazon S3 bucket has encountered a data loss.
+ Someone has manually deleted the record in Amazon S3.
+ By default, data records in Kinesis are only accessible for 24 hours from the time they are added to a stream.
+ The access of the Kinesis stream to the S3 bucket is insufficient.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company has an application that uses multiple EC2 instances located in various AWS regions such as US East (Ohio), US West (N. California), and EU (Ireland). The manager instructed the Solutions Architect to set up a latency-based routing to route incoming traffic for www.tutorialsdojo.com to all the EC2 instances across all AWS regions.

Which of the following options can satisfy the given requirement?
+ Use a Network Load Balancer to distribute the load to the multiple EC2 instances across all AWS Regions.
+ Use Route 53 to distribute the load to the multiple EC2 instances across all AWS Regions.
+ Use an Application Load Balancer to distribute the load to the multiple EC2 instances across all AWS Regions.
+ Use AWS DataSync to distribute the load to the multiple EC2 instances across all AWS Regions.


<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A new DevOps engineer has created a CloudFormation template for a web application and she raised a `<code>pull request</code>` in GIT for you to check and review. After checking the template, you immediately told her that the template will not work. Which of the following is the reason why this CloudFormation template will fail to deploy the stack?
```json
{
 "AWSTemplateFormatVersion":"2010-09-09",
 "Parameters":{
   "VPCId":{
     "Type":"String",
     "Description":"manila"
 },
 "SubnetId":{
   "Type":"String",
   "Description":"subnet-b46032ec"
 }
},
"Outputs":{
 "InstanceId":{
  "Value":{
   "Ref":"manilaInstance"
  },
  "Description":"Instance Id"
  }
 }
}
```

+ The value of the `AWSTemplateFormatVersion` is incorrect. It should be 2017-06-06.
+ The `Resources` section is missing.
+ An invalid section named `Parameters` is present. This will cause the CloudFormation stack to fail.
+ The `Conditions` section is missing.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---
A company is running an on-premises application backed by a 1TB MySQL 8.0 database. A couple of times each month, the production data is fully copied to a staging database at the request of the analytics team. The team can't work on the staging database until the copy is finished, which takes hours.

Throughout this period, the application experiences intermittent downtimes as well. To expedite the process for the analytics team, a solutions architect must redesign the application's architecture in AWS. The application must also be highly resilient to disruptions.

Which combination of actions best satisfies the given set of requirements while being the most cost-effective? (Select TWO)

+ Use an Amazon Aurora database with Multi-AZ Replicas.
+ Use an Amazon RDS database in a Multi-AZ Deployments configuration
+ Take a manual snapshot and restore it to a database in the staging environment.
+ Replicate the production database to a staging database using the `mysqldump` client utility
+ Clone the production database in the staging environment using Aurora cloning.

<details close>
<summary>Answer</summary>
a,e
</details>

<br>

---

An application is hosted in an Auto Scaling group of EC2 instances and a Microsoft SQL Server on Amazon RDS. There is a requirement that all in-flight data between your web servers and RDS should be secured.

Which of the following options is the MOST suitable solution that you should implement? (Select TWO.)
+ Force all connections to your DB instance to use SSL by setting the `rds.force_ssl` parameter to true. Once done, reboot your DB instance.
+ Download the Amazon RDS Root CA certificate. Import the certificate to your servers and configure your application to use SSL to encrypt the connection to RDS.
+ Specify the TDE option in an RDS option group that is associated with that DB instance to enable transparent data encryption (TDE). 
+ Enable the IAM DB authentication in RDS using the AWS Management Console.
+ Configure the security groups of your EC2 instances and RDS to only allow traffic to and from port 443.

<details close>
<summary>Answer</summary>
a,b
</details>

<br>

---

A Solutions Architect needs to launch a web application that will be served globally using Amazon CloudFront. The application is hosted in an Amazon EC2 instance which will be configured as the origin server to process and serve dynamic content to its customers.

Which of the following options provides high availability for the application?
+ Use Amazon S3 to serve the dynamic content of your web application and configure the S3 bucket to be part of an origin group.
+ Launch an Auto Scaling group of EC2 instances and configure it to be part of an origin group.
+ Provision two EC2 instances deployed in different Availability Zones and configure them to be part of an origin group.
+ Use Lambda@Edge to improve the performance of your web application and ensure high availability. Set the Lambda@Edge functions to be part of an origin group.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A software development company has hundreds of Amazon EC2 instances with multiple Application Load Balancers (ALBs) across multiple AWS Regions. The public applications hosted in their EC2 instances are accessed on their on-premises network. The company needs to reduce the number of IP addresses that it needs to regularly whitelist on the corporate firewall device.

Which of the following approach can be used to fulfill this requirement?
+ Use AWS Global Accelerator and create an endpoint group for each AWS Region. Associate the Application Load Balancer from each region to the corresponding endpoint group.
+ Use AWS Global Accelerator and create multiple endpoints for all the available AWS Regions. Associate all the private IP addresses of the EC2 instances to the corresponding endpoints.
+ Create a new Lambda function that tracks the changes in the IP addresses of all ALBs across multiple AWS Regions. Schedule the function to run and update the corporate firewall every hour using Amazon CloudWatch Events.
+ Launch a Network Load Balancer with an associated Elastic IP address. Set the ALBs in multiple Regions as targets.

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
AWS Global Accelerator is a service that improves the availability and performance of your applications with local or global users. It provides static IP addresses that act as a fixed entry point to your application endpoints in a single or multiple AWS Regions, such as your Application Load Balancers, Network Load Balancers, or Amazon EC2 instances.
</details>

<br>

---

A company plans to use a cloud storage service to temporarily store its log files. The number of files to be stored is still unknown, but it only needs to be kept for 12 hours.

Which of the following is the most cost-effective storage class to use in this scenario?
+ Amazon S3 Standard
+ Amazon S3 One Zone-IA
+ Amazon S3 Standard-IA
+ Amazon S3 Glacier Deep Archive


<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
The scenario requires you to select a cost-effective service that does not have a minimum storage duration since the data will only last for 12 hours. Among the options given, only Amazon S3 Standard has the feature of no minimum storage duration. It is also the most cost-effective storage service because you will only be charged for the last 12 hours, unlike in other storage classes where you will still be charged based on its respective storage duration (e.g. 30 days, 90 days, 180 days). S3 Intelligent-Tiering also has no minimum storage duration and this is designed for data with changing or unknown access patters.
</details>

<br>

---

A Solutions Architect is managing a three-tier web application that processes credit card payments and online transactions. Static web pages are used on the front-end tier while the application tier contains a single Amazon EC2 instance that handles long-running processes. The data is stored in a MySQL database. The Solutions Architect is instructed to decouple the tiers to create a highly available application.

Which of the following options can satisfy the given requirement?
+ Move all the static assets and web pages to Amazon CloudFront. Use Auto Scaling in Amazon EC2 instance. Migrate the database to Amazon RDS with Multi-AZ deployments configuration.
+ Move all the static assets, web pages, and the backend application to a larger instance. Use Auto Scaling in Amazon EC2 instance. Migrate the database to Amazon Aurora.
+ Move all the static assets to Amazon S3. Set concurrency limit in AWS Lambda to move the application to a serverless architecture. Migrate the database to Amazon DynamoDB.
+ Move all the static assets and web pages to Amazon S3. Re-host the application to Amazon Elastic Container Service (Amazon ECS) containers and enable Service Auto Scaling. Migrate the database to Amazon RDS with Multi-AZ deployments configuration.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A company plans to design an application that can handle batch processing of large amounts of financial data. The Solutions Architect is tasked to create two Amazon S3 buckets to store the input and output data. The application will transfer the data between multiple EC2 instances over the network to complete the data processing.

Which of the following options would reduce the data transfer costs?
+ Deploy the Amazon EC2 instances behind an Application Load Balancer.
+ Deploy the Amazon EC2 instances in the same Availability Zone.
+ Deploy the Amazon EC2 instances in the same AWS Region.
+ Deploy the Amazon EC2 instances in private subnets in different Availability Zones.

<details close>
<summary>Answer</summary>
b
</details>

<br>


<details close>
<summary>Note</summary>
In this scenario, you should deploy all the EC2 instances in the same Availability Zone. If you recall, data transferred between Amazon EC2, Amazon RDS, Amazon Redshift, Amazon ElastiCache instances, and Elastic Network Interfaces in the same Availability Zone is free. Instead of using the public network to transfer the data, you can use the private network to reduce the overall data transfer costs.
</details>

<br>

---
A company has several unencrypted EBS snapshots in their VPC. The Solutions Architect must ensure that all of the new EBS volumes restored from the unencrypted snapshots are automatically encrypted.

What should be done to accomplish this requirement?

+ Enable the EBS Encryption By Default feature for specific EBS volumes.
+ Launch new EBS volumes and specify the symmetric customer master key (CMK) for encryption.
+ Enable the EBS Encryption By Default feature for the AWS Region.
+ Launch new EBS volumes and encrypt them using an asymmetric customer master key (CMK).

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company is using an Amazon RDS for MySQL 5.6 with Multi-AZ deployment enabled and several web servers across two AWS Regions. The database is currently experiencing highly dynamic reads due to the growth of the company’s website. The Solutions Architect tried to test the read performance from the secondary AWS Region and noticed a notable slowdown on the SQL queries.

Which of the following options would provide a read replication latency of less than 1 second?
+ Migrate the existing database to Amazon Aurora and create a cross-region read replica.
+ Upgrade the MySQL database engine.
+ Use Amazon ElastiCache to improve database performance.
+ Create an Amazon RDS for MySQL read replica in the secondary AWS Region.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A website hosted on Amazon ECS container instances loads slowly during peak traffic, affecting its availability. Currently, the container instances are run behind an Application Load Balancer, and CloudWatch alarms are configured to send notifications to the operations team if there is a problem in availability so they can scale out if needed. A solutions architect needs to create an automatic scaling solution when such problems occur.

Which solution could satisfy the requirement? (Select TWO.)
+ Create an AWS Auto Scaling policy that scales out an ECS service when the ALB endpoint becomes unreachable.
+ Create an AWS Auto Scaling policy that scales out the ECS service when the ALB hits a high CPU utilization.
+ Create an AWS Auto Scaling policy that scales out the ECS cluster when the ALB target group’s CPU utilization is too high.
+ Create an AWS Auto Scaling policy that scales out the ECS service when the service’s memory utilization is too high.
+ Create an AWS Auto Scaling policy that scales out the ECS cluster when the cluster’s CPU utilization is too high.

<details close>
<summary>Answer</summary>
d,e
</details>

<details close>
<summary>Note</summary>
CPU Utilization

Disk Reads

Disk Read Operations

Disk Writes

Disk Write Operations

Network In

Network Out

Status Check Failed (Any)

Status Check Failed (Instance)

Status Check Failed (System)

The following metrics are available for ECS Service:

ECSServiceAverageCPUUtilization—Average CPU utilization of the service.

ECSServiceAverageMemoryUtilization—Average memory utilization of the service.

ALBRequestCountPerTarget—Number of requests completed per target in an Application Load Balancer target group.


</details>

<br>

---

A Solutions Architect is implementing a new High-Performance Computing (HPC) system in AWS that involves orchestrating several Amazon Elastic Container Service (Amazon ECS) tasks with an EC2 launch type that is part of an Amazon ECS cluster. The system will be frequently accessed by users around the globe and it is expected that there would be hundreds of ECS tasks running most of the time. The Architect must ensure that its storage system is optimized for high-frequency read and write operations. The output data of each ECS task is around 10 MB but the obsolete data will eventually be archived and deleted so the total storage size won’t exceed 10 TB.

Which of the following is the MOST suitable solution that the Architect should recommend?
+ Launch an Amazon Elastic File System (Amazon EFS) with Provisioned Throughput mode and set the performance mode to  
+ Set up an SMB file share by creating an Amazon FSx File Gateway in Storage Gateway. Set the file share as the container mount point in the ECS task definition of the Amazon ECS cluster.
+ Launch an Amazon Elastic File System (Amazon EFS) file system with Bursting Throughput mode and set the performance mode to `General Purpose`. Configure the EFS file system as the container mount point in the ECS task definition of the Amazon ECS cluster.
+ Launch an Amazon DynamoDB table with Amazon DynamoDB Accelerator (DAX) and DynamoDB Streams enabled. Configure the table to be accessible by all Amazon ECS cluster instances. Set the DynamoDB table as the container mount point in the ECS task definition of the Amazon ECS cluster.

<details close>
<summary>Answer</summary>
a
</details>

---

An airline company receives a lot of requests to book flights, update booking details, and flight check-ins. Since these requests flood the customer support teams, the management wants to build a self-service solution that can handle these requests without a human agent. This solution should be text-based wherein users can type their concerns in a chat box and an AI will analyze their intention, provide answers, or fulfill pre-defined actions automatically.

Which of the following options is the recommended solution for the above requirements?

+ Create a conversational chatbot using Amazon Comprehend for natural-language processing (NLU). Depending on the user’s intent, invoke AWS Lambda functions that can perform the needed actions.
+ Work with an AWS Managed Service Provider (MSP) to deploy a conversational chatbot using Amazon Polly for natural-language processing (NLU). Integrate AWS Lambda functions as code hooks to perform actions based on user requests.
+ Deploy a conversational chatbot using Amazon Lex. Define conversation flow for specific user intentions. Integrate AWS Lambda functions as code hooks to perform actions based on user requests.
+ Deploy a conversational chatbot using Amazon Rekognition. Define conversation flow for specific user intentions. Create AWS Lambda functions that can be invoked depending on user intentions.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
Amazon Lex enables you to build applications using a speech or text interface powered by the same technology that powers Amazon Alexa. Amazon Lex provides the deep functionality and flexibility of natural language understanding (NLU) and automatic speech recognition (ASR), so you can build highly engaging user experiences with lifelike conversational interactions and create new categories of products.

Amazon Lex enables any developer to build conversational chatbots quickly. With Amazon Lex, no deep learning expertise is necessary—to create a bot, you just specify the basic conversation flow in the Amazon Lex console. The console provides a graphical user interface that you use to build a production-ready bot for your application.


</details>

---

A company has several websites and hosts its infrastructure on the AWS Cloud. The mission-critical web applications are hosted on fleets of Amazon EC2 instances behind Application Load Balancers. The company uses AWS Certificate Manager (ACM) provided certificate on the ALBs to enable HTTPS access on its websites. The security team wants to get notified 30 days before the expiration of the SSL certificates.

Which of the following can the Solutions Architect implement to meet this request? (Select TWO.)

+ Use AWS Config to manually create a rule that checks for certificate expiry on ACM. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to send an alert to an Amazon Simple Notification Service (Amazon SNS) topic when AWS Config flags a resource.
+ Create an Amazon EventBridge (Amazon CloudWatch Events) rule that will check AWS Health or ACM expiration events related to ACM certificates. Send an alert notification to an Amazon Simple Notification Service (Amazon SNS) topic when a certificate is going to expire in 30 days.
+ Modify all certificates to use the AWS Certificate Manager Private Certificate Authority. Create an Amazon EventBridge (Amazon CloudWatch Events) rule that will check for ACM events that shows certificates expiring within 30 days. Set the target to invoke an AWS Lambda function to send a message to an Amazon SNS topic.
+ Utilize AWS Trusted Advisor to check for the ACM certificates that will expire in 30 days. Using this metric, create an Amazon CloudWatch alarm that will send an alert to an AWS Systems Manager OpsItem.
+ Create an Amazon EventBridge (Amazon CloudWatch Events) rule and schedule it to run every day to identify the expiring ACM certificates. Configure to rule to check the `DaysToExpiry` metric of all ACM certificates in Amazon CloudWatch. Send an alert notification to an Amazon Simple Notification Service (Amazon SNS) topic when a certificate is going to expire in 30 days.

<details close>
<summary>Answer</summary>
b,e
</details>

