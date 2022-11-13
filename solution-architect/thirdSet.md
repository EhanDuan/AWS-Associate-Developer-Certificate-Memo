# Solution Architect Exam#2 Practice Set

A Solutions Architect needs to deploy a mobile application that collects votes for a singing competition. Millions of users from around the world will submit votes using their mobile phones. These votes must be collected and stored in a highly scalable and highly available database which will be queried for real-time ranking. The database is expected to undergo frequent schema changes throughout the voting period.

Which of the following combination of services should the architect use to meet this requirement?
+ Amazon DynamoDB and AWS AppSync
+ Amazon DocumentDB (with MongoDB compatibility) and Amazon AppFlow
+ Amazon Relational Database Service (RDS) and Amazon MQ
+ Amazon Aurora and Amazon Cognito 

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
DynamoDB is durable, scalable, and highly available data store which can be used for real-time tabulation. You can also use AppSync with DynamoDB to make it easy for you to build collaborative apps that keep shared data updated in real-time. You just specify the data for your app with simple code statements and AWS AppSync manages everything needed to keep the app data updated in real-time. This will allow your app to access data in Amazon DynamoDB, trigger AWS Lambda functions, or run Amazon Elasticsearch queries and combine data from these services to provide the exact data you need for your app.
</details>

<br>

---

A solutions architect is writing an AWS Lambda function that will process encrypted documents from an Amazon FSx for NetApp ONTAP file system. The documents are protected by an AWS KMS customer key. After processing the documents, the Lambda function will store the results in an S3 bucket with an Amazon S3 Glacier Flexible Retrieval storage class. The solutions architect must ensure that the files can be decrypted by the Lambda function.

Which action accomplishes the requirement?
+ Attach the `kms:decrypt` permission to the Lambda function’s execution role. Add a statement to the AWS KMS key’s policy that grants the function’s execution role the `kms:decrypt`  permission.
+ Attach the `kms:decrypt` permission to the Lambda function’s resource policy. Add a statement to the AWS KMS key’s policy that grants the function’s resource policy ARN the `kms:decrypt` permission.
+ Attach the `kms:decrypt`  permission to the Lambda function’s execution role. Add a statement to the AWS KMS key’s policy that grants the function’s ARN the `kms:decrypt` permission.
+ Attach the `kms:decrypt`  permission to the Lambda function’s resource policy. Add a statement to the AWS KMS key’s policy that grants the function’s execution role the `kms:decrypt` permission.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A Solutions Architect is managing a company's AWS account of approximately 300 IAM users. They have a new company policy that requires changing the associated permissions of all 100 IAM users that control the access to Amazon S3 buckets.

What will the Solutions Architect do to avoid the time-consuming task of applying the policy to each user?
+ Create a new IAM group and then add the users that require access to the S3 bucket. Afterward, apply the policy to the IAM group.
+ Create a new policy and apply it to multiple IAM users using a shell script.
+ Create a new S3 bucket access policy with unlimited access for each IAM user.
+ Create a new IAM role and add each user to the IAM role.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A Solutions Architect for a global news company is configuring a fleet of EC2 instances in a subnet that currently is in a VPC with an Internet gateway attached. All of these EC2 instances can be accessed from the Internet. The architect launches another subnet and deploys an EC2 instance in it, however, the architect is not able to access the EC2 instance from the Internet.

What could be the possible reasons for this issue? (Select TWO.)
+ The Amazon EC2 instance does not have a public IP address associated with it.
+ The Amazon EC2 instance is not a member of the same Auto Scaling group.
+ The Amazon EC2 instance does not have an attached Elastic Fabric Adapter (EFA).
+ The route table is not configured properly to send traffic from the EC2 instance to the Internet through the Internet gateway.
+ The route table is not configured properly to send traffic from the EC2 instance to the Internet through the customer gateway (CGW).

<details close>
<summary>Answer</summary>
a,d
</details>

<br>

---

A data analytics company is setting up an innovative checkout-free grocery store. Their Solutions Architect developed a real-time monitoring application that uses smart sensors to collect the items that the customers are getting from the grocery’s refrigerators and shelves then automatically deduct it from their accounts. The company wants to analyze the items that are frequently being bought and store the results in S3 for durable storage to determine the purchase behavior of its customers.

What service must be used to easily capture, transform, and load streaming data into Amazon S3, Amazon Elasticsearch Service, and Splunk?
+ Amazon Kinesis Data Firehose
+ Amazon Kinesis
+ Amazon Redshift
+ Amazon SQS

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A tech startup is launching an on-demand food delivery platform using Amazon ECS cluster with an AWS Fargate serverless compute engine and Amazon Aurora. It is expected that the database read queries will significantly increase in the coming weeks ahead. A Solutions Architect recently launched two Read Replicas to the database cluster to improve the platform's scalability.

Which of the following is the MOST suitable configuration that the Architect should implement to load balance all of the incoming read requests equally to the two Read Replicas?
+ Use the built-in Reader endpoint of the Amazon Aurora database.
+ Use the built-in Cluster endpoint of the Amazon Aurora database.
+ Enable Amazon Aurora Parallel Query.
+ Create a new Network Load Balancer to evenly distribute the read queries to the Read Replicas of the Amazon Aurora database.

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
A reader endpoint for an Aurora DB cluster provides load-balancing support for read-only connections to the DB cluster. Use the reader endpoint for read operations, such as queries. By processing those statements on the read-only Aurora Replicas, this endpoint reduces the overhead on the primary instance. It also helps the cluster to scale the capacity to handle simultaneous SELECT queries, proportional to the number of Aurora Replicas in the cluster. Each Aurora DB cluster has one reader endpoint.
</details>

<br>

---

A manufacturing company has EC2 instances running in AWS. The EC2 instances are configured with Auto Scaling. There are a lot of requests being lost because of too much load on the servers. The Auto Scaling is launching new EC2 instances to take the load accordingly yet, there are still some requests that are being lost.

Which of the following is the MOST suitable solution that you should implement to avoid losing recently submitted requests?
+ Use an Amazon SQS queue to decouple the application components and scale-out the EC2 instances based upon the `ApproximateNumberOfMessages`  metric in Amazon CloudWatch.
+ Replace the Auto Scaling group with a cluster placement group to achieve a low-latency network performance necessary for tightly-coupled node-to-node communication.
+ Use larger instances for your application with an attached Elastic Fabric Adapter (EFA).
+ Set up Amazon Aurora Serverless for on-demand, auto-scaling configuration of your EC2 Instances and also enable Amazon Aurora Parallel Query feature for faster analytical queries over your current data.
<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company is using multiple AWS accounts that are consolidated using AWS Organizations. They want to copy several S3 objects to another S3 bucket that belonged to a different AWS account which they also own. The Solutions Architect was instructed to set up the necessary permissions for this task and to ensure that the destination account owns the copied objects and not the account it was sent from.

How can the Architect accomplish this requirement?
+ Enable the Requester Pays feature in the source S3 bucket. The fees would be waived through Consolidated Billing since both AWS accounts are part of AWS Organizations.
+ Configure cross-account permissions in S3 by creating an IAM customer-managed policy that allows an IAM user or role to copy objects from the source bucket in one account to the destination bucket in the other account. Then attach the policy to the IAM user or role that you want to use to copy objects between accounts.
+ Set up cross-origin resource sharing (CORS) in S3 by creating a bucket policy that allows an IAM user or role to copy objects from the source bucket in one account to the destination bucket in the other account.
+ Connect the two S3 buckets from two different AWS accounts to Amazon WorkDocs. Set up cross-account access to integrate the two S3 buckets. Use the Amazon WorkDocs console to copy the objects from one account to the other with modified object ownership assigned to the destination account.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company plans to set up a cloud infrastructure in AWS. In the planning, it was discussed that you need to deploy two EC2 instances that should continuously run for three years. The CPU utilization of the EC2 instances is also expected to be stable and predictable.

Which is the most cost-efficient Amazon EC2 Pricing type that is most appropriate for this scenario?
+ Reserved Instances
+ On-Demand instances
+ Spot instances
+ Dedicated Hosts

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company deployed a high-performance computing (HPC) cluster that spans multiple EC2 instances across multiple Availability Zones and processes various wind simulation models. Currently, the Solutions Architect is experiencing a slowdown in their applications and upon further investigation, it was discovered that it was due to latency issues.

Which is the MOST suitable solution that the Solutions Architect should implement to provide low-latency network performance necessary for tightly-coupled node-to-node communication of the HPC cluster?
+ Set up a spread placement group across multiple Availability Zones in multiple AWS Regions.
+ Set up AWS Direct Connect connections across multiple Availability Zones for increased bandwidth throughput and more consistent network experience.
+ Use EC2 Dedicated Instances.
+ Set up a cluster placement group within a single Availability Zone in the same AWS Region.

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>

Cluster – packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications.

Partition – spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka.

Spread – strictly places a small group of instances across distinct underlying hardware to reduce correlated failures.

Cluster placement groups are recommended for applications that benefit from low network latency, high network throughput, or both. They are also recommended when the majority of the network traffic is between the instances in the group. To provide the lowest latency and the highest packet-per-second network performance for your placement group, choose an instance type that supports enhanced networking.

</details>

<br>

---

A company installed sensors to track the number of people who visit the park. The data is sent every day to an Amazon Kinesis stream with default settings for processing, in which a consumer is configured to process the data every other day. You noticed that the S3 bucket is not receiving all of the data that is being sent to the Kinesis stream. You checked the sensors if they are properly sending the data to Amazon Kinesis and verified that the data is indeed sent every day.

What could be the reason for this?
+ There is a problem in the sensors. They probably had some intermittent connection hence, the data is not sent to the stream.
+ By default, Amazon S3 stores the data for 1 day and moves it to Amazon Glacier.
+ Your AWS account was hacked and someone has deleted some data in your Kinesis stream.
+ By default, the data records are only accessible for 24 hours from the time they are added to a Kinesis stream.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

You are automating the creation of EC2 instances in your VPC. Hence, you wrote a python script to trigger the Amazon EC2 API to request 50 EC2 instances in a single Availability Zone. However, you noticed that after 20 successful requests, subsequent requests failed.

What could be a reason for this issue and how would you resolve it?
+ There was an issue with the Amazon EC2 API. Just resend the requests and these will be provisioned successfully.
+ By default, AWS allows you to provision a maximum of 20 instances per region. Select a different region and retry the failed request.
+ By default, AWS allows you to provision a maximum of 20 instances per Availability Zone. Select a different Availability Zone and retry the failed request.
+ There is a vCPU-based On-Demand Instance limit per region which is why subsequent requests failed. Just submit the limit increase form to AWS and retry the failed requests once approved.

<details close>
<summary>Answer</summary>
d
</details>

---
A large insurance company has an AWS account that contains three VPCs (DEV, UAT and PROD) in the same region. UAT is peered to both PROD and DEV using a VPC peering connection. All VPCs have non-overlapping CIDR blocks. The company wants to push minor code releases from Dev to Prod to speed up time to market.

Which of the following options helps the company accomplish this?
+ Create a new VPC peering connection between PROD and DEV with the appropriate routes.
+ Create a new entry to PROD in the DEV route table using the VPC peering connection as the target.
+ Change the DEV and PROD VPCs to have overlapping CIDR blocks to be able to connect them.
+ Do nothing. Since these two VPCs are already connected via UAT, they already have a connection to each other.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

An on-premises server uses an SMB network file share to store application data. The application produces around 50 MB of data per day, but it only needs to access some of it for daily processes. To save on storage costs, the company plans to copy all the application data to AWS, however, they want to retain the ability to retrieve data with the same low-latency access as the local file share. The company does not have the capacity to develop the needed tool for this operation.

Which AWS service should the company use?
+ AWS Virtual Private Network (VPN)
+ Amazon FSx for Windows File Server
+ AWS Snowball Edge
+ AWS Storage Gateway

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A company is generating confidential data that is saved on their on-premises data center. As a backup solution, the company wants to upload their data to an Amazon S3 bucket. In compliance with its internal security mandate, the encryption of the data must be done before sending it to Amazon S3. The company must spend time managing and rotating the encryption keys as well as controlling who can access those keys.

Which of the following methods can achieve this requirement? (Select TWO.)
+ Set up Server-Side Encryption with keys stored in a separate S3 bucket.
+ Set up Client-Side Encryption with a customer master key stored in AWS Key Management Service (AWS KMS).
+ Set up Client-Side Encryption with Amazon S3 managed encryption keys.
+ Set up Server-Side Encryption (SSE) with EC2 key pair.
+ Set up Client-Side Encryption using a client-side master key.

<details close>
<summary>Answer</summary>
b,e
</details>

<br>

---

An investment bank is working with an IT team to handle the launch of the new digital wallet system. The applications will run on multiple EBS-backed EC2 instances which will store the logs, transactions, and billing statements of the user in an S3 bucket. Due to tight security and compliance requirements, the IT team is exploring options on how to safely store sensitive data on the EBS volumes and S3.

Which of the below options should be carried out when storing sensitive data on AWS? (Select TWO.)
+ Create an EBS Snapshot
+ Enable EBS Encryption
+ Migrate the EC2 instances from the public to private subnet.
+ Enable Amazon S3 Server-Side or use Client-Side Encryption
+ Use AWS Shield and WAF

<details close>
<summary>Answer</summary>
b,d
</details>

<br>

---

A document sharing website is using AWS as its cloud infrastructure. Free users can upload a total of 5 GB data while premium users can upload as much as 5 TB. Their application uploads the user files, which can have a max file size of 1 TB, to an S3 Bucket.

In this scenario, what is the best way for the application to upload the large files in S3?
+ Use a single PUT request to upload the large file
+ Use AWS Snowball
+ Use AWS Import/Export
+ Use Multipart Upload

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A Solutions Architect is designing a highly available environment for an application. She plans to host the application on EC2 instances within an Auto Scaling Group. One of the conditions requires data stored on root EBS volumes to be preserved if an instance terminates.

What should be done to satisfy the requirement?

+ Use AWS DataSync to replicate root volume data to Amazon S3.
+ Set the value of `DeleteOnTermination`  attribute of the EBS volumes to `False`
+ Configure ASG to suspend the health check process for each EC2 instance.
+ Enable the Termination Protection option for all EC2 instances.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company needs to collect gigabytes of data per second from websites and social media feeds to gain insights into its product offerings and continuously improve the user experience. To meet this design requirement, an application is deployed on an Auto Scaling group of Spot EC2 instances which processes the data and stores the results to DynamoDB and Redshift. The solution should have a built-in enhanced fan-out feature.

Which fully-managed AWS service can you use to collect and process large streams of data records in real-time with the LEAST amount of administrative overhead?
+ Amazon S3 Access Points
+ AWS Data Exchange
+ Amazon Managed Streaming for Apache Kafka (Amazon MSK)
+ Amazon Kinesis Data Streams

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A solutions architect is managing an application that runs on a Windows EC2 instance with an attached Amazon FSx for Windows File Server. To save cost, management has decided to stop the instance during off-hours and restart it only when needed. It has been observed that the application takes several minutes to become fully operational which impacts productivity.

How can the solutions architect speed up the instance’s loading time without driving the cost up?
+ Migrate the application to a Linux-based EC2 instance.
+ Migrate the application to an EC2 instance with hibernation enabled.
+ Enable the hibernation mode on the EC2 instance.
+ Disable the Instance Metadata Service to reduce the things that need to be loaded at startup.

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
Enable the hibernation mode on the EC2 instance is incorrect. It is not possible to enable or disable hibernation for an instance after it has been launched.

</details>

<br>

---

A FinTech startup deployed an application on an Amazon EC2 instance with attached Instance Store volumes and an Elastic IP address. The server is only accessed from 8 AM to 6 PM and can be stopped from 6 PM to 8 AM for cost efficiency using Lambda with the script that automates this based on tags.

Which of the following will occur when the EC2 instance is stopped and started? (Select TWO.)
+ The underlying host for the instance is possibly changed.
+ The ENI (Elastic Network Interface) is detached.
+ All data on the attached instance-store devices will be lost.
+ The Elastic IP address is disassociated with the instance.
+ There will be no changes.

<details close>
<summary>Answer</summary>
a,c
</details>

<br>

---

An online stocks trading application that stores financial data in an S3 bucket has a lifecycle policy that moves older data to Glacier every month. There is a strict compliance requirement where a surprise audit can happen at anytime and you should be able to retrieve the required data in under 15 minutes under all circumstances. Your manager instructed you to ensure that retrieval capacity is available when you need it and should handle up to 150 MB/s of retrieval throughput.   

Which of the following should you do to meet the above requirement? (Select TWO.)
+ Retrieve the data using Amazon Glacier Select.
+ Use Expedited Retrieval to access the financial data.
+ Use Bulk Retrieval to access the financial data.
+ Specify a range, or portion, of the financial data archive to retrieve.
+ Purchase provisioned retrieval capacity.

<details close>
<summary>Answer</summary>
b,e
</details>

<details close>
<summary>Note</summary>
bulk retrievals typically complete within 5–12 hours hence, this does not satisfy the requirement of retrieving the data within 15 minutes. The provisioned capacity option is also not compatible with Bulk retrievals

Retrieving the data using Amazon Glacier Select is incorrect because this is not an archive retrieval option and is primarily used to perform filtering operations using simple Structured Query Language (SQL) statements directly on your data archive in Glacier.

Provisioned capacity ensures that your retrieval capacity for expedited retrievals is available when you need i
</details>

---

A company has a global online trading platform in which the users from all over the world regularly upload terabytes of transactional data to a centralized S3 bucket.

What AWS feature should you use in your present system to improve throughput and ensure consistently fast data transfer to the Amazon S3 bucket, regardless of your user's location?
+ FTP
+ AWS Direct Connect
+ Amazon S3 Transfer Acceleration
+ Use CloudFront Origin Access Identity

<details close>
<summary>Answer</summary>
c
</details>

---

A Solutions Architect is working for a financial company. The manager wants to have the ability to automatically transfer obsolete data from their S3 bucket to a low-cost storage system in AWS.

What is the best solution that the Architect can provide to them?

+ Use an EC2 instance and a scheduled job to transfer the obsolete data from their S3 location to Amazon S3 Glacier.
+ Use Lifecycle Policies in S3 to move obsolete data to Glacier.
+ Use Amazon SQS.
+ Use CloudEndure Migration.
<details close>
<summary>Answer</summary>
b
</details>

---

A Solutions Architect working for a startup is designing a High Performance Computing (HPC) application which is publicly accessible for their customers. The startup founders want to mitigate distributed denial-of-service (DDoS) attacks on their application.

Which of the following options are not suitable to be implemented in this scenario? (Select TWO.)
+ Use Dedicated EC2 instances to ensure that each instance has the maximum performance possible.
+ Add multiple Elastic Fabric Adapters (EFA) to each EC2 instance to increase the network bandwidth.
+ Use an Amazon CloudFront service for distributing both static and dynamic content.
+ Use an Application Load Balancer with Auto Scaling groups for your EC2 instances. Prevent direct Internet traffic to your Amazon RDS database by deploying it to a new private subnet.
+ Use AWS Shield and AWS WAF.

<details close>
<summary>Answer</summary>
a,b
</details>

---

A company is deploying a Microsoft SharePoint Server environment on AWS using CloudFormation. The Solutions Architect needs to install and configure the architecture that is composed of Microsoft Active Directory (AD) domain controllers, Microsoft SQL Server 2012, multiple Amazon EC2 instances to host the Microsoft SharePoint Server and many other dependencies. The Architect needs to ensure that the required components are properly running before the stack creation proceeds.

Which of the following should the Architect do to meet this requirement?
+ Configure the `DependsOn`  attribute in the CloudFormation template. Send a success signal after the applications are installed and configured using the `cfn-init`  helper script.
+ Configure a `UpdatePolicy` attribute to the instance in the CloudFormation template. Send a success signal after the applications are installed and configured using the `cfn-signal` helper script.
+ Configure the `UpdateReplacePolicy` attribute in the CloudFormation template. Send a success signal after the applications are installed and configured using the `cfn-signal` helper script.
+ Configure a `CreationPolicy` attribute to the instance in the CloudFormation template. Send a success signal after the applications are installed and configured using the `cfn-signal` helper script.

<details close>
<summary>Answer</summary>
d
</details>

---

A company is hosting EC2 instances that are on non-production environment and processing non-priority batch loads, which can be interrupted at any time.   

What is the best instance purchasing option which can be applied to your EC2 instances in this case? 
+ Reserved Instances
+ On-Demand Instances
+ Spot Instances
+ On-Demand Capacity Reservationss

<details close>
<summary>Answer</summary>
c
</details>

---

The media company that you are working for has a video transcoding application running on Amazon EC2. Each EC2 instance polls a queue to find out which video should be transcoded, and then runs a transcoding process. If this process is interrupted, the video will be transcoded by another instance based on the queuing system. This application has a large backlog of videos which need to be transcoded. Your manager would like to reduce this backlog by adding more EC2 instances, however, these instances are only needed until the backlog is reduced.

In this scenario, which type of Amazon EC2 instance is the most cost-effective type to use?
+ Reserved instances
+ Spot instances
+ Dedicated instances
+ On-demand instances

<details close>
<summary>Answer</summary>
b
</details>

---

A company currently has an Augment Reality (AR) mobile game that has a serverless backend. It is using a DynamoDB table which was launched using the AWS CLI to store all the user data and information gathered from the players and a Lambda function to pull the data from DynamoDB. The game is being used by millions of users each day to read and store data.

How would you design the application to improve its overall performance and make it more scalable while keeping the costs low? (Select TWO.)

+ Enable DynamoDB Accelerator (DAX) and ensure that the Auto Scaling is enabled and increase the maximum provisioned read and write capacity.
+ Configure CloudFront with DynamoDB as the origin; cache frequently accessed data on the client device using ElastiCache.
+ Use AWS SSO and Cognito to authenticate users and have them directly access DynamoDB using single-sign on. Manually set the provisioned read and write capacity to a higher RCU and WCU.
+ Since Auto Scaling is enabled by default, the provisioned read and write capacity will adjust automatically. Also enable DynamoDB Accelerator (DAX) to improve the performance from milliseconds to microseconds.
<details close>
<summary>Answer</summary>
a,d
</details>

<details close>
<summary>Note</summary>
By default, Auto Scaling is not enabled in a DynamoDB table which is created using the AWS CLI.

</details>

---

A company has an e-commerce application that saves the transaction logs to an S3 bucket. You are instructed by the CTO to configure the application to keep the transaction logs for one month for troubleshooting purposes, and then afterward, purge the logs.

What should you do to accomplish this requirement?
+ Add a new bucket policy on the Amazon S3 bucket.
+ Configure the lifecycle configuration rules on the Amazon S3 bucket to purge the transaction logs after a month 
+ Create a new IAM policy for the Amazon S3 bucket that automatically deletes the logs after a month
+ Enable CORS on the Amazon S3 bucket which will enable the automatic monthly deletion of data

<details close>
<summary>Answer</summary>
b
</details>

---

A solutions architect is formulating a strategy for a startup that needs to transfer 50 TB of on-premises data to Amazon S3. The startup has a slow network transfer speed between its data center and AWS which causes a bottleneck for data migration.

Which of the following should the solutions architect implement?

+ Request an Import Job to Amazon S3 using a Snowball device in the AWS Snowball Console.
+ Deploy an AWS Migration Hub Discovery agent in the on-premises data center.
+ Enable Amazon S3 Transfer Acceleration on the target S3 bucket.
+ Integrate AWS Storage Gateway File Gateway with the on-premises data center.
<details close>
<summary>Answer</summary>
a
</details>

---

A Solutions Architect is unable to connect to the newly deployed EC2 instance via SSH using a home computer. However, the Architect was able to successfully access other existing instances in the VPC without any issues.

Which of the following should the Architect check and possibly correct to restore connectivity?
+ Use Amazon Data Lifecycle Manager.
+ Configure the Network Access Control List of your VPC to permit ingress traffic over port 22 from your IP.
+ Configure the Security Group of the EC2 instance to permit ingress traffic over port 3389 from your IP.
+ Configure the Security Group of the EC2 instance to permit ingress traffic over port 22 from your IP. 

<details close>
<summary>Answer</summary>
d
</details>

---

A Solutions Architect is working for a large insurance firm. To maintain compliance with HIPAA laws, all data that is backed up or stored on Amazon S3 needs to be encrypted at rest.

Which encryption methods can be employed, assuming S3 is being used for storing financial-related data? (Select TWO.)
+ Enable SSE on an S3 bucket to make use of AES-256 encryption
+ Store the data in encrypted EBS snapshots
+ Encrypt the data using your own encryption keys then copy the data to Amazon S3 over HTTPS endpoints.
+ Store the data on EBS volumes with encryption enabled instead of using Amazon S3
+ Use AWS Shield to protect your data at rest

<details close>
<summary>Answer</summary>
a,c
</details>

---

A tech company is currently using Auto Scaling for their web application. A new AMI now needs to be used for launching a fleet of EC2 instances.

Which of the following changes needs to be done?
+ Do nothing. You can start directly launching EC2 instances in the Auto Scaling group with the same launch configuration.
+ Create a new launch configuration.
+ Create a new target group.
+ Create a new target group and launch configuration.

<details close>
<summary>Answer</summary>
b
</details>

---

A company is setting up a cloud architecture for an international money transfer service to be deployed in AWS which will have thousands of users around the globe. The service should be available 24/7 to avoid any business disruption and should be resilient enough to handle the outage of an entire AWS region. To meet this requirement, the Solutions Architect has deployed their AWS resources to multiple AWS Regions. He needs to use Route 53 and configure it to set all of the resources to be available all the time as much as possible. When a resource becomes unavailable, Route 53 should detect that it's unhealthy and stop including it when responding to queries.

Which of the following is the most fault-tolerant routing configuration that the Solutions Architect should use in this scenario?
+ Configure an Active-Active Failover with Weighted routing policy.  
+ Configure an Active-Passive Failover with Weighted Records.  
+ Configure an Active-Active Failover with One Primary and One Secondary Resource.  
+ Configure an Active-Passive Failover with Multiple Primary and Secondary Resources.   

<details close>
<summary>Answer</summary>
a
</details>

---

A new online banking platform has been re-designed to have a microservices architecture in which complex applications are decomposed into smaller, independent services. The new platform is using Docker considering that application containers are optimal for running small, decoupled services. The new solution should remove the need to provision and manage servers, let you specify and pay for resources per application, and improve security through application isolation by design.

Which of the following is the MOST suitable service to use to migrate this new platform to AWS?
+ Amazon EKS
+ Amazon EFS
+ AWS Fargate
+ Amazon EBS

<details close>
<summary>Answer</summary>
c
</details>

---

A large telecommunications company needs to run analytics against all combined log files from the Application Load Balancer as part of the regulatory requirements.

Which AWS services can be used together to collect logs and then easily perform log analysis?
+ Amazon DynamoDB for storing and EC2 for analyzing the logs.
+ Amazon EC2 with EBS volumes for storing and analyzing the log files.
+ Amazon S3 for storing the ELB log files and an EC2 instance for analyzing the log files using a custom-built application.
+ Amazon S3 for storing ELB log files and Amazon EMR for analyzing the log files.

<details close>
<summary>Answer</summary>
d
</details>

---

A call center wants to use Artificial Intelligence(AI) to extract insights from audio recordings to assess the quality of its customer service. The calls are available in both English and Hindi. A sentiment analysis report in English must be generated for each recording to assess whether or not the customer had a positive experience. Once the solution is completed, new languages will eventually be supported, such as Arabic, Mandarin, and Spanish.

How can the solutions architect build the solution without maintaining any machine learning model?
+ Convert audio recordings into text using Amazon Transcribe. Set up Amazon Translate to translate Hindi texts into English and use Amazon Comprehend for sentiment analysis.
+ Transcribe audio recordings into text using Amazon Polly. Set up Amazon Rekognition to recognize and automatically translate Hindi texts into English. Use the combination of Amazon Fraud Detector and Amazon SageMaker BlazingText algorithm for sentiment analysis.
+ Utilize the Amazon Lex service to convert audio recordings into text. Call the Amazon Translate API to translate Hindi texts into English and use Amazon Forecast for sentiment prediction and analysis.
+ Set up Amazon Comprehend to convert audio recordings into text. Use Amazon Kendra to translate Hindi texts into English and utilize the Amazon Detective service to automatically detect negative user behaviors for sentiment analysis.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
Amazon Transcribe is an AWS service that makes it easy for customers to convert speech-to-text. Using Automatic Speech Recognition (ASR) technology, customers can choose to use Amazon Transcribe for a variety of business applications, including transcription of voice-based customer service calls, generation of subtitles on audio/video content, and conduct (text-based) content analysis on audio/video content.

Amazon Translate is a Neural Machine Translation (MT) service for translating text between supported languages.

Amazon Comprehend is a natural language processing (NLP) service that uses machine learning to find meaning and insights in text.
</details>

---

Due to the large volume of query requests, the database performance of an online reporting application significantly slowed down. The Solutions Architect is trying to convince her client to use Amazon RDS Read Replica for their application instead of setting up a Multi-AZ Deployments configuration.

What are two benefits of using Read Replicas over Multi-AZ that the Architect should point out? (Select TWO.)
+ It elastically scales out beyond the capacity constraints of a single DB instance for read-heavy database workloads.
+ Allows both read and write operations on the read replica to complement the primary database.
+ Provides asynchronous replication and improves the performance of the primary database by taking read-heavy database workloads from it.
+ Provides synchronous replication and automatic failover in the case of Availability Zone service failures.
+ It enhances the read performance of your primary database by increasing its IOPS and accelerates its query processing via AWS Global Accelerator.

<details close>
<summary>Answer</summary>
a,c
</details>


