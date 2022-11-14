# Solution Architect Exam#3 Practice Set

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

---

A company is using Amazon VPC that has a CIDR block of `10.31.0.0/27` that is connected to the on-premises data center. There was a requirement to create a Lambda function that will process massive amounts of cryptocurrency transactions every minute and then store the results to EFS. After setting up the serverless architecture and connecting the Lambda function to the VPC, the Solutions Architect noticed an increase in invocation errors with EC2 error types such as `EC2ThrottledException` at certain times of the day.

Which of the following are the possible causes of this issue? (Select TWO.)
+ You only specified one subnet in your Lambda function configuration. That single subnet runs out of available IP addresses and there is no other subnet or Availability Zone which can handle the peak load.
+ Your VPC does not have a NAT gateway.
+ Your VPC does not have sufficient subnet ENIs or subnet IPs.
+ The associated security group of your function does not allow outbound connections.
+ The attached IAM execution role of your function does not have the necessary permissions to access the resources of your VPC.

<details close>
<summary>Answer</summary>
a,c
</details>

---

An aerospace engineering company recently adopted a hybrid cloud infrastructure with AWS. One of the Solutions Architect’s tasks is to launch a VPC with both public and private subnets for their EC2 instances as well as their database instances.

Which of the following statements are true regarding Amazon VPC subnets? (Select TWO.)
+ EC2 instances in a private subnet can communicate with the Internet only if they have an Elastic IP.
+ Each subnet maps to a single Availability Zone.
+ The allowed block size in VPC is between a /16 netmask (65,536 IP addresses) and /27 netmask (32 IP addresses).
+ Every subnet that you create is automatically associated with the main route table for the VPC. 
+ Each subnet spans to 2 Availability Zones.

<details close>
<summary>Answer</summary>
b,d
</details>

---

A company that is rapidly growing in recent months has been in the process of setting up IAM users on its single AWS Account. A solutions architect has been tasked to handle the user management, which includes granting read-only access to users and denying permissions whenever an IAM user has no MFA setup. New users will be added frequently based on their respective departments.

Which of the following action is the MOST secure way to grant permissions to the new users?

+ Launch an IAM Group for each department. Create an IAM Policy that enforces MFA authentication with the least privilege permission. Attach the IAM Policy to each IAM Group.
+ Create a Service Control Policy (SCP) that enforces MFA authentication for each department. Add a trust relationship to every SCP and attach it to each IAM User.
+ Create an IAM Role that enforces MFA authentication with the least privilege permission. Set up a corresponding IAM Group for each department. Attach the IAM Role to the IAM Groups.
+ Set up IAM roles for each IAM user and associate a permissions boundary that defines the maximum permissions.

<details close>
<summary>Answer</summary>
a
</details>

---

A major TV network has a web application running on eight Amazon T3 EC2 instances. The number of requests that the application processes are consistent and do not experience spikes. To ensure that eight instances are running at all times, the Solutions Architect should create an Auto Scaling group and distribute the load evenly between all instances.

Which of the following options can satisfy the given requirements?
+ Deploy eight EC2 instances with Auto Scaling
+ Deploy four EC2 instances with Auto Scaling in one region and four in another region behind an Amazon Elastic Load Balancer.
+ Deploy four EC2 instances with Auto Scaling in one Availability Zone and four in another availability zone in the same region behind an Amazon Elastic Load Balancer.
+ Deploy two EC2 instances with Auto Scaling in four regions behind an Amazon Elastic Load Balancer.

<details close>
<summary>Answer</summary>
c
</details>

---

In Amazon EC2, you can manage your instances from the moment you launch them up to their termination. You can flexibly control your computing costs by changing the EC2 instance state. Which of the following statements is true regarding EC2 billing? (Select TWO.)
+ You will be billed when your On-Demand instance is in `pending`  state.
+ You will be billed when your Spot instance is preparing to stop with a `stopping` state.
+ You will be billed when your On-Demand instance is preparing to hibernate with a `stopping`  state.
+ You will be billed when your Reserved instance is in `terminated`  state.
+ You will not be billed for any instance usage while an instance is not in the `running` state.

<details close>
<summary>Answer</summary>
c,d
</details>

---

A large financial firm needs to set up a Linux bastion host to allow access to the Amazon EC2 instances running in their VPC. For security purposes, only the clients connecting from the corporate external public IP address 175.45.116.100 should have SSH access to the host.

Which is the best option that can meet the customer's requirement?

+ Security Group Inbound Rule: Protocol – TCP. Port Range – 22, Source 175.45.116.100/32
+ Security Group Inbound Rule: Protocol – UDP, Port Range – 22, Source 175.45.116.100/32
+ Network ACL Inbound Rule: Protocol – UDP, Port Range – 22, Source 175.45.116.100/32
+ Network ACL Inbound Rule: Protocol – TCP, Port Range-22, Source 175.45.116.100/0

<details close>
<summary>Answer</summary>
a
</details>

---

A travel company has a suite of web applications hosted in an Auto Scaling group of On-Demand EC2 instances behind an Application Load Balancer that handles traffic from various web domains such as `i-love-manila.com`, `i-love-boracay.com`, `i-love-cebu.com` and many others. To improve security and lessen the overall cost, you are instructed to secure the system by allowing multiple domains to serve SSL traffic without the need to reauthenticate and reprovision your certificate everytime you add a new domain. This migration from HTTP to HTTPS will help improve their SEO and Google search ranking.

Which of the following is the most cost-effective solution to meet the above requirement?


<details close>
<summary>Answer</summary>
d
</details>

---

A large financial firm in the country has an AWS environment that contains several Reserved EC2 instances hosting a web application that has been decommissioned last week. To save costs, you need to stop incurring charges for the Reserved instances as soon as possible.

What cost-effective steps will you take in this circumstance? (Select TWO.)
+ Stop the Reserved instances as soon as possible.
+ Contact AWS to cancel your AWS subscription.
+ Go to the AWS Reserved Instance Marketplace and sell the Reserved instances.
+ Terminate the Reserved instances as soon as possible to avoid getting billed at the on-demand price when it expires.
+ Go to the Amazon.com online shopping website and sell the Reserved instances.

<details close>
<summary>Answer</summary>
c,d
</details>

---

A company has clients all across the globe that access product files stored in several S3 buckets, which are behind each of their own CloudFront web distributions. They currently want to deliver their content to a specific client, and they need to make sure that only that client can access the data. Currently, all of their clients can access their S3 buckets directly using an S3 URL or through their CloudFront distribution. The Solutions Architect must serve the private content via CloudFront only, to secure the distribution of files.

Which combination of actions should the Architect implement to meet the above requirements? (Select TWO.)
+ Create a custom CloudFront function to check and ensure that only their clients can access the files.
+ Enable the Origin Shield feature of the Amazon CloudFront distribution to protect the files from unauthorized access.
+ Use S3 pre-signed URLs to ensure that only their client can access the files. Remove permission to use Amazon S3 URLs to read the files for anyone else.
+ Restrict access to files in the origin by creating an origin access identity (OAI) and give it permission to read the files in the bucket.
+ Require the users to access the private content by using special CloudFront signed URLs or signed cookies.

<details close>
<summary>Answer</summary>
d,e
</details>

---

A company is storing its financial reports and regulatory documents in an Amazon S3 bucket. To comply with the IT audit, they tasked their Solutions Architect to track all new objects added to the bucket as well as the removed ones. It should also track whether a versioned object is permanently deleted. The Architect must configure Amazon S3 to publish notifications for these events to a queue for post-processing and to an Amazon SNS topic that will notify the Operations team.

Which of the following is the MOST suitable solution that the Architect should implement?
+ Create a new Amazon SNS topic and Amazon SQS queue. Add an S3 event notification configuration on the bucket to publish `s3:ObjectCreated:*` and `s3:ObjectRemoved:Delete`  event types to SQS and SNS. 
+ Create a new Amazon SNS topic and Amazon MQ. Add an S3 event notification configuration on the bucket to publish `s3:ObjectAdded:*` and `s3:ObjectRemoved:*` event types to SQS and SNS.
+ Create a new Amazon SNS topic and Amazon SQS queue. Add an S3 event notification configuration on the bucket to publish `s3:ObjectCreated:*` and `ObjectRemoved:DeleteMarkerCreated` event types to SQS and SNS.
+ Create a new Amazon SNS topic and Amazon MQ. Add an S3 event notification configuration on the bucket to publish `s3:ObjectCreated:*` and `ObjectRemoved:DeleteMarkerCreated` event types to SQS and SNS.

<details close>
<summary>Answer</summary>
a
</details>

---

An application needs to retrieve a subset of data from a large CSV file stored in an Amazon S3 bucket by using simple SQL expressions. The queries are made within Amazon S3 and must only return the needed data. 

Which of the following actions should be taken?
+ Perform an S3 Select operation based on the bucket's name and object's key.
+ Perform an S3 Select operation based on the bucket's name and object's metadata.
+ Perform an S3 Select operation based on the bucket's name and object tags.
+ Perform an S3 Select operation based on the bucket’s name.

<details close>
<summary>Answer</summary>
a
</details>

---

A media company recently launched their newly created web application. Many users tried to visit the website, but they are receiving a 503 Service Unavailable Error. The system administrator tracked the EC2 instance status and saw the capacity is reaching its maximum limit and unable to process all the requests. To gain insights from the application's data, they need to launch a real-time analytics service.

Which of the following allows you to read records in batches?
+ Create an Amazon S3 bucket to store the captured data and use Amazon Athena to analyze the data.
+ Create a Kinesis Data Firehose and use AWS Lambda to read records from the data stream.
+ Create an Amazon S3 bucket to store the captured data and use Amazon Redshift Spectrum to analyze the data.
+ Create a Kinesis Data Stream and use AWS Lambda to read records from the data stream.

<details close>
<summary>Answer</summary>
d
</details>

---

A company needs to use Amazon Aurora as the Amazon RDS database engine of their web application. The Solutions Architect has been instructed to implement a 90-day backup retention policy.

Which of the following options can satisfy the given requirement?
+ Configure an automated backup and set the backup retention period to 90 days.
+ Create an AWS Backup plan to take daily snapshots with a retention period of 90 days.
+ Configure RDS to export the automated snapshot automatically to Amazon S3 and create a lifecycle policy to delete the object after 90 days.
+ Create a daily scheduled event using CloudWatch Events and AWS Lambda to directly download the RDS automated snapshot to an S3 bucket. Archive snapshots older than 90 days to Glacier.

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
AWS Backup is a centralized backup service that makes it easy and cost-effective for you to backup your application data across AWS services in the AWS Cloud, helping you meet your business and regulatory backup compliance requirements. AWS Backup makes protecting your AWS storage volumes, databases, and file systems simple by providing a central place where you can configure and audit the AWS resources you want to backup, automate backup scheduling, set retention policies, and monitor all recent backup and restore activity.

Configure an automated backup and set the backup retention period to 90 days is incorrect because the maximum backup retention period for automated backup is only 35 days.

Configure RDS to export the automated snapshot automatically to Amazon S3 and create a lifecycle policy to delete the object after 90 days is incorrect because you can't export an automated snapshot automatically to Amazon S3. You must export the snapshot manually.

</details>

---

A company plans to use a durable storage service to store on-premises database backups to the AWS cloud. To move their backup data, they need to use a service that can store and retrieve objects through standard file storage protocols for quick recovery.

Which of the following options will meet this requirement?
+ Use the AWS Storage Gateway volume gateway to store the backup data and directly access it using Amazon S3 API actions.
+ Use Amazon EBS volumes to store all the backup data and attach it to an Amazon EC2 instance.
+ Use AWS Snowball Edge to directly backup the data in Amazon S3 Glacier.
+ Use the AWS Storage Gateway file gateway to store all the backup data in Amazon S3.

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
Use the AWS Storage Gateway volume gateway to store the backup data and directly access it using Amazon S3 API actions is incorrect. Although this is a possible solution, you cannot directly access the volume gateway using Amazon S3 APIs. You should use File Gateway to access your data in Amazon S3.
</details>

---

A company has established a dedicated network connection from its on-premises data center to AWS Cloud using AWS Direct Connect (DX). The core network services, such as the Domain Name System (DNS) service and Active Directory services, are all hosted on-premises. The company has new AWS accounts that will also require consistent and dedicated access to these network services.

Which of the following can satisfy this requirement with the LEAST amount of operational overhead and in a cost-effective manner?

+ Set up another Direct Connect connection for each and every new AWS account that will be added.
+ Set up a new Direct Connect gateway and integrate it with the existing Direct Connect connection. Configure a VPC peering connection between AWS accounts and associate it with Direct Connect gateway.
+ Create a new AWS VPN CloudHub. Set up a Virtual Private Network (VPN) connection for additional AWS accounts.
+ Create a new Direct Connect gateway and integrate it with the existing Direct Connect connection. Set up a Transit Gateway between AWS accounts and associate it with the Direct Connect gateway.

<details close>
<summary>Answer</summary>
d
</details>

---

A company hosted a web application on a Linux Amazon EC2 instance in the public subnet that uses a default network ACL. The instance uses a default security group and has an attached Elastic IP address. The network ACL has been configured to block all traffic to the instance. The Solutions Architect must allow incoming traffic on port 443 to access the application from any source.

Which combination of steps will accomplish this requirement? (Select TWO.)

+ In the Security Group, add a new rule to allow TCP connection on port 443 from source `0.0.0.0/0` 

+ In the Network ACL, update the rule to allow both inbound and outbound TCP connection on port 443 from source `0.0.0.0/0` and to destination `0.0.0.0/0`
+ In the Security Group, create a new rule to allow TCP connection on port 443 to destination `0.0.0.0/0`
+ In the Network ACL, update the rule to allow outbound TCP connection on port `32768 - 65535`  to destination `0.0.0.0/0`
+ In the Network ACL, update the rule to allow inbound TCP connection on port 443 from source `0.0.0.0/0` and outbound TCP connection on port `32768 - 65535` to destination  `0.0.0.0/0`

<details close>
<summary>Answer</summary>
a,e
</details>

---

A production MySQL database hosted on Amazon RDS is running out of disk storage. The management has consulted its solutions architect to increase the disk space without impacting the database performance.

How can the solutions architect satisfy the requirement with the LEAST operational overhead?

+ Modify the DB instance settings and enable storage autoscaling.
+ Increase the allocated storage for the DB instance.
+ Change the `default_storage_engine` of the DB instance’s parameter group to `MyISAM`.
+ Modify the DB instance storage type to Provisioned IOPS.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>

The option that says: Increase the allocated storage for the DB instance is incorrect. Although this will solve the problem of low disk space, increasing the allocated storage might cause performance degradation during the change.


</details>

---

A company is hosting an application on EC2 instances that regularly pushes and fetches data in Amazon S3. Due to a change in compliance, the instances need to be moved on a private subnet. Along with this change, the company wants to lower the data transfer costs by configuring its AWS resources.

How can this be accomplished in the MOST cost-efficient manner?

+ Set up a NAT Gateway in the public subnet to connect to Amazon S3.
+ Create an Amazon S3 interface endpoint to enable a connection between the instances and Amazon S3.
+ Create an Amazon S3 gateway endpoint to enable a connection between the instances and Amazon S3.
+ Set up an AWS Transit Gateway to access Amazon S3.

<details close>
<summary>Answer</summary>
c
</details>

<summary>Note</summary>

The option that says: Create an Amazon S3 interface endpoint to enable a connection between the instances and Amazon S3 is incorrect. This is also a possible solution but it's not the most cost-effective solution. You pay an hourly rate for every provisioned Interface endpoint.

</details>

---

An online registration system hosted in an Amazon EKS cluster stores data to a` db.t4g.medium` Amazon Aurora DB cluster. The database performs well during regular hours but is unable to handle the traffic surge that occurs during flash sales. A solutions architect must move the database to Aurora Serverless while minimizing downtime and the impact on the operation of the application.

Which change should be taken to meet the objective?
+ Use AWS Database Migration Service (AWS DMS) to migrate to a new Aurora Serverless database.
+ Change the Aurora Instance class to Serverless
+ Take a snapshot of the DB cluster. Use the snapshot to create a new Aurora DB cluster.
+ Add an Aurora Replica to the cluster and set its instance class to Serverless. Failover to the read replica and promote it to primary.

<details close>
<summary>Answer</summary>
a
</details>

---

A firm has a containerized application that runs on a self-managed Kubernetes cluster. The cluster writes data in an on-premises MongoDB database. A solutions architect is requested to move the service to AWS in order to minimize operational overhead. The firm prohibits any changes to the code.

Which action meets these objectives?

+ Migrate the cluster to an Amazon Elastic Kubernetes Service (EKS) cluster and the database to an Amazon DocumentDB (with MongoDB compatibility) database.
+ Migrate the cluster to an Amazon Elastic Container Service (ECS) cluster using Amazon ECS Anywhere and the database to an Amazon Aurora Serverless database.
+ Migrate the cluster to an Amazon Elastic Kubernetes Service (EKS) cluster using Amazon EKS Anywhere and the database to an Amazon DynamoDB table.
+ Migrate the cluster to an Amazon Elastic Container Service (ECS) cluster with the images stored in the Amazon Elastic Container Registry (Amazon ECR). Move the database to an Amazon Neptune database

<details close>
<summary>Answer</summary>
a
</details>

---

A company requires that all AWS resources be tagged with a standard naming convention for better access control. The company’s solutions architect must implement a solution that checks for untagged AWS resources.

Which solution requires the least amount of effort to implement?
+ Use an AWS Config rule to detect non-compliant tags.
+ Use tag policies in AWS Organizations to standardize the naming of tags. Store all the tags in an Amazon S3 bucket with the S3 Object Lock feature enabled.
+ Create a Lambda function that runs compliance checks on tagged resources. Schedule the function using Amazon EventBridge.
+ Use service control policies (SCP) to detect resources that are not tagged properly.

<details close>
<summary>Answer</summary>
a
</details>

---

A company intends to give each of its developers a personal AWS account through AWS Organizations. To enforce regulatory policies, preconfigured AWS Config rules will be set in the new accounts. A solutions architect must see to it that developers are unable to remove or modify any rules in AWS Config.

Which solution meets the objective with the least operational overhead?
+ Add the developers' AWS account to an organization unit (OU). Attach a service control policy (SCP) to the OU that restricts access to AWS Config.
+ Use an IAM Role in the new accounts with an attached IAM trust relationship to disable the access of the root user to AWS Config.
+ Configure an AWS Config rule in the root account to detect if changes to the new account’s Config rules are made.
+ Set up an AWS Control Tower in the root account to detect if there were any changes to the new account’s AWS Config rules. Attach an IAM trust relationship to the IAM User of each developer which prevents any changes in AWS Config.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
Keep in mind that the effects of IAM Policies do not apply to account root users. 
</details>

---

A solutions architect is in charge of preparing the infrastructure for a serverless application. The application is built from a Docker image pulled from an Amazon Elastic Container Registry (ECR) repository. It is compulsory that the application has access to 5 GB of ephemeral storage.

Which action satisfies the requirements?
+ Deploy the application to an Amazon ECS cluster that uses Fargate tasks.
+ Deploy the application in a Lambda function with Container image support. Set the function’s storage to 5 GB.
+ Deploy the application in a Lambda function with Container image support. Attach an Amazon Elastic File System (EFS) volume to the function.
+ Deploy the application Amazon ECS cluster with EC2 worker nodes and attach a 5 GB Amazon EBS volume.

<details close>
<summary>Answer</summary>
a
</details>

---

A company runs a multi-tier web application in the AWS Cloud. The application tier is hosted on Amazon EC2 instances and the backend database is hosted on an Amazon Aurora for MySQL DB cluster. For security compliance, all of the application variables such as DB hostnames, environment settings, product keys, and database passwords must be stored securely with encryption.

Which of the following options is the most cost-effective solution to meet the requirements?
+ Store the values by creating SecureString type parameters in AWS Systems Manager Parameter Store. Use AWS Key Management Service (AWS KMS) for the encryption. Update the application to retrieve the parameter values.
+ Store the values by creating secrets in AWS Secrets Manager. Use AWS Key Management Service (AWS KMS) for the encryption. Update the application to retrieve the value of the secrets.
+ Store the values in a file saved in an Amazon S3 bucket. Enable encryption on the Amazon S3 bucket. Configure the application to download the file contents when it starts.
+ Store the values as key-value pairs in AWS Systems Manager OpsCenter. By default, the key-value pairs will be encrypted at rest. Configure the application to retrieve the variables when it starts.

<details close>
<summary>Answer</summary>
a
</details>


