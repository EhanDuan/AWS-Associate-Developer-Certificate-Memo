# Solution Architect Exam#4 Practice Set

A company runs its multitier online shopping platform on AWS. Every new sale transaction is published as a message in an open-source RabbitMQ queue that runs on an Amazon EC2 instance. There is a consumer application is hosted on a separate EC2 instance that consumes the incoming messages, which then stores the transaction in a self-hosted PostgreSQL database on another EC2 instance.

All of the EC2 instances used are in the same Availability Zone in the `eu-central-1` Region. A solutions architect needs to redesign its cloud architecture to provide the highest availability with the least amount of operational overhead.

What should a solutions architect do to meet the company’s requirements above?

+ Migrate the RabbitMQ queue to Amazon Simple Queue Service (SQS). Rehost the consumer application to an Amazon OpenSearch Service (Amazon Elasticsearch) cluster. Migrate the PostgreSQL database to an Amazon Aurora Serverless cluster
+ Migrate the RabbitMQ queue to Amazon MQ to a cluster broker deployment setup. Launch a Multi-AZ Auto Scaling group for the Amazon EC2 instances that host the consumer application. Migrate the existing database to Amazon RDS for PostgreSQL in a Multi-AZ Deployment configuration.
+ Migrate the RabbitMQ queue to an Auto Scaling group of EC2 instances. Rehost the consumer application to an Amazon ECS cluster with AWS Fargate. Migrate the PostgreSQL database to Amazon Aurora PostgreSQL using the Aurora cloning feature.
+ Migrate the RabbitMQ queue to a redundant pair (active/standby) of Amazon MQ brokers in AWS. Launch a Multi-AZ Auto Scaling group for the Amazon EC2 instances that host the consumer application. Migrate the PostgreSQL database to Amazon RDS for PostgreSQL with cross-Region read replicas

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A large electronics company is using Amazon Simple Storage Service to store important documents. For reporting purposes, they want to track and log every request access to their S3 buckets including the requester, bucket name, request time, request action, referrer, turnaround time, and error code information. The solution should also provide more visibility into the object-level operations of the bucket.

Which is the best solution among the following options that can satisfy the requirement?
+ Enable AWS CloudTrail to audit all Amazon S3 bucket access.
+ Enable server access logging for all required Amazon S3 buckets.
+ Enable the Requester Pays option to track access via AWS Billing.
+ Enable Amazon S3 Event Notifications for PUT and POST.

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
AWS CloudTrail alone won't give detailed logging information for object-level access.
</details>

---

A tech company currently has an on-premises infrastructure. They are currently running low on storage and want to have the ability to extend their storage using the AWS cloud.

Which AWS service can help them achieve this requirement?
+ Amazon EC2
+ Amazon Storage Gateway
+ Amazon Elastic Block Storage
+ Amazon SQS

<details close>
<summary>Answer</summary>
b
</details>

---

A startup launched a new FTP server using an On-Demand EC2 instance in a newly created VPC with default settings. The server should not be accessible publicly but only through the IP address `175.45.116.100` and nowhere else.

Which of the following is the most suitable way to implement this requirement?
+ Create a new inbound rule in the security group of the EC2 instance with the following details: Protocol: TCP , Port Range: 20 - 21 , Source: `175.45.116.100/32`
+ Create a new inbound rule in the security group of the EC2 instance with the following details: Protocol: UDP , Port Range: 20 - 21 , Source: `175.45.116.100/32`
+ Create a new Network ACL inbound rule in the subnet of the EC2 instance with the following details: Protocol: TCP , Port Range: 20 - 21 , Source: `175.45.116.100/0`, Allow/Deny: ALLOW
+ Create a new Network ACL inbound rule in the subnet of the EC2 instance with the following details: Protocol: UDP , Port Range: 20 - 21 , Source: `175.45.116.100/0` , Allow/Deny: ALLOW

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
FTP - File Transfer Protocol, use TCP
The FTP protocol uses TCP via ports 20 and 21
</details>

---

A Solutions Architect is designing a monitoring application which generates audit logs of all operational activities of the company's cloud infrastructure. Their IT Security and Compliance team mandates that the application retain the logs for 5 years before the data can be deleted.

How can the Architect meet the above requirement?

+ Store the audit logs in a Glacier vault and use the Vault Lock feature.
+ Store the audit logs in an EBS volume and then take EBS snapshots every month.
+ Store the audit logs in an Amazon S3 bucket and enable Multi-Factor Authentication Delete (MFA Delete) on the S3 bucket.
+ Store the audit logs in an EFS volume and use Network File System version 4 (NFSv4) file-locking mechanism.

<details close>
<summary>Answer</summary>
a
</details>

---

The company you are working for has a set of AWS resources hosted in ap-northeast-1 region. You have been asked by your IT Manager to create an AWS CLI shell script that will call an AWS service which could create duplicate resources in another region in the event that ap-northeast-1 region fails. The duplicated resources should also contain the VPC Peering configuration and other networking components from the primary stack.

Which of the following AWS services could help fulfill this task?
+ AWS Elastic Beanstalk
+ Amazon SQS
+ AWS CloudFormation
+ Amazon SNS

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
Elastic Beanstalk environments have limited resources; for example, Elastic Beanstalk does not create a VPC for you. CloudFormation on the other hand is more of a low-level service that you can use to model the entirety of your AWS environment. In fact, Elastic Beanstalk uses CloudFormation under the hood to create resources.

</details>

---

A company is using an Auto Scaling group which is configured to launch new `t2.micro` EC2 instances when there is a significant load increase in the application. To cope with the demand, you now need to replace those instances with a larger `t2.2xlarge` instance type.

How would you implement this change?
+ Just change the instance type to `t2.2xlarge`  in the current launch configuration
+ Create another Auto Scaling Group and attach the new instance type.
+ Create a new launch configuration with the new instance type and update the Auto Scaling Group.
+ Change the instance type of each EC2 instance manually.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has a set of Linux servers running on multiple On-Demand EC2 Instances. The Audit team wants to collect and process the application log files generated from these servers for their report.

Which of the following services is best to use in this case?
+ Amazon S3 for storing the application log files and Amazon Elastic MapReduce for processing the log files.
+ Amazon S3 Glacier for storing the application log files and Spot EC2 Instances for processing them.
+ A single On-Demand Amazon EC2 instance for both storing and processing the log files
+ Amazon S3 Glacier Deep Archive for storing the application log files and AWS ParallelCluster for processing the log files.

<details close>
<summary>Answer</summary>
a
</details>

---

To save costs, your manager instructed you to analyze and review the setup of your AWS cloud infrastructure. You should also provide an estimate of how much your company will pay for all of the AWS resources that they are using. In this scenario, which of the following will incur costs? (Select TWO.)
+ A running EC2 Instance
+ A stopped On-Demand EC2 Instance
+ EBS Volumes attached to stopped EC2 Instances
+ Using an Amazon VPC
+ Public Data Set

<details close>
<summary>Answer</summary>
a,c
</details>

---

A multinational bank is storing its confidential files in an S3 bucket. The security team recently performed an audit, and the report shows that multiple files have been uploaded without 256-bit Advanced Encryption Standard (AES) server-side encryption. For added protection, the encryption key must be automatically rotated every year. The solutions architect must ensure that there would be no other unencrypted files uploaded in the S3 bucket in the future.

Which of the following will meet these requirements with the LEAST operational overhead?
+ Create a Service Control Policy (SCP) for the S3 bucket that rejects any object uploads unless the request includes the `s3:x-amz-server-side-encryption": "AES256"` header. Enable server-side encryption with Amazon S3-managed encryption keys (SSE-S3) and modify the built-in key rotation feature of the SSE-S3 encryption keys to rotate the key yearly.
+ Create an S3 bucket policy that denies permissions to upload an object unless the request includes the `s3:x-amz-server-side-encryption": "AES256"`  header. Enable server-side encryption with Amazon S3-managed encryption keys (SSE-S3) and rely on the built-in key rotation feature of the SSE-S3 encryption keys.
+ Create a new customer-managed key (CMK) from the AWS Key Management Service (AWS KMS). Configure the default encryption behavior of the bucket to use the customer-managed key. Manually rotate the CMK each and every year.
+ Create an S3 bucket policy for the S3 bucket that rejects any object uploads unless the request includes the `s3:x-amz-server-side-encryption":"aws:kms"` header. Enable the S3 Object Lock in compliance mode for all objects to automatically rotate the built-in AES256 customer-managed key of the bucket.

<details close>
<summary>Answer</summary>
b
</details>

---

A company is using the AWS Directory Service to integrate their on-premises Microsoft Active Directory (AD) domain with their Amazon EC2 instances via an AD connector. The below identity-based policy is attached to the IAM Identities that use the AWS Directory service:
```json
{
 "Version":"2012-10-17",
 "Statement":[
  {
   "Sid":"DirectoryTutorialsDojo1234",
   "Effect":"Allow",
   "Action":[
    "ds:*"
   ],
   "Resource":"arn:aws:ds:us-east-1:987654321012:directory/d-1234567890"
  },
  {
   "Effect":"Allow",
   "Action":[
   "ec2:*"
   ],
   "Resource":"*"
  }
 ]
}

```
Which of the following BEST describes what the above resource policy does?
+ Allows all AWS Directory Service (`ds`) calls as long as the resource contains the directory ID: `d-1234567890`
+ Allows all AWS Directory Service (`ds`) calls as long as the resource contains the directory ID: `DirectoryTutorialsDojo1234`
+ Allows all AWS Directory Service (`ds`) calls as long as the resource contains the directory ID:  `987654321012`
+ Allows all AWS Directory Service (`ds`) calls as long as the resource contains the directory name of: `DirectoryTutorialsDojo1234`

<details close>
<summary>Answer</summary>
a
</details>

---

A technology company is building a new cryptocurrency trading platform that allows the buying and selling of Bitcoin, Ethereum, Ripple, Tether, and many others. You were hired as a Cloud Engineer to build the required infrastructure needed for this new trading platform. On your first week at work, you started to create CloudFormation YAML scripts that define all of the needed AWS resources for the application. Your manager was shocked that you haven't created the EC2 instances, S3 buckets, and other AWS resources straight away. He does not understand the text-based scripts that you have done and has asked for your clarification.

In this scenario, what are the benefits of using the Amazon CloudFormation service that you should tell your manager to clarify his concerns? (Select TWO.)
+ Provides highly durable and scalable data storage
+ A storage location for the code of your application
+ Enables modeling, provisioning, and version-controlling of your entire AWS infrastructure
+ Allows you to model your entire infrastructure in a text file
+ Using CloudFormation itself is free, including the AWS resources that have been created.

<details close>
<summary>Answer</summary>
c,d
</details>

---

A company has a web application hosted in AWS cloud where the application logs are sent to Amazon CloudWatch. Lately, the web application has recently been encountering some errors which can be resolved simply by restarting the instance.

What will you do to automatically restart the EC2 instances whenever the same application error occurs?

+ First, look at the existing CloudWatch logs for keywords related to the application error to create a custom metric. Then, create a CloudWatch alarm for that custom metric which invokes an action to restart the EC2 instance.
+ First, look at the existing CloudWatch logs for keywords related to the application error to create a custom metric. Then, create an alarm in Amazon SNS for that custom metric which invokes an action to restart the EC2 instance.
+ First, look at the existing Flow logs for keywords related to the application error to create a custom metric. Then, create a CloudWatch alarm for that custom metric which invokes an action to restart the EC2 instance.
+ First, look at the existing Flow logs for keywords related to the application error to create a custom metric. Then, create a CloudWatch alarm for that custom metric which calls a Lambda function that invokes an action to restart the EC2 instance.

<details close>
<summary>Answer</summary>
a
</details>

---

A real-time data analytics application is using AWS Lambda to process data and store results in JSON format to an S3 bucket. To speed up the existing workflow, you have to use a service where you can run sophisticated Big Data analytics on your data without moving them into a separate analytics system.   

Which of the following group of services can you use to meet this requirement? 
+ S3 Select, Amazon Neptune, DynamoDB DAX  
+ Amazon X-Ray, Amazon Neptune, DynamoDB  
+ Amazon Glue, Glacier Select, Amazon Redshift  
+ S3 Select, Amazon Athena, Amazon Redshift Spectrum  

<details close>
<summary>Answer</summary>
d
</details>

---

A company has a web application hosted in an On-Demand EC2 instance. You are creating a shell script that needs the instance's public and private IP addresses.

What is the best way to get the instance's associated IP addresses which your shell script can use?
+ By using IAM.
+ By using a CloudWatch metric.
+ By using a Curl or Get Command to get the latest metadata information from http://169.254.169.254/latest/meta-data/
+ By using a Curl or Get Command to get the latest user data information from http://169.254.169.254/latest/user-data/

<details close>
<summary>Answer</summary>
c
</details>

---

A technical lead of the Cloud Infrastructure team was consulted by a software developer regarding the required AWS resources of the web application that he is building. The developer knows that an Instance Store only provides ephemeral storage where the data is automatically deleted when the instance is terminated. To ensure that the data of the web application persists, the app should be launched in an EC2 instance that has a durable, block-level storage volume attached. The developer knows that they need to use an EBS volume, but they are not sure what type they need to use.

In this scenario, which of the following is true about Amazon EBS volume types and their respective usage? (Select TWO.)
+ Spot volumes provide the lowest cost per gigabyte of all EBS volume types and are ideal for workloads where data is accessed infrequently, and applications where the lowest storage cost is important.
+ Provisioned IOPS volumes offer storage with consistent and low-latency performance, and are designed for I/O intensive applications such as large relational or NoSQL databases. 
+ Magnetic volumes provide the lowest cost per gigabyte of all EBS volume types and are ideal for workloads where data is accessed infrequently, and applications where the lowest storage cost is important.
+ General Purpose SSD (gp3) volumes with multi-attach enabled offer consistent and low-latency performance, and are designed for applications requiring multi-az resiliency.
+ Single root I/O virtualization (SR-IOV) volumes are suitable for a broad range of workloads, including small to medium-sized databases, development and test environments, and boot volumes.

<details close>
<summary>Answer</summary>
b,c
</details>

---

A company has an OLTP (Online Transactional Processing) application that is hosted in an Amazon ECS cluster using the Fargate launch type. It has an Amazon RDS database that stores data of its production website. The Data Analytics team needs to run queries against the database to track and audit all user transactions. These query operations against the production database must not impact application performance in any way.

Which of the following is the MOST suitable and cost-effective solution that you should implement?

+ Set up a new Amazon Redshift database cluster. Migrate the product database into Redshift and allow the Data Analytics team to fetch data from it.
+ Set up a new Amazon RDS Read Replica of the production database. Direct the Data Analytics team to query the production data from the replica.
+ Set up a Multi-AZ deployments configuration of your production database in RDS. Direct the Data Analytics team to query the production data from the standby instance.
+ Upgrade the instance type of the RDS database to a large instance.

<details close>
<summary>Answer</summary>
b
</details>

---

A company has a global news website hosted in a fleet of EC2 Instances. Lately, the load on the website has increased which resulted in slower response time for the site visitors. This issue impacts the revenue of the company as some readers tend to leave the site if it does not load after 10 seconds.

Which of the below services in AWS can be used to solve this problem? (Select TWO.)
+ Use Amazon CloudFront with website as the custom origin.
+ For better read throughput, use AWS Storage Gateway to distribute the content across multiple regions.
+ Use Amazon ElastiCache for the website's in-memory data store or cache.
+ Deploy the website to all regions in different VPCs for faster processing.

<details close>
<summary>Answer</summary>
a,c
</details>

---

A company has a High Performance Computing (HPC) cluster that is composed of EC2 Instances with Provisioned IOPS volume to process transaction-intensive, low-latency workloads. The Solutions Architect must maintain high IOPS while keeping the latency down by setting the optimal queue length for the volume. The size of each volume is 10 GiB.

Which of the following is the MOST suitable configuration that the Architect should set up?
+ Set the IOPS to 400 then maintain a low queue length.
+ Set the IOPS to 500 then maintain a low queue length.
+ Set the IOPS to 600 then maintain a high queue length.
+ Set the IOPS to 800 then maintain a low queue length.

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
Size(GiB) : IOPS = 1: 50
</details>

---
A company is running a web application on AWS. The application is made up of an Auto-Scaling group that sits behind an Application Load Balancer and an Amazon DynamoDB table where user data is stored. The solutions architect must design the application to remain available in the event of a regional failure. A solution to automatically monitor the status of your workloads across your AWS account, conduct architectural reviews and check for AWS best practices.

Which configuration meets the requirement with the least amount of downtime possible?
+ In a secondary region, create a global table of the DynamoDB table and replicate the auto-scaling group and application load balancer. Use Route 53 DNS failover to automatically route traffic to the resources in the secondary region. Set up the AWS Well-Architected Tool to easily get recommendations for improving your workloads based on the AWS best practices
+ In a secondary region, create a global secondary index of the DynamoDB table and replicate the auto-scaling group and application load balancer. Use Route 53 DNS failover to automatically route traffic to the resources in the secondary region. Set up the AWS Compute Optimizer to automatically get recommendations for improving your workloads based on the AWS best practices
+ Write a CloudFormation template that includes the auto-scaling group, application load balancer, and DynamoDB table. In the event of a failure, deploy the template in a secondary region. Use Route 53 DNS failover to automatically route traffic to the resources in the secondary region. Set up and configure the Amazon Managed Service for Prometheus service to receive insights for improving your workloads based on the AWS best practices.
+ Write a CloudFormation template that includes the auto-scaling group, application load balancer, and DynamoDB table. In the event of a failure, deploy the template in a secondary region. Configure Amazon EventBridge to trigger a Lambda function that updates the application’s Route 53 DNS record. Launch an Amazon Managed Grafana workspace to automatically receive tips and action items for improving your workloads based on the AWS best practices

<details close>
<summary>Answer</summary>
a
</details>

---

A company has a two-tier environment in its on-premises data center which is composed of an application tier and database tier. You are instructed to migrate their environment to the AWS cloud, and to design the subnets in their VPC with the following requirements:

1. There is an application load balancer that would distribute the incoming traffic among the servers in the application tier.
2. The application tier and the database tier must not be accessible from the public Internet. The application tier should only accept traffic coming from the load balancer.
3. The database tier contains very sensitive data. It must not share the same subnet with other AWS resources and its custom route table with other instances in the environment.
4. The environment must be highly available and scalable to handle a surge of incoming traffic over the Internet.

How many subnets should you create to meet the above requirements?
+ 2
+ 3
+ 4
+ 6

<details close>
<summary>Answer</summary>
d
</details>

---

A financial firm is designing an application architecture for its online trading platform that must have high availability and fault tolerance. Their Solutions Architect configured the application to use an Amazon S3 bucket located in the us-east-1 region to store large amounts of intraday financial data. The stored financial data in the bucket must not be affected even if there is an outage in one of the Availability Zones or if there's a regional service failure.

What should the Architect do to avoid any costly service disruptions and ensure data durability?
+ Copy the S3 bucket to an EBS-backed EC2 instance.
+ Create a Lifecycle Policy to regularly backup the S3 bucket to Amazon Glacier.
+ Create a new S3 bucket in another region and configure Cross-Account Access to the bucket located in us-east-1.
+ Enable Cross-Region Replication.

<details close>
<summary>Answer</summary>
d
</details>

---

A popular augmented reality (AR) mobile game is heavily using a RESTful API which is hosted in AWS. The API uses Amazon API Gateway and a DynamoDB table with a preconfigured read and write capacity. Based on your systems monitoring, the DynamoDB table begins to throttle requests during high peak loads which causes the slow performance of the game. 

Which of the following can you do to improve the performance of your app? 
+ Integrate an Application Load Balancer with your DynamoDB table.  
+ Add the DynamoDB table to an Auto Scaling Group.  
+ Use DynamoDB Auto Scaling  
+ Create an SQS queue in front of the DynamoDB table.  

<details close>
<summary>Answer</summary>
c
</details>

---

A data analytics company, which uses machine learning to collect and analyze consumer data, is using Redshift cluster as their data warehouse. You are instructed to implement a disaster recovery plan for their systems to ensure business continuity even in the event of an AWS region outage.   

Which of the following is the best approach to meet this requirement?
+ Create a scheduled job that will automatically take the snapshot of your Redshift Cluster and store it to an S3 bucket. Restore the snapshot in case of an AWS region outage.
+ Do nothing because Amazon Redshift is a highly available, fully-managed data warehouse which can withstand an outage of an entire AWS region.
+ Use Automated snapshots of your Redshift Cluster.
+ Enable Cross-Region Snapshots Copy in your Amazon Redshift Cluster.

<details close>
<summary>Answer</summary>
d
</details>

---

There is a new compliance rule in your company that audits every Windows and Linux EC2 instances each month to view any performance issues. They have more than a hundred EC2 instances running in production, and each must have a logging function that collects various system details regarding that instance. The SysOps team will periodically review these logs and analyze their contents using AWS Analytics tools, and the result will need to be retained in an S3 bucket.

In this scenario, what is the most efficient way to collect and analyze logs from the instances with minimal effort?
+ Install the unified CloudWatch Logs agent in each instance which will automatically collect and push data to CloudWatch Logs. Analyze the log data with CloudWatch Logs Insights.
+ Install AWS SDK in each instance and create a custom daemon script that would collect and push data to CloudWatch Logs periodically. Enable CloudWatch detailed monitoring and use CloudWatch Logs Insights to analyze the log data of all instances.
+ Install the AWS Systems Manager Agent (SSM Agent) in each instance which will automatically collect and push data to CloudWatch Logs. Analyze the log data with CloudWatch Logs Insights.
+ Install AWS Inspector Agent in each instance which will collect and push data to CloudWatch Logs periodically. Set up a CloudWatch dashboard to properly analyze the log data of all instances.

<details close>
<summary>Answer</summary>
a
</details>

---

A large multinational investment bank has a web application that requires a minimum of 4 EC2 instances to run to ensure that it can cater to its users across the globe. You are instructed to ensure fault tolerance of this system.

Which of the following is the best option?
+ Deploy an Auto Scaling group with 2 instances in each of 3 Availability Zones behind an Application Load Balancer.
+ Deploy an Auto Scaling group with 2 instances in each of 2 Availability Zones behind an Application Load Balancer.
+ Deploy  an Auto Scaling group with 4 instances in one Availability Zone behind an Application Load Balancer.
+ Deploy an Auto Scaling group with 1 instance in each of 4 Availability Zones behind an Application Load Balancer.

<details close>
<summary>Answer</summary>
a
</details>

---

A media company is using Amazon EC2, ELB, and S3 for its video-sharing portal for filmmakers. They are using a standard S3 storage class to store all high-quality videos that are frequently accessed only during the first three months of posting.

As a Solutions Architect, what should you do if the company needs to automatically transfer or archive media data from an S3 bucket to Glacier?
+ Use a custom shell script that transfers data from the S3 bucket to Glacier
+ Use Lifecycle Policies
+ Use Amazon SQS
+ Use Amazon SWF

<details close>
<summary>Answer</summary>
b
</details>

---

A company recently launched an e-commerce application that is running in eu-east-2 region, which strictly requires six EC2 instances running at all times. In that region, there are 3 Availability Zones (AZ) that you can use - eu-east-2a, eu-east-2b, and eu-east-2c.

Which of the following deployments provide 100% fault tolerance if any single AZ in the region becomes unavailable? (Select TWO.)
+ eu-east-2a with two EC2 instances, eu-east-2b with four EC2 instances, and eu-east-2c with two EC2 instances
+ eu-east-2a with two EC2 instances, eu-east-2b with two EC2 instances, and eu-east-2c with two EC2 instances
+ eu-east-2a with four EC2 instances, eu-east-2b with two EC2 instances, and eu-east-2c with two EC2 instances
+ eu-east-2a with six EC2 instances, eu-east-2b with six EC2 instances, and eu-east-2c with no EC2 instances
+ eu-east-2a with three EC2 instances, eu-east-2b with three EC2 instances, and eu-east-2c with three EC2 instances

<details close>
<summary>Answer</summary>
d,e
</details>

---

A company plans to develop a custom messaging service that will also be used to train their AI for an automatic response feature which they plan to implement in the future. Based on their research and tests, the service can receive up to thousands of messages a day, and all of these data are to be sent to Amazon EMR for further processing. It is crucial that none of the messages are lost, no duplicates are produced, and that they are processed in EMR in the same order as their arrival.

Which of the following options can satisfy the given requirement?

+ Create an Amazon Kinesis Data Stream to collect the messages.
+ Set up a default Amazon SQS queue to handle the messages.
+ Set up an Amazon SNS Topic to handle the messages.
+ Create a pipeline using AWS Data Pipeline to handle the messages.

<details close>
<summary>Answer</summary>
a
</details>

---

A company has several web applications with users all around the world. Each application is hosted in an Auto Scaling group of EC2 instances in multiple AZs behind an Application Load Balancer (ALB). All applications have their own fully qualified domain name. For added security, the applications must use a publicly trusted SSL certificate.

Which solution will meet this requirement with the LEAST operational overhead?
+ Launch a self-hosted certificate authority (CA) using the Let's Encrypt tool in an Amazon EC2 instance. Utilize the built-in ISRG Root X1 trusted root CA certificate. Generate a new SSL/TLS certificate using the `certbot` CLI utility. Associate the new certificate on the HTTPS listener of the ALBs.
+ Use the AWS Certificate Manager (ACM) to generate a public SSL/TLS certificate. Associate the new SSL/TLS certificate on the HTTPS listener of the ALBs.
+ Use OpenSSL to generate a self-signed certificate. Import the SSL/TLS certificate to the AWS Certificate Manager (ACM) and associate it with the HTTPS listener of the ALBs
+ Issue an SSL/TLS certificate using the AWS Certificate Manager Private Certificate Authority. Associate the new certificate on the HTTPS listener of the ALBs.

<details close>
<summary>Answer</summary>
b
</details>

---

A leading IT consulting company has an application which processes a large stream of financial data by an Amazon ECS Cluster then stores the result to a DynamoDB table. You have to design a solution to detect new entries in the DynamoDB table then automatically trigger a Lambda function to run some tests to verify the processed data.

What solution can be easily implemented to alert the Lambda function of new entries while requiring minimal configuration change to your architecture?
+ Use CloudWatch Alarms to trigger the Lambda function whenever a new entry is created in the DynamoDB table.
+ Invoke the Lambda functions using SNS each time that the ECS Cluster successfully processed financial data.
+ Enable DynamoDB Streams to capture table activity and automatically trigger the Lambda function
+ Use Systems Manager Automation to detect new entries in the DynamoDB table then automatically invoke the Lambda function for processing.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has hundreds of VPCs with multiple VPN connections to their data centers spanning 5 AWS Regions. As the number of its workloads grows, the company must be able to scale its networks across multiple accounts and VPCs to keep up. A Solutions Architect is tasked to interconnect all of the company's on-premises networks, VPNs, and VPCs into a single gateway, which includes support for inter-region peering across multiple AWS regions.

Which of the following is the BEST solution that the architect should set up to support the required interconnectivity?
+ Set up an AWS Direct Connect Gateway to achieve inter-region VPC access to all of the AWS resources and on-premises data centers. Set up a link aggregation group (LAG) to aggregate multiple connections at a single AWS Direct Connect endpoint in order to treat them as a single, managed connection. Launch a virtual private gateway in each VPC and then create a public virtual interface for each AWS Direct Connect connection to the Direct Connect Gateway.
+ Set up an AWS Transit Gateway in each region to interconnect all networks within it. Then, route traffic between the transit gateways through a peering connection.
+ Set up an AWS VPN CloudHub for inter-region VPC access and a Direct Connect gateway for the VPN connections to the on-premises data centers. Create a virtual private gateway in each VPC, then create a private virtual interface for each AWS Direct Connect connection to the Direct Connect gateway.
+ Enable inter-region VPC peering that allows peering relationships to be established between multiple VPCs across different AWS regions. Set up a networking configuration that ensures that the traffic will always stay on the global AWS backbone and never traverse the public Internet.

<details close>
<summary>Answer</summary>
b
</details>

---

A company is looking to store their confidential financial files in AWS which are accessed every week. The Architect was instructed to set up the storage system which uses envelope encryption and automates key rotation. It should also provide an audit trail that shows who used the encryption key and by whom for security purposes.

Which combination of actions should the Architect implement to satisfy the requirement in the most cost-effective way? (Select TWO.)
+ Use Amazon S3 to store the data.
+ Use Amazon S3 Glacier Deep Archive to store the data.
+ Configure Server-Side Encryption with Customer-Provided Keys (SSE-C).
+ Configure Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3).
+ Configure Server-Side Encryption with AWS KMS-Managed Keys (SSE-KMS).

<details close>
<summary>Answer</summary>
a,e
</details>

---

A company needs to implement a solution that will process real-time streaming data of its users across the globe. This will enable them to track and analyze globally-distributed user activity on their website and mobile applications, including clickstream analysis. The solution should process the data in close geographical proximity to their users and respond to user requests at low latencies.

Which of the following is the most suitable solution for this scenario?
+ Use a CloudFront web distribution and Route 53 with a latency-based routing policy, in order to process the data in close geographical proximity to users and respond to user requests at low latencies. Process real-time streaming data using Kinesis and durably store the results to an Amazon S3 bucket.
+ Integrate CloudFront with Lambda@Edge in order to process the data in close geographical proximity to users and respond to user requests at low latencies. Process real-time streaming data using Amazon Athena and durably store the results to an Amazon S3 bucket.
+ Use a CloudFront web distribution and Route 53 with a Geoproximity routing policy in order to process the data in close geographical proximity to users and respond to user requests at low latencies. Process real-time streaming data using Kinesis and durably store the results to an Amazon S3 bucket.
+ Integrate CloudFront with Lambda@Edge in order to process the data in close geographical proximity to users and respond to user requests at low latencies. Process real-time streaming data using Kinesis and durably store the results to an Amazon S3 bucket.

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
you can only route traffic using Route 53 since it does not have any computing capability
</details>

---

A company launched a global news website that is deployed to AWS and is using MySQL RDS. The website has millions of viewers from all over the world, which means that the website has a read-heavy database workload. All database transactions must be ACID compliant to ensure data integrity.

In this scenario, which of the following is the best option to use to increase the read-throughput on the MySQL database?
+ Enable Multi-AZ deployments
+ Enable Amazon RDS Standby Replicas
+ Enable Amazon RDS Read Replicas
+ Use SQS to queue up the requests

<details close>
<summary>Answer</summary>
c
</details>

---

A company deployed an online enrollment system database on a prestigious university, which is hosted in RDS. The Solutions Architect is required to monitor the database metrics in Amazon CloudWatch to ensure the availability of the enrollment system.

What are the enhanced monitoring metrics that Amazon CloudWatch gathers from Amazon RDS DB instances which provide more accurate information? (Select TWO.)
+ CPU Utilization
+ Database Connections
+ Freeable Memory
+ RDS child processes.
+ OS processes

<details close>
<summary>Answer</summary>
d,e
</details>

---

An automotive company is working on an autonomous vehicle development and deployment project using AWS. The solution requires High Performance Computing (HPC) in order to collect, store and manage massive amounts of data as well as to support deep learning frameworks. The Linux EC2 instances that will be used should have a lower latency and higher throughput than the TCP transport traditionally used in cloud-based HPC systems. It should also enhance the performance of inter-instance communication and must include an OS-bypass functionality to allow the HPC to communicate directly with the network interface hardware to provide low-latency, reliable transport functionality.

Which of the following is the MOST suitable solution that you should implement to achieve the above requirements?
+ Attach an Elastic Network Adapter (ENA) on each Amazon EC2 instance to accelerate High Performance Computing (HPC).
+ Attach an Elastic Fabric Adapter (EFA) on each Amazon EC2 instance to accelerate High Performance Computing (HPC).
+ Attach an Elastic Network Interface (ENI) on each Amazon EC2 instance to accelerate High Performance Computing (HPC).
+ Attach a Private Virtual Interface (VIF) on each Amazon EC2 instance to accelerate High Performance Computing (HPC).

<details close>
<summary>Answer</summary>
b
</details>


<details close>
<summary>Note</summary>
An Elastic Fabric Adapter (EFA) is a network device that you can attach to your Amazon EC2 instance to accelerate High Performance Computing (HPC) and machine learning applications. EFA enables you to achieve the application performance of an on-premises HPC cluster with the scalability, flexibility, and elasticity provided by the AWS Cloud.
</details>

---

A web application is hosted in an Auto Scaling group of EC2 instances deployed across multiple Availability Zones behind an Application Load Balancer. You need to implement an SSL solution for your system to improve its security which is why you requested an SSL/TLS certificate from a third-party certificate authority (CA).

Where can you safely import the SSL/TLS certificate of your application? (Select TWO.)
+ AWS Certificate Manager
+ IAM certificate store
+ A private S3 bucket with versioning enabled
+ An S3 bucket configured with server-side encryption with customer-provided encryption keys (SSE-C)
+ CloudFront

<details close>
<summary>Answer</summary>
a,b
</details>

---

A web application requires a minimum of six Amazon Elastic Compute Cloud (EC2) instances running at all times. You are tasked to deploy the application to three availability zones in the EU Ireland region (eu-west-1a, eu-west-1b, and eu-west-1c). It is required that the system is fault-tolerant up to the loss of one Availability Zone.

Which of the following setup is the most cost-effective solution which also maintains the fault-tolerance of your system?
+ 3 instances in eu-west-1a, 3 instances in eu-west-1b, and 3 instances in eu-west-1c
+ 6 instances in eu-west-1a, 6 instances in eu-west-1b, and 6 instances in eu-west-1c
+ 2 instances in eu-west-1a, 2 instances in eu-west-1b, and 2 instances in eu-west-1c
+ 6 instances in eu-west-1a, 6 instances in eu-west-1b, and no instances in eu-west-1c

<details close>
<summary>Answer</summary>
a
</details>

---

A Solutions Architect is working for a large global media company with multiple office locations all around the world. The Architect is instructed to build a system to distribute training videos to all employees.

Using CloudFront, what method would be used to serve content that is stored in S3, but not publicly accessible from S3 directly?
+ Create an Origin Access Identity (OAI) for CloudFront and grant access to the objects in your S3 bucket to that OAI.
+ Create an Identity and Access Management (IAM) user for CloudFront and grant access to the objects in your S3 bucket to that IAM user.
+ Create an S3 bucket policy that lists the CloudFront distribution ID as the principal and the target bucket as the Amazon Resource Name (ARN).
+ Create a web ACL in AWS WAF to block any public S3 access and attach it to the Amazon CloudFront distribution.
<details close>
<summary>Answer</summary>
a
</details>

---

A company has a fixed set of Amazon EC2 instances inside a VPC in the AWS cloud. The instances run a mission-critical application. In a recent incident, one of the EC2 instances suddenly powered down which affected the availability of the application. To avoid this incident in the future, the management wants to get notified of any upcoming AWS events that may affect these EC2 instances.

Which of the following options is the recommended action to meet the above requirements?

+ Create an Amazon EventBridge (Amazon CloudWatch Events) rule that is scheduled to run every 24 hours. Set the target to an AWS Lambda function that will check AWS Service Health Dashboard and send notifications for any events that may affect Amazon EC2 instances.
+ Set up an Amazon EventBridge (Amazon CloudWatch Events) rule to check for any status change for Amazon EC2 instances. Set the target to an AWS Lambda function that will send a notification and restart the affected Amazon EC2 instances.
+ Create an Amazon EventBridge (Amazon CloudWatch Events) rule to check for AWS Personal Health Dashboard events that are related to Amazon EC2 instances. To send notifications, set an Amazon SNS topic as a target for the rule.
+ Set up an Amazon EventBridge (Amazon CloudWatch Events) rule to check for AWS Service Health Dashboard events that are related to Amazon EC2 instances. To send notifications, set an Amazon SNS topic as a target for the rule.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
AWS Health provides ongoing visibility into your resource performance and the availability of your AWS services and accounts
</details>

---

An online survey startup is collecting real estate data in the United States for several years. The startup already has a total of 5 TB of data stored in an Amazon S3 bucket located in the us-east-1 Region. All real estate data must be shared with a European AWS Managed Service Provider (MSP) Partner which also uses Amazon S3 for storage. Due to budget constraints, the startup must keep its data transfer costs in S3 as low as possible and disable anonymous access.

Which solution meets this requirement MOST cost-effectively?
+ Enable the Requester Pays feature on the Amazon S3 bucket to lower data transfer costs and disable anonymous access
+ Enable Cross-Region Replication(CRR) on the startup’s S3 bucket to automatically copy the S3 content to the partner’s S3 bucket in Europe.
+ Enable cross-account access of the startup’s S3 bucket to allow the data downloads and exclusive access from the partner’s AWS account
+ Enable S3 Object Lock in governance mode to lower data transfer costs and set a Legal Hold for each object to disable anonymous access

<details close>
<summary>Answer</summary>
a
</details>

---

A company hosts all its applications on its data center on the US East coast. Most of the workloads are legacy applications that are hosted on individual virtual machines running in Linux and Windows operating systems. The company plans to migrate all of its VM workloads to the AWS cloud. To minimize changes in the applications during the migration process, it has been decided that the company will use a “lift-and-shift” strategy. The company also wants to minimize downtime during the migration process.

Which of the following option should the Solutions Architect implement for this scenario?
+ Export the on-premises VMs and upload the images to an Amazon S3 bucket. Use VM Import/Export service to import the images and launch them as Amazon EC2 instances.
+ Install the AWS Replication Agent on each of the on-premises VMs to continuously replicate the servers to AWS. Use AWS Migration Service (AWS MGN) to launch test instances and perform cutover once testing is completed.
+ Use the AWS Application Discovery Service for lift-and-shift migrations. Deploy the AWS Application Discovery Agent to the on-premises data center to start the replication process. After the replication task is completed, launch Amazon EC2 instances based on the created AMIs.
+ Utilize AWS DataSync to migrate the application workloads to AWS. Deploy the AWS DataSync VM on the on-premises data center. Once replication is completed, launch Amazon EC2 instances based on the created AMIs.

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
AWS Application Migration Service (AWS MGN) is the primary migration service recommended for lift-and-shift migrations to AWS. AWS encourage customers who are currently using CloudEndure Migration or AWS SMS to switch to AWS MGN for future migrations. AWS MGN enables organizations to move applications to AWS without having to make any changes to the applications, their architecture, or the migrated servers.
</details>

---

A company is using an On-Demand EC2 instance to host a legacy web application that uses an Amazon Instance Store-Backed AMI. The web application should be decommissioned as soon as possible and hence, you need to terminate the EC2 instance.

When the instance is terminated, what happens to the data on the root volume?
+ Data is automatically saved as an EBS snapshot.
+ Data is automatically saved as an EBS volume.
+ Data is unavailable until the instance is restarted.
+ Data is automatically deleted.

<details close>
<summary>Answer</summary>
d
</details>

---

A company decided to change its third-party data analytics tool to a cheaper solution. They sent a full data export on a CSV file which contains all of their analytics information. You then save the CSV file to an S3 bucket for storage. Your manager asked you to do some validation on the provided data export.

In this scenario, what is the most cost-effective and easiest way to analyze export data using standard SQL?
+ Create a migration tool to load the CSV export file from S3 to a DynamoDB instance. Once the data has been loaded, run queries using DynamoDB.
+ Use mysqldump client utility to load the CSV export file from S3 to a MySQL RDS instance. Run some SQL queries once the data has been loaded to complete your validation.
+ To be able to run SQL queries, use AWS Athena to analyze the export data file in S3.
+ Use a migration tool to load the CSV export file from S3 to a database that is designed for online analytic processing (OLAP) such as AWS RedShift. Run some queries once the data has been loaded to complete your validation.

<details close>
<summary>Answer</summary>
c
</details>

---

A startup plans to develop a multiplayer game that uses UDP as the protocol for communication between clients and game servers. The data of the users will be stored in a key-value store. As the Solutions Architect, you need to implement a solution that will distribute the traffic across a number of servers.

Which of the following could help you achieve this requirement?
+ Distribute the traffic using Application Load Balancer and store the data in Amazon DynamoDB.
+ Distribute the traffic using Network Load Balancer and store the data in Amazon Aurora.
+ Distribute the traffic using Application Load Balancer and store the data in Amazon RDS.
+ Distribute the traffic using Network Load Balancer and store the data in Amazon DynamoDB.

<details close>
<summary>Answer</summary>
d
</details>

---

A media company needs to configure an Amazon S3 bucket to serve static assets for the public-facing web application. Which methods ensure that all of the objects uploaded to the S3 bucket can be read publicly all over the Internet? (Select TWO.)
+ Grant public read access to the object when uploading it using the S3 Console.
+ Configure the cross-origin resource sharing (CORS) of the S3 bucket to allow objects to be publicly accessible from all domains.
+ Configure the S3 bucket policy to set all objects to public read.
+ Create an IAM role to set the objects inside the S3 bucket to public read.
+ Do nothing. Amazon S3 objects are already public by default.

<details close>
<summary>Answer</summary>
a,c
</details>

---

A company needs to integrate the Lightweight Directory Access Protocol (LDAP) directory service from the on-premises data center to the AWS VPC using IAM. The identity store which is currently being used is not compatible with SAML.

Which of the following provides the most valid approach to implement the integration?
+ Use an IAM policy that references the LDAP identifiers and AWS credentials.
+ Use AWS Single Sign-On (SSO) service to enable single sign-on between AWS and your LDAP.
+ Develop an on-premises custom identity broker application and use STS to issue short-lived AWS credentials.
+ Use IAM roles to rotate the IAM credentials whenever LDAP credentials are updated.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
f your identity store is not compatible with SAML 2.0 then you can build a custom identity broker application to perform a similar function. The broker application authenticates users, requests temporary credentials for users from AWS, and then provides them to the user to access AWS resources.

The application verifies that employees are signed into the existing corporate network's identity and authentication system, which might use LDAP, Active Directory, or another system. The identity broker application then obtains temporary security credentials for the employees.
</details>

---

A company has a team of developers that provisions their own resources on the AWS cloud. The developers use IAM user access keys to automate their resource provisioning and application testing processes in AWS. To ensure proper security compliance, the security team wants to automate the process of deactivating and deleting any IAM user access key that is over 90 days old.

Which solution will meet these requirements with the LEAST operational effort?
+ Use the AWS Config managed rule to check if the IAM user access keys are not rotated within 90 days. Create an Amazon EventBridge (Amazon CloudWatch Events) rule for the non-compliant keys, and define a target to invoke a custom Lambda function to deactivate and delete the keys.
+ Create an Amazon EventBridge (Amazon CloudWatch Events) rule to filter IAM user access keys older than 90 days. Schedule an AWS Batch job that runs every 24 hours to delete all the specified access keys.
+ Create a custom AWS Config rule to check for the max-age of IAM access keys. Schedule an AWS Batch job that runs every 24 hours to delete all the non-compliant access keys.
+ Create an Amazon EventBridge (Amazon CloudWatch Events) rule to filter IAM user access keys older than 90 days. Define a target to invoke a Lambda function to deactivate and delete the old access keys.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
AWS Config can only use Systems Manager Automation documents as remediation actions. Moreover, the AWS Batch service cannot be used for remediating non-compliant resources like IAM access keys.
</details>

---

A company launched an EC2 instance in the newly created VPC. They noticed that the generated instance does not have an associated DNS hostname.

Which of the following options could be a valid reason for this issue?
+ The newly created VPC has an invalid CIDR block.
+ Amazon Route53 is not enabled.
+ The DNS resolution and DNS hostname of the VPC configuration should be enabled.
+ The security group of the EC2 instance needs to be modified.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
When you launch an EC2 instance into a default VPC, AWS provides it with public and private DNS hostnames that correspond to the public IPv4 and private IPv4 addresses for the instance.

However, when you launch an instance into a non-default VPC, AWS provides the instance with a private DNS hostname only. New instances will only be provided with a public DNS hostname depending on these two DNS attributes: the DNS resolution and DNS hostnames that you have specified for your VPC and if your instance has a public IPv4 address.

In this case, the new EC2 instance does not automatically get a DNS hostname because the DNS resolution and DNS hostnames attributes are disabled in the newly created VPC.
</details>

---

A hospital has a mission-critical application that uses a RESTful API powered by Amazon API Gateway and AWS Lambda. The medical officers upload PDF reports to the system which are then stored as static media content in an Amazon S3 bucket.

The security team wants to improve its visibility when it comes to cyber-attacks and ensure HIPAA (Health Insurance Portability and Accountability Act) compliance. The company is searching for a solution that continuously monitors object-level S3 API operations and identifies protected health information (PHI) in the reports, with minimal changes in their existing Lambda function.

Which of the following solutions will meet these requirements with the LEAST operational overhead?
+ Use Amazon Textract Medical with PII redaction turned on to extract and filter sensitive text from the PDF reports. Create a new Lambda function that calls the regular Amazon Comprehend API to identify the PHI from the extracted text.
+ Use Amazon Textract to extract the text from the PDF reports. Integrate Amazon Comprehend Medical with the existing Lambda function to identify the PHI from the extracted text.
+ Use Amazon Transcribe to read and analyze the PDF reports using the `StartTranscriptionJob API`  operation. Use Amazon SageMaker Ground Truth to label and detect protected health information (PHI) content with low-confidence predictions.
+ Use Amazon Rekognition to extract the text data from the PDF reports. Integrate the Amazon Comprehend Medical service with the existing Lambda functions to identify the PHI from the extracted text.

<details close>
<summary>Answer</summary>
b
</details>

---

A tech startup has recently received a Series A round of funding to continue building their mobile forex trading application. You are hired to set up their cloud architecture in AWS and to implement a highly available, fault tolerant system. For their database, they are using DynamoDB and for authentication, they have chosen to use Cognito. Since the mobile application contains confidential financial transactions, there is a requirement to add a second authentication method that doesn't rely solely on user name and password.   

How can you implement this in AWS?

+ Add multi-factor authentication (MFA) to a user pool in Cognito to protect the identity of your users.
+ Add a new IAM policy to a user pool in Cognito.
+ Integrate Cognito with Amazon SNS Mobile Push to allow additional authentication via SMS.
+ Develop a custom application that integrates with Cognito that implements a second layer of authentication.

<details close>
<summary>Answer</summary>
a
</details>

---

There are a few, easily reproducible but confidential files that your client wants to store in AWS without worrying about storage capacity. For the first month, all of these files will be accessed frequently but after that, they will rarely be accessed at all. The old files will only be accessed by developers so there is no set retrieval time requirement. However, the files under a specific `tdojo-finance` prefix in the S3 bucket will be used for post-processing that requires millisecond retrieval time.

Given these conditions, which of the following options would be the most cost-effective solution for your client's storage needs?
+ Store the files in S3 then after a month, change the storage class of the bucket to S3-IA using lifecycle policy.
+ Store the files in S3 then after a month, change the storage class of the bucket to Intelligent-Tiering using lifecycle policy.
+ Store the files in S3 then after a month, change the storage class of the `tdojo-finance`  prefix to One Zone-IA while the remaining go to Glacier using lifecycle policy.
+ Store the files in S3 then after a month, change the storage class of the `tdojo-finance` prefix to S3-IA while the remaining go to Glacier using lifecycle policy.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
 Remember that the files are easily reproducible so you can safely move the data to S3-One Zone IA and in case there is an outage, you can simply generate the missing data again.
</details>

---

A Solutions Architect is designing the cloud architecture for the enterprise application suite of the company. Both the web and application tiers need to access the Internet to fetch data from public APIs. However, these servers should be inaccessible from the Internet.

Which of the following steps should the Architect implement to meet the above requirements?
+ Deploy the web and application tier instances to a private subnet and then allocate an Elastic IP address to each EC2 instance.
+ Deploy a NAT gateway in the private subnet and add a route to it from the public subnet where the web and application tiers are hosted.
+ Deploy the web and application tier instances to a public subnet and then allocate an Elastic IP address to each EC2 instance.
+ Deploy a NAT gateway in the public subnet and add a route to it from the private subnet where the web and application tiers are hosted.

<details close>
<summary>Answer</summary>
b
</details>

---

A company has a web-based order processing system that is currently using a standard queue in Amazon SQS. The IT Manager noticed that there are a lot of cases where an order was processed twice. This issue has caused a lot of trouble in processing and made the customers very unhappy. The manager has asked you to ensure that this issue will not recur.

What can you do to prevent this from happening again in the future? (Select TWO.)
+ Alter the retention period in Amazon SQS.
+ Alter the visibility timeout of SQS.
+ Replace Amazon SQS and instead, use Amazon Simple Workflow service.
+ Change the message size in SQS.
+ Use an Amazon SQS FIFO Queue instead.

<details close>
<summary>Answer</summary>
c,e
</details>

<details close>
<summary>Note</summary>
Amazon SWF provides useful guarantees around task assignments. It ensures that a task is never duplicated and is assigned only once. Thus, even though you may have multiple workers for a particular activity type (or a number of instances of a decider), Amazon SWF will give a specific task to only one worker (or one decider instance). Additionally, Amazon SWF keeps at most one decision task outstanding at a time for workflow execution. Thus, you can run multiple decider instances without worrying about two instances operating on the same execution simultaneously. These facilities enable you to coordinate your workflow without worrying about duplicate, lost, or conflicting tasks.
</details>

---

A new company policy requires IAM users to change their passwords’ minimum length to 12 characters. After a random inspection, you found out that there are still employees who do not follow the policy.

How can you automatically check and evaluate whether the current password policy for an account complies with the company password policy?
+ Configure AWS Config to trigger an evaluation that will check the compliance for a user’s password periodically.
+ Create a CloudTrail trail. Filter the result by setting the attribute to “Event Name” and lookup value to “ChangePassword”. This easily gives you the list of users who have made changes to their passwords.
+ Create a Scheduled Lambda Function that will run a custom script to check compliance against changes made to the passwords periodically.
+ Create a rule in the Amazon CloudWatch event. Build an event pattern to match events on IAM. Set the event name to “ChangePassword” in the event pattern. Configure SNS to send notifications to you whenever a user has made changes to his password.

<details close>
<summary>Answer</summary>
a
</details>

---

An organization plans to use an AWS Direct Connect connection to establish a dedicated connection between its on-premises network and AWS. The organization needs to launch a fully managed solution that will automate and accelerate the replication of data to and from various AWS storage services.

Which of the following solutions would you recommend?
+ Use an AWS DataSync agent to rapidly move the data over a service endpoint.
+ Use an AWS Storage Gateway tape gateway to store data on virtual tape cartridges and asynchronously copy your backups to AWS.
+ Use an AWS DataSync agent to rapidly move the data over the Internet.
+ Use an AWS Storage Gateway file gateway to store and retrieve files directly using the SMB file system protocol.

<details close>
<summary>Answer</summary>
a
</details>

---

A Solutions Architect is designing a setup for a database that will run on Amazon RDS for MySQL. He needs to ensure that the database can automatically failover to an RDS instance to continue operating in the event of failure. The architecture should also be as highly available as possible.

Which among the following actions should the Solutions Architect do?
+ Create a standby replica in another availability zone by enabling Multi-AZ deployment.
+ Create a read replica in the same region where the DB instance resides. In addition, create a read replica in a different region to survive a region’s failure. In the event of an Availability Zone outage, promote any replica to become the primary instance.
+ Create five read replicas across different availability zones. In the event of an Availability Zone outage, promote any replica to become the primary instance.
+ Create five cross-region read replicas in each region. In the event of an Availability Zone outage, promote any replica to become the primary instance.

<details close>
<summary>Answer</summary>
a
</details>

---

An Auto Scaling group (ASG) of Linux EC2 instances has an Amazon FSx for OpenZFS file system with basic monitoring enabled in CloudWatch. The Solutions Architect noticed that the legacy web application hosted in the ASG takes a long time to load. After checking the instances, the Architect noticed that the ASG is not launching more instances as it should be, even though the servers already have high memory usage.

Which of the following options should the Architect implement to solve this issue?

+ Implement an AI solution that leverages Amazon Comprehend to track the near-real-time memory usage of each and every EC2 instance? Use Amazon SageMaker to automatically trigger the Auto Scaling event if there is high memory usage.
+ Install the CloudWatch unified agent to the EC2 instances. Set up a custom parameter in AWS Systems Manager Parameter Store with the CloudWatch agent configuration to create an aggregated metric on memory usage percentage. Scale the Auto Scaling group based on the aggregated metric.
+ Enable detailed monitoring on the Amazon EC2 instances of the Auto Scaling group. Use Amazon Forecast to automatically scale out the Auto Scaling group based on the aggregated memory usage of Amazon EC2 instances.
+ Set up Amazon Rekognition to automatically identify and recognize the cause of the high memory usage. Use the AWS Well-Architected Tool to automatically trigger the scale-out event in the ASG based on the overall memory usage.


<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
The premise of the scenario is that the EC2 servers have high memory usage, but since this specific metric is not tracked by the Auto Scaling group by default, the scaling out activity is not being triggered. Remember that by default, CloudWatch doesn't monitor memory usage but only the CPU utilization, Network utilization, Disk performance, and Disk Reads/Writes.
</details>

---

A company plans to deploy an application in an Amazon EC2 instance. The application will perform the following tasks:

- Read large datasets from an Amazon S3 bucket.

- Execute multi-stage analysis on the datasets.

- Save the results to Amazon RDS.

During multi-stage analysis, the application will store a large number of temporary files in the instance storage. As the Solutions Architect, you need to recommend the fastest storage option with high I/O performance for the temporary files.

Which of the following options fulfills this requirement?

+ Enable Transfer Acceleration in Amazon S3.
+ Configure RAID 1 in multiple instance store volumes.
+ Attach multiple Provisioned IOPS SSD volumes in the instance.
+ Configure RAID 0 in multiple instance store volumes.


<details close>
<summary>Answer</summary>
d
</details>


<details close>
<summary>Note</summary>
RAID 0 configuration enables you to improve your storage volumes' performance by distributing the I/O across the volumes in a stripe. Therefore, if you add a storage volume, you get the straight addition of throughput and IOPS. This configuration can be implemented on both EBS or instance store volumes. Since the main requirement in the scenario is storage performance, you need to use an instance store volume. It uses NVMe or SATA-based SSD to deliver high random I/O performance. This type of storage is a good option when you need storage with very low latency and you don't need the data to persist when the instance terminates.

Attach multiple Provisioned IOPS SSD volumes in the instance is incorrect because persistent storage is not needed in the scenario. Also, instance store volumes have greater I/O performance than EBS volumes.

</details>

---

A company plans to migrate a NoSQL database to an EC2 instance. The database is configured to replicate the data automatically to keep multiple copies of data for redundancy. The Solutions Architect needs to launch an instance that has a high IOPS and sequential read/write access.

Which of the following options fulfills the requirement if I/O throughput is the highest priority?

+ Use Storage optimized instances with instance store volume.
+ Use General purpose instances with EBS volume.
+ Use Compute optimized instance with instance store volume.
+ Use Memory optimized instances with EBS volume.

<details close>
<summary>Answer</summary>
a
</details>

---

A company has stored 200 TB of backup files in Amazon S3. The files are in a vendor-proprietary format. The Solutions Architect needs to use the vendor's proprietary file conversion software to retrieve the files from their Amazon S3 bucket, transform the files to an industry-standard format, and re-upload the files back to Amazon S3. The solution must minimize the data transfer costs.

Which of the following options can satisfy the given requirement?
+ Install the file conversion software in Amazon S3. Use S3 Batch Operations to perform data transformation.
+ Export the data using AWS Snowball Edge device. Install the file conversion software on the device. Transform the data and re-upload it to Amazon S3.
+ Deploy the EC2 instance in a different Region. Install the conversion software on the instance. Perform data transformation and re-upload it to Amazon S3.
+ Deploy the EC2 instance in the same Region as Amazon S3. Install the file conversion software on the instance. Perform data transformation and re-upload it to Amazon S3.

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
You pay for all bandwidth into and out of Amazon S3, except for the following:

- Data transferred in from the Internet.

- Data transferred out to an Amazon EC2 instance, when the instance is in the same AWS Region as the S3 bucket (including to a different account in the same AWS region).

- Data transferred out to Amazon CloudFront.

To minimize the data transfer charges, you need to deploy the EC2 instance in the same Region as Amazon S3. Take note that there is no data transfer cost between S3 and EC2 in the same AWS Region. Install the conversion software on the instance to perform data transformation and re-upload the data to Amazon S3.


</details>

---

Every week, an e-commerce company announces a sales promotion, causing its application hosted on an Auto Scaling group to experience intermittent downtime. Because of long initialization times, the application only becomes operational minutes before a new EC2 instance turns into `RUNNING` state. A solutions architect must devise a solution that launches capacity in advance based on a forecasted load in order to scale faster.

Which solution meets the requirements with the least amount of effort?
+ Configure the Auto Scaling group to use predictive scaling.
+ Use Amazon Forecast to analyze and predict the workload pattern of the application. Create a scheduled scaling policy based on the prediction results.
+ Create a dynamic scaling policy based on the historical average CPU load of the application.
+ Create a Scheduled Amazon EventBridge Rule that runs a scaling job on a Lambda function every midnight.

<details close>
<summary>Answer</summary>
a
</details>

---
A startup is planning to set up and govern a secure, compliant, multi-account AWS environment in preparation for its upcoming projects. The IT Manager requires the solution to have a dashboard for continuous detection of policy non-conformance and non-compliant resources across the enterprise, as well as to comply with the AWS multi-account strategy best practices.

Which of the following offers the easiest way to fulfill this task?
+ Use AWS Organizations to build a landing zone to automatically provision new AWS accounts. Utilize the AWS Personal Health Dashboard to see provisioned accounts across your enterprise. Enable preventive and detective guardrails enabled for policy enforcement.
+ Launch new AWS member accounts using the AWS CloudFormation StackSets. Use AWS Config to continuously track the configuration changes and set rules to monitor non-compliant resources. Set up a Multi-Account Multi-Region Data Aggregator to monitor compliance data for rules and accounts in an aggregated view
+ Use AWS Control Tower to launch a landing zone to automatically provision and configure new accounts through an Account Factory. Utilize the AWS Control Tower dashboard to monitor provisioned accounts across your enterprise. Set up preventive and detective guardrails for policy enforcement.
+ Use AWS Service Catalog to launch new AWS member accounts. Configure AWS Service Catalog Launch Constraints to continuously track configuration changes and monitor non-compliant resources. Set up a Multi-Account Multi-Region Data Aggregator to monitor compliance data for rules and accounts in an aggregated view

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
AWS Control Tower offers a straightforward way to set up and govern an AWS multi-account environment, following prescriptive best practices. AWS Control Tower orchestrates the capabilities of several other AWS services, including AWS Organizations, AWS Service Catalog, and AWS Single Sign-On, to build a landing zone in less than an hour. It offers a dashboard to see provisioned accounts across your enterprise, guardrails enabled for policy enforcement, guardrails enabled for continuous detection of policy non-conformance, and non-compliant resources organized by accounts and OUs
</details>

---


