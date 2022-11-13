# Solution Architect Exam#2 Practice Set
A company has an on-premises MySQL database that needs to be replicated in Amazon S3 as CSV files. The database will eventually be launched to an Amazon Aurora Serverless cluster and be integrated with an RDS Proxy to allow the web applications to pool and share database connections. Once data has been fully copied, the ongoing changes to the on-premises database should be continually streamed into the S3 bucket. The company wants a solution that can be implemented with little management overhead yet still highly secure.

Which ingestion pattern should a solutions architect take?
+ Set up a full load replication task using AWS Database Migration Service (AWS DMS). Launch an AWS DMS endpoint with SSL using the AWS Network Firewall service.
+ Create a full load and change data capture (CDC) replication task using AWS Database Migration Service (AWS DMS). Add a new Certificate Authority (CA) certificate and create an AWS DMS endpoint with SSL.
+ Use an AWS Snowball Edge cluster to migrate data to Amazon S3 and AWS DataSync to capture ongoing changes. Create your own custom AWS KMS envelope encryption key for the associated AWS Snowball Edge job.
+ Use AWS Schema Conversion Tool (AWS SCT) to convert MySQL data to CSV files. Set up the AWS Server Migration Service (AWS MGN) to capture ongoing changes from the on-premises MySQL database and send them to Amazon S3.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has a serverless application made up of AWS Amplify, Amazon API Gateway and a Lambda function. The application is connected to an Amazon RDS MySQL database instance inside a private subnet. A Lambda Function URL is also implemented as the dedicated HTTPS endpoint for the function, which has the following value: 

`https://12june1898pil1pinas.lambda-url.us-west-2.on.aws/`

There are times during peak loads when the database throws a “too many connections” error preventing the users from accessing the application.

Which solution could the company take to resolve the issue?

+ Increase the concurrency limit of the Lambda function
+ Provision an RDS Proxy between the Lambda function and RDS database instance
+ Increase the rate limit of API Gateway
+ Increase the memory allocation of the Lambda function

<details close>
<summary>Answer</summary>
b
</details>


<details close>
<summary>Note</summary>
RDS Proxy helps you manage a large number of connections from Lambda to an RDS database by establishing a warm connection pool to the database. Your Lambda functions interact with RDS Proxy instead of your database instance. It handles the connection pooling necessary for scaling many simultaneous connections created by concurrent Lambda functions. This allows your Lambda applications to reuse existing connections, rather than creating new connections for every function invocation.

</details>


---

A music publishing company is building a multitier web application that requires a key-value store which will save the document models. Each model is composed of band ID, album ID, song ID, composer ID, lyrics, and other data. The web tier will be hosted in an Amazon ECS cluster with AWS Fargate launch type.

Which of the following is the MOST suitable setup for the database-tier?
+ Launch an Amazon RDS database with Read Replicas.
+ Launch a DynamoDB table.
+ Use Amazon WorkDocs to store the document models.
+ Launch an Amazon Aurora Serverless database.

<details close>
<summary>Answer</summary>
b
</details>

---

A company plans to migrate its suite of containerized applications running on-premises to a container service in AWS. The solution must be cloud-agnostic and use an open-source platform that can automatically manage containerized workloads and services. It should also use the same configuration and tools across various production environments.

What should the Solution Architect do to properly migrate and satisfy the given requirement?
+ Migrate the application to Amazon Container Registry (ECR) with Amazon EC2 instance worker nodes.
+ Migrate the application to Amazon Elastic Kubernetes Service with EKS worker nodes.
+ Migrate the application to Amazon Elastic Container Service with ECS tasks that use the AWS Fargate launch type.
+ Migrate the application to Amazon Elastic Container Service with ECS tasks that use the Amazon EC2 launch type.

<details close>
<summary>Answer</summary>
b
</details>

---

A media company has two VPCs: VPC-1 and VPC-2 with peering connection between each other. VPC-1 only contains private subnets while VPC-2 only contains public subnets. The company uses a single AWS Direct Connect connection and a virtual interface to connect their on-premises network with VPC-1.

Which of the following options increase the fault tolerance of the connection to VPC-1? (Select TWO.)
+ Use the AWS VPN CloudHub to create a new AWS Direct Connect connection and private virtual interface in the same region as VPC-2.
+ Establish a hardware VPN over the Internet between VPC-1 and the on-premises network.
+ Establish a hardware VPN over the Internet between VPC-2 and the on-premises network.
+ Establish a new AWS Direct Connect connection and private virtual interface in the same region as VPC-2.
+ Establish another AWS Direct Connect connection and private virtual interface in the same AWS region as VPC-1.

<details close>
<summary>Answer</summary>
b,e
</details>

---

An online events registration system is hosted in AWS and uses ECS to host its front-end tier and an RDS configured with Multi-AZ for its database tier. What are the events that will make Amazon RDS automatically perform a failover to the standby replica? (Select TWO.)
+ Loss of availability in primary Availability Zone
+ Storage failure on primary
+ Storage failure on secondary DB instance
+ In the event of Read Replica failure
+ Compute unit failure on secondary DB instance

<details close>
<summary>Answer</summary>
a,b
</details>

---

A company wants to streamline the process of creating multiple AWS accounts within an AWS Organization. Each organization unit (OU) must be able to launch new accounts with preapproved configurations from the security team which will standardize the baselines and network configurations for all accounts in the organization.

Which solution entails the least amount of effort to implement?
+ Set up an AWS Control Tower Landing Zone. Enable pre-packaged guardrails to enforce policies or detect violations.
+ Configure AWS Resource Access Manager (AWS RAM) to launch new AWS accounts as well as standardize the baselines and network configurations for each organization unit
+ Set up an AWS Config aggregator on the root account of the organization to enable multi-account, multi-region data aggregation. Deploy conformance packs to standardize the baselines and network configurations for all accounts.
+ Centralized the creation of AWS accounts using AWS Systems Manager OpsCenter. Enforce policies and detect violations to all AWS accounts using AWS Security Hub.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
AWS Control Tower provides a single location to easily set up your new well-architected multi-account environment and govern your AWS workloads with rules for security, operations, and internal compliance. You can automate the setup of your AWS environment with best-practices blueprints for multi-account structure, identity, access management, and account provisioning workflow. For ongoing governance, you can select and apply pre-packaged policies enterprise-wide or to specific groups of accounts.

AWS Control Tower offers "guardrails" for ongoing governance of your AWS environment. Guardrails provide governance controls by preventing the deployment of resources that don’t conform to selected policies or detecting non-conformance of provisioned resources. AWS Control Tower automatically implements guardrails using multiple building blocks such as AWS CloudFormation to establish a baseline, AWS Organizations service control policies (SCPs) to prevent configuration changes, and AWS Config rules to continuously detect non-conformance.

In this scenario, the requirement is to simplify the creation of AWS accounts that have governance guardrails and a defined baseline in place. To save time and resources, you can use AWS Control Tower to automate account creation. With the appropriate user group permissions, you can specify standardized baselines and network configurations for all accounts in the organization.
</details>

---

A Solutions Architect created a new Standard-class S3 bucket to store financial reports that are not frequently accessed but should immediately be available when an auditor requests them. To save costs, the Architect changed the storage class of the S3 bucket from Standard to Infrequent Access storage class.

In Amazon S3 Standard - Infrequent Access storage class, which of the following statements are true? (Select TWO.)
+ It is designed for data that is accessed less frequently.
+ It automatically moves data to the most cost-effective access tier without any operational overhead.
+ It is designed for data that requires rapid access when needed.
+ It provides high latency and low throughput performance
+ Ideal to use for data archiving.

<details close>
<summary>Answer</summary>
a,c
</details>

---

A solutions architect is designing a three-tier website that will be hosted on an Amazon EC2 Auto Scaling group fronted by an Internet-facing Application Load Balancer (ALB). The website will persist data to an Amazon Aurora Serverless DB cluster, which will also be used for generating monthly reports.

The company requires a network topology that follows a layered approach to reduce the impact of misconfigured security groups or network access lists. Web filtering must also be enabled to automatically stop traffic to known malicious URLs and to immediately drop requests coming from blacklisted fully qualified domain names (FQDNs).

Which network topology provides the minimum resources needed for the website to work?
+ Set up an Application Load Balancer deployed in a public subnet, then host the Auto Scaling Group of Amazon EC2 instances and the Aurora Serverless DB cluster in private subnets. Launch an AWS Network Firewall with the appropriate firewall policy to automatically stop traffic to known malicious URLs and drop requests coming from blacklisted FQDNs. Reroute your Amazon VPC network traffic through the firewall endpoints.
+ Set up an Application Load Balancer and a NAT Gateway deployed in public subnets. Launch the Auto Scaling Group of Amazon EC2 instances and Aurora Serverless DB cluster in private subnets. Directly integrate the AWS Network Firewall with the Application Load Balancer to automatically stop traffic to known malicious URLs and drop requests coming from blacklisted FQDNs.
+ Set up an Application Load Balancer in front of an Auto Scaling group of Amazon EC2 instances with an Aurora Serverless DB cluster to persist data. Launch a NAT Gateway in a public subnet to restrict external services from initiating a connection to the EC2 instances and immediately drop requests from unauthorized FQDNs. Deploy all other resources in private subnets.
+ Set up an Auto Scaling group of Amazon EC2 instances behind an Application Load Balancer with an Aurora Serverless DB cluster to store application data. Deploy all resources in a public subnet. Configure host-based routing to the Application Load Balancer to stop traffic to known malicious URLs and drop requests from blacklisted FQDNs.

<details close>
<summary>Answer</summary>
a
</details>


<details close>
<summary>Note</summary>
A defense-in-depth strategy is one of the design principles for security in the AWS cloud. This strategy entails implementing security controls at multiple layers (for example, edge of network, VPC, load balancing, every instance and compute service, operating system, application, and code).
</details>

---

A Solutions Architect is building a cloud infrastructure where EC2 instances require access to various AWS services such as S3 and Redshift. The Architect will also need to provide access to system administrators so they can deploy and test their changes.

Which configuration should be used to ensure that the access to the resources is secured and not compromised? (Select TWO.)
+ Enable Multi-Factor Authentication.
+ Assign an IAM role to the Amazon EC2 instance.
+ Store the AWS Access Keys in the EC2 instance.
+ Assign an IAM user for each Amazon EC2 Instance.
+ Store the AWS Access Keys in ACM.

<details close>
<summary>Answer</summary>
a,b
</details>

---

A media company is setting up an ECS batch architecture for its image processing application. It will be hosted in an Amazon ECS Cluster with two ECS tasks that will handle image uploads from the users and image processing. The first ECS task will process the user requests, store the image in an S3 input bucket, and push a message to a queue. The second task reads from the queue, parses the message containing the object name, and then downloads the object. Once the image is processed and transformed, it will upload the objects to the S3 output bucket. To complete the architecture, the Solutions Architect must create a queue and the necessary IAM permissions for the ECS tasks.

Which of the following should the Architect do next?
+ Launch a new Amazon SQS queue and configure the second ECS task to read from it. Create an IAM role that the ECS tasks can assume in order to get access to the S3 buckets and SQS queue. Declare the IAM Role (`taskRoleArn`) in the task definition.
+ Launch a new Amazon AppStream 2.0 queue and configure the second ECS task to read from it. Create an IAM role that the ECS tasks can assume in order to get access to the S3 buckets and AppStream 2.0 queue. Declare the IAM Role (`taskRoleArn`) in the task definition.
+ Launch a new Amazon Kinesis Data Firehose and configure the second ECS task to read from it. Create an IAM role that the ECS tasks can assume in order to get access to the S3 buckets and Kinesis Data Firehose. Specify the ARN of the IAM Role in the (`taskDefinitionArn`) field of the task definition.
+ Launch a new Amazon MQ queue and configure the second ECS task to read from it. Create an IAM role that the ECS tasks can assume in order to get access to the S3 buckets and Amazon MQ queue. Set the (`EnableTaskIAMRole`) option to true in the task definition.

<details close>
<summary>Answer</summary>
a
</details>

---

A company is running a dashboard application on a Spot EC2 instance inside a private subnet. The dashboard is reachable via a domain name that maps to the private IPv4 address of the instance’s network interface. A solutions architect needs to increase network availability by allowing the traffic flow to resume in another instance if the primary instance is terminated.

Which solution accomplishes these requirements?
+ Create a secondary elastic network interface and point its private IPv4 address to the application’s domain name. Attach the new network interface to the primary instance. If the instance goes down, move the secondary network interface to another instance.
+ Attach an elastic IP address to the instance’s primary network interface and point its IP address to the application’s domain name. Automatically move the EIP to a secondary instance if the primary instance becomes unavailable using the AWS Transit Gateway.
+ Use the AWS Network Firewall to detach the instance’s primary elastic network interface and move it to a new instance upon failure.
+ Set up AWS Transfer for FTPS service in Implicit FTPS mode to automatically disable the `source/destination` checks on the instance’s primary elastic network interface and reassociate it to another instance.

<details close>
<summary>Answer</summary>
a
</details>

---

A company has an application that continually sends encrypted documents to Amazon S3. The company requires that the configuration for data access is in line with their strict compliance standards. They should also be alerted if there is any risk of unauthorized access or suspicious access patterns.

Which step is needed to meet the requirements?
+ Use Amazon GuardDuty to monitor malicious activity on S3.
+ Use Amazon Macie to monitor and detect access patterns on S3.
+ Use Amazon Rekognition to monitor and recognize patterns on S3.
+ Use Amazon Inspector to alert whenever a security violation is detected on S3.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>

Macie cannot detect usage patterns on S3 data. While Amazon Macie is capable of detecting policy changes in S3 buckets, this is not enough to detect unauthorized or suspicious access patterns

Inspector is basically an automated security assessment service that helps improve the security and compliance of applications deployed on AWS.

</details>

---

A digital media company shares static content to its premium users around the world and also to their partners who syndicate their media files. The company is looking for ways to reduce its server costs and securely deliver their data to their customers globally with low latency.

Which combination of services should be used to provide the MOST suitable and cost-effective architecture? (Select TWO.)
+ Amazon CloudFront
+ AWS Fargate
+ AWS Lambda
+ Amazon S3
+ AWS Global Accelerator

<details close>
<summary>Answer</summary>
a,d
</details>

<details close>
<summary>Note</summary>

AWS Global Accelerator is incorrect because this service is more suitable for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice over IP, as well as for HTTP use cases that specifically require static IP addresses or deterministic, fast regional failover. Moreover, there is no direct way that you can integrate AWS Global Accelerator with Amazon S3. It's more suitable to use Amazon CloudFront instead in this scenario.

</details>

---

A company launched a website that accepts high-quality photos and turns them into a downloadable video montage. The website offers a free and a premium account that guarantees faster processing. All requests by both free and premium members go through a single SQS queue and then processed by a group of EC2 instances that generate the videos. The company needs to ensure that the premium users who paid for the service have higher priority than the free members.

How should the company re-design its architecture to address this requirement?
+ For the requests made by premium members, set a higher priority in the SQS queue so it will be processed first compared to the requests made by free members.
+ Create an SQS queue for free members and another one for premium members. Configure your EC2 instances to consume messages from the premium queue first and if it is empty, poll from the free members' SQS queue.
+ Use Amazon Kinesis to process the photos and generate the video montage in real-time.
+ Use Amazon S3 to store and process the photos and then generate the video montage afterward.

<details close>
<summary>Answer</summary>
b
</details>

---

A solutions architect is designing a cost-efficient, highly available storage solution for company data. One of the requirements is to ensure that the previous state of a file is preserved and retrievable if a modified version of it is uploaded. Also, to meet regulatory compliance, data over 3 years must be retained in an archive and will only be accessible once a year.

How should the solutions architect build the solution?

+ Create an S3 Standard bucket with object-level versioning enabled and configure a lifecycle rule that transfers files to Amazon S3 Glacier Deep Archive after 3 years.
+ Create an S3 Standard bucket and enable S3 Object Lock in governance mode.
+ Create an S3 Standard bucket with S3 Object Lock in compliance mode enabled then configure a lifecycle rule that transfers files to Amazon S3 Glacier Deep Archive after 3 years.
+ Create a One-Zone-IA bucket with object-level versioning enabled and configure a lifecycle rule that transfers files to Amazon S3 Glacier Deep Archive after 3 years.

<details close>
<summary>Answer</summary>
a
</details>

---

A GraphQL API hosted is hosted in an Amazon EKS cluster with Fargate launch type and deployed using AWS SAM. The API is connected to an Amazon DynamoDB table with an Amazon DynamoDB Accelerator (DAX) as its data store. Both resources are hosted in the us-east-1 region.

The AWS IAM authenticator for Kubernetes is integrated into the EKS cluster for role-based access control (RBAC) and cluster authentication. A solutions architect must improve network security by preventing database calls from traversing the public internet. An automated cross-account backup for the DynamoDB table is also required for long-term retention.

Which of the following should the solutions architect implement to meet the requirement?
+ Create a DynamoDB gateway endpoint. Associate the endpoint to the appropriate route table. Use AWS Backup to automatically copy the on-demand DynamoDB backups to another AWS account for disaster recovery.
+ Create a DynamoDB interface endpoint. Associate the endpoint to the appropriate route table. Enable Point-in-Time Recovery (PITR) to restore the DynamoDB table to a particular point in time on the same or a different AWS account.
+ Create a DynamoDB gateway endpoint. Set up a Network Access Control List (NACL) rule that allows outbound traffic to the `dynamodb.us-east-1.amazonaws.com`  gateway endpoint. Use the built-in on-demand DynamoDB backups for cross-account backup and recovery.
+ Create a DynamoDB interface endpoint. Set up a stateless rule using AWS Network Firewall to control all outbound traffic to only use the  `dynamodb.us-east-1.amazonaws.com` endpoint. Integrate the DynamoDB table with Amazon Timestream to allow point-in-time recovery from a different AWS account.

<details close>
<summary>Answer</summary>
a
</details>

---

A company has two On-Demand EC2 instances inside the Virtual Private Cloud in the same Availability Zone but are deployed to different subnets. One EC2 instance is running a database and the other EC2 instance a web application that connects with the database. You need to ensure that these two instances can communicate with each other for the system to work properly.

What are the things you have to check so that these EC2 instances can communicate inside the VPC? (Select TWO.)
+ Check the Network ACL if it allows communication between the two subnets.
+ Check if both instances are the same instance class.
+ Check if the default route is set to a NAT instance or Internet Gateway (IGW) for them to communicate.
+ Check if all security groups are set to allow the application host to communicate to the database on the right port and protocol.
+ Ensure that the EC2 instances are in the same Placement Group.

<details close>
<summary>Answer</summary>
a,d
</details>

---

A company developed a web application and deployed it on a fleet of EC2 instances that uses Amazon SQS. The requests are saved as messages in the SQS queue, which is configured with the maximum message retention period. However, after thirteen days of operation, the web application suddenly crashed and there are 10,000 unprocessed messages that are still waiting in the queue. Since they developed the application, they can easily resolve the issue but they need to send a communication to the users on the issue.

What information should they provide and what will happen to the unprocessed messages?
+ Tell the users that unfortunately, they have to resubmit all the requests again.
+ Tell the users that the application will be operational shortly however, requests sent over three days ago will need to be resubmitted.
+ Tell the users that the application will be operational shortly and all received requests will be processed after the web application is restarted.
+ Tell the users that unfortunately, they have to resubmit all of the requests since the queue would not be able to process the 10,000 messages together.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
A single Amazon SQS message queue can contain an unlimited number of messages. However, there is a 120,000 limit for the number of inflight messages for a standard queue and 20,000 for a FIFO queue. Messages are inflight after they have been received from the queue by a consuming component, but have not yet been deleted from the queue.
</details>

---

A media company hosts large volumes of archive data that are about 250 TB in size on their internal servers. They have decided to move these data to S3 because of its durability and redundancy. The company currently has a 100 Mbps dedicated line connecting their head office to the Internet.

Which of the following is the FASTEST and the MOST cost-effective way to import all these data to Amazon S3?

+ Upload it directly to S3
+ Establish an AWS Direct Connect connection then transfer the data over to S3.
+ Use AWS Snowmobile to transfer the data over to S3.
+ Order multiple AWS Snowball devices to upload the files to Amazon S3.

<details close>
<summary>Answer</summary>
d
</details>

---

A company plans to migrate all of their applications to AWS. The Solutions Architect suggested to store all the data to EBS volumes. The Chief Technical Officer is worried that EBS volumes are not appropriate for the existing workloads due to compliance requirements, downtime scenarios, and IOPS performance.

Which of the following are valid points in proving that EBS is the best service to use for migration? (Select TWO.)
+ When you create an EBS volume in an Availability Zone, it is automatically replicated on a separate AWS region to prevent data loss due to a failure of any single hardware component.
+ EBS volumes can be attached to any EC2 Instance in any Availability Zone.
+ An EBS volume is off-instance storage that can persist independently from the life of an instance.
+ EBS volumes support live configuration changes while in production which means that you can modify the volume type, volume size, and IOPS capacity without service interruptions.
+ Amazon EBS provides the ability to create snapshots (backups) of any EBS volume and write a copy of the data in the volume to Amazon RDS, where it is stored redundantly in multiple Availability Zones 


<details close>
<summary>Answer</summary>
c,d
</details>

---

A company has a top priority requirement to monitor a few database metrics and then afterward, send email notifications to the Operations team in case there is an issue. Which AWS services can accomplish this requirement? (Select TWO.)

+ Amazon Simple Email Service
+ Amazon CloudWatch
+ Amazon Simple Queue Service (SQS)
+ Amazon EC2 Instance with a running Berkeley Internet Name Domain (BIND) Server.
+ Amazon Simple Notification Service (SNS)

<details close>
<summary>Answer</summary>
b,e
</details>

---

A Solutions Architect of a multinational gaming company develops video games for PS4, Xbox One, and Nintendo Switch consoles, plus a number of mobile games for Android and iOS. Due to the wide range of their products and services, the architect proposed that they use API Gateway.

What are the key features of API Gateway that the architect can tell to the client? (Select TWO.)
+ It automatically provides a query language for your APIs similar to GraphQL.
+ Provides you with static anycast IP addresses that serve as a fixed entry point to your applications hosted in one or more AWS Regions.
+ Enables you to build RESTful APIs and WebSocket APIs that are optimized for serverless workloads.
+ Enables you to run applications requiring high levels of inter-node communications at scale on AWS through its custom-built operating system (OS) bypass hardware interface.
+ You pay only for the API calls you receive and the amount of data transferred out.
<details close>
<summary>Answer</summary>
c,e
</details>

---

A technology company has a suite of container-based web applications and serverless solutions that are hosted in AWS. The Solutions Architect must define a standard infrastructure that will be used across development teams and applications. There are application-specific resources too that change frequently, especially during the early stages of application development. Developers must be able to add supplemental resources to their applications, which are beyond what the architects predefined in the system environments and service templates.

Which of the following should be implemented to satisfy this requirement?
+ Set up AWS Proton for deploying container applications and serverless solutions. Create components from the AWS Proton console and attach them to their respective service instance.
+ Use the Amazon EKS Anywhere service for deploying container applications and serverless solutions. Create a service instance for each application-specific resource.
+ Set up AWS Control Tower to automate container-based application deployments. Use AWS Config for application-specific resources that change frequently.
+ Use the Amazon Elastic Container Service (ECS) Anywhere service for deploying container applications and serverless solutions. Configure Prometheus metrics collection on the ECS cluster and use Amazon Managed Service for Prometheus for monitoring frequently-changing resources

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
AWS Proton allows you to deploy any serverless or container-based application with increased efficiency, consistency, and control. You can define infrastructure standards and effective continuous delivery pipelines for your organization. Proton breaks down the infrastructure into environment and service (“infrastructure as code” templates).
</details>

---

A company has a static corporate website hosted in a standard S3 bucket and a new web domain name that was registered using Route 53. You are instructed by your manager to integrate these two services in order to successfully launch their corporate website.

What are the prerequisites when routing traffic using Amazon Route 53 to a website that is hosted in an Amazon S3 Bucket? (Select TWO.)
+ The S3 bucket name must be the same as the domain name
+ A registered domain name
+ The record set must be of type "MX"
+ The S3 bucket must be in the same region as the hosted zone
+ The Cross-Origin Resource Sharing (CORS) option should be enabled in the S3 bucket

<details close>
<summary>Answer</summary>
a,b
</details>

---

A software company has resources hosted in AWS and on-premises servers. You have been requested to create a decoupled architecture for applications which make use of both resources.

Which of the following options are valid? (Select TWO.)

+ Use SWF to utilize both on-premises servers and EC2 instances for your decoupled application
+ Use RDS to utilize both on-premises servers and EC2 instances for your decoupled application
+ Use SQS to utilize both on-premises servers and EC2 instances for your decoupled application
+ Use VPC peering to connect both on-premises servers and EC2 instances for your decoupled application
+ Use DynamoDB to utilize both on-premises servers and EC2 instances for your decoupled application

<details close>
<summary>Answer</summary>
a,c
</details>

Amazon SWF is a web service that makes it easy to coordinate work across distributed application components.

---

A company owns a photo-sharing app that stores user uploads on Amazon S3. There has been an increase in the number of explicit and offensive images being reported. The company currently relies on human efforts to moderate content, and they want to streamline this process by using Artificial Intelligence to only flag images for review. For added security, any communication with your resources on your Amazon VPC must not traverse the public Internet.

How can this task be accomplished with the LEAST amount of effort?

+ Use Amazon Rekognition to detect images with graphic nudity or violence in Amazon S3. Create an Interface VPC endpoint for Amazon Rekognition with the necessary policies to prevent any traffic from traversing the public Internet.
+ Use an image classification model in Amazon SageMaker. Set up Amazon GuardDuty and connect it with Amazon SageMaker to ensure that all communications do not traverse the public Internet.
+ Use Amazon Detective to detect images with graphic nudity or violence in Amazon S3. Ensure that all communications made by your AWS resources do not traverse the public Internet via the AWS Audit Manager service.
+ Use Amazon Monitron to monitor each user upload in S3. Use the AWS Transit Gateway Network Manager to block any outbound requests to the public Internet.

<details close>
<summary>Answer</summary>
a
</details>

---

A startup has multiple AWS accounts that are assigned to its development teams. Since the company is projected to grow rapidly, the management wants to consolidate all of its AWS accounts into a multi-account setup. To simplify the login process on the AWS accounts, the management wants to utilize its existing directory service for user authentication

Which combination of actions should a solutions architect recommend to meet these requirements? (Select TWO.)
+ On the master account, use AWS Organizations to create a new organization with all features turned on. Enable the organization’s external authentication and point it to use the company’s directory service.
+ Create an identity pool on Amazon Cognito and configure it to use the company’s directory service. Configure AWS IAM Identity Center (AWS Single Sign-On) to accept Cognito authentication.
+ Create Service Control Policies (SCP) in the organization to manage the child accounts. Configure AWS IAM Identity Center (AWS Single Sign-On) to use AWS Directory Service.
+ On the master account, use AWS Organizations to create a new organization with all features turned on. Invite the child accounts to this new organization.
+ Configure AWS IAM Identity Center (AWS Single Sign-On) for the organization and integrate it with the company’s directory service using the Active Directory Connector

<details close>
<summary>Answer</summary>
d,e
</details>


<details close>
<summary>Note</summary>
SCPs are not necessarily needed for logging in on this scenario. You can use SCP if you want to restrict or implement a policy across several accounts in the organization.
</details>

---

A company has a dynamic web app written in MEAN stack that is going to be launched in the next month. There is a probability that the traffic will be quite high in the first couple of weeks. In the event of a load failure, how can you set up DNS failover to a static website?
+ Duplicate the exact application architecture in another region and configure DNS weight-based routing.
+ Enable failover to an application hosted in an on-premises data center.
+ Use Route 53 with the failover option to a static S3 website bucket or CloudFront distribution.
+ Add more servers in case the application fails.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has a requirement to move 80 TB data warehouse to the cloud. It would take 2 months to transfer the data given their current bandwidth allocation.

Which is the most cost-effective service that would allow you to quickly upload their data into AWS?
+ AWS Snowmobile
+ AWS Snowball Edge
+ AWS Direct Connect
+ Amazon S3 Multipart Upload

<details close>
<summary>Answer</summary>
b
</details>

---

An Intelligence Agency developed a missile tracking application that is hosted on both development and production AWS accounts. The Intelligence agency’s junior developer only has access to the development account. She has received security clearance to access the agency’s production account but the access is only temporary and only write access to EC2 and S3 is allowed.

Which of the following allows you to issue short-lived access tokens that act as temporary security credentials to allow access to your AWS resources?
+ Use AWS Cognito to issue JSON Web Tokens (JWT)
+ Use AWS STS
+ Use AWS SSO
+ All of the given options are correct.

<details close>
<summary>Answer</summary>
b
</details>

---

As part of the Business Continuity Plan of your company, your IT Director instructed you to set up an automated backup of all of the EBS Volumes for your EC2 instances as soon as possible. 

What is the fastest and most cost-effective solution to automatically back up all of your EBS Volumes?

+ For an automated solution, create a scheduled job that calls the "create-snapshot" command via the AWS CLI to take a snapshot of production EBS volumes periodically.  
+ Set your Amazon Storage Gateway with EBS volumes as the data source and store the backups in your on-premises servers through the storage gateway.
+ Use an EBS-cycle policy in Amazon S3 to automatically back up the EBS volumes.
+ Use Amazon Data Lifecycle Manager (Amazon DLM) to automate the creation of EBS snapshots.
<details close>
<summary>Answer</summary>
d
</details>


<details close>
<summary>Note</summary>
You can use Amazon Data Lifecycle Manager (Amazon DLM) to automate the creation, retention, and deletion of snapshots taken to back up your Amazon EBS volumes. Automating snapshot management helps you to:

- Protect valuable data by enforcing a regular backup schedule.

- Retain backups as required by auditors or internal compliance.

- Reduce storage costs by deleting outdated backups.


</details>

---

A commercial bank has a forex trading application. They created an Auto Scaling group of EC2 instances that allow the bank to cope with the current traffic and achieve cost-efficiency. They want the Auto Scaling group to behave in such a way that it will follow a predefined set of parameters before it scales down the number of EC2 instances, which protects the system from unintended slowdown or unavailability.

Which of the following statements are true regarding the cooldown period? (Select TWO.)
+ It ensures that before the Auto Scaling group scales out, the EC2 instances have ample time to cooldown.
+ It ensures that the Auto Scaling group launches or terminates additional EC2 instances without any downtime.
+ It ensures that the Auto Scaling group does not launch or terminate additional EC2 instances before the previous scaling activity takes effect.
+ Its default value is 300 seconds.
+ Its default value is 600 seconds.

<details close>
<summary>Answer</summary>
c,d
</details>

---

An application is hosted in AWS Fargate and uses RDS database in Multi-AZ Deployments configuration with several Read Replicas. A Solutions Architect was instructed to ensure that all of their database credentials, API keys, and other secrets are encrypted and rotated on a regular basis to improve data security. The application should also use the latest version of the encrypted credentials when connecting to the RDS database.

Which of the following is the MOST appropriate solution to secure the credentials?
+ Store the database credentials, API keys, and other secrets to Systems Manager Parameter Store each with a `SecureString` data type. The credentials are automatically rotated by default.
+ Use AWS Secrets Manager to store and encrypt the database credentials, API keys, and other secrets. Enable automatic rotation for all of the credentials.
+ Store the database credentials, API keys, and other secrets to AWS ACM.
+ Store the database credentials, API keys, and other secrets in AWS KMS.

<details close>
<summary>Answer</summary>
b
</details>

---

An insurance company utilizes SAP HANA for its day-to-day ERP operations. Since they can’t migrate this database due to customer preferences, they need to integrate it with the current AWS workload in the VPC in which they are required to establish a site-to-site VPN connection.

What needs to be configured outside of the VPC for them to have a successful site-to-site VPN connection?

+ A dedicated NAT instance in a public subnet
+ An Internet-routable IP address (static) of the customer gateway's external interface for the on-premises network
+ The main route table in your VPC to route traffic through a NAT instance
+ An EIP to the Virtual Private Gateway

<details close>
<summary>Answer</summary>
b
</details>

---

A company is running a multi-tier web application farm in a virtual private cloud (VPC) that is not connected to their corporate network. They are connecting to the VPC over the Internet to manage the fleet of Amazon EC2 instances running in both the public and private subnets. The Solutions Architect has added a bastion host with Microsoft Remote Desktop Protocol (RDP) access to the application instance security groups, but the company wants to further limit administrative access to all of the instances in the VPC.

Which of the following bastion host deployment options will meet this requirement?
+ Deploy a Windows Bastion host on the corporate network that has RDP access to all EC2 instances in the VPC.
+ Deploy a Windows Bastion host with an Elastic IP address in the private subnet, and restrict RDP access to the bastion from only the corporate public IP addresses.
+ Deploy a Windows Bastion host with an Elastic IP address in the public subnet and allow SSH access to the bastion from anywhere.
+ Deploy a Windows Bastion host with an Elastic IP address in the public subnet and allow RDP access to bastion only from the corporate IP addresses.

<details close>
<summary>Answer</summary>
d
</details>

---

For data privacy, a healthcare company has been asked to comply with the Health Insurance Portability and Accountability Act (HIPAA). The company stores all its backups on an Amazon S3 bucket. It is required that data stored on the S3 bucket must be encrypted.

What is the best option to do this? (Select TWO.)

+ Before sending the data to Amazon S3 over HTTPS, encrypt the data locally first using your own encryption keys.
+ Store the data on EBS volumes with encryption enabled instead of using Amazon S3.
+ Store the data in encrypted EBS snapshots.
+ Enable Server-Side Encryption on an S3 bucket to make use of AES-256 encryption.
+ Enable Server-Side Encryption on an S3 bucket to make use of AES-128 encryption.

<details close>
<summary>Answer</summary>
a,d
</details>

---

A Solutions Architect is working for an online hotel booking firm with terabytes of customer data coming from the websites and applications. There is an annual corporate meeting where the Architect needs to present the booking behavior and acquire new insights from the customers’ data. The Architect is looking for a service to perform super-fast analytics on massive data sets in near real-time.

Which of the following services gives the Architect the ability to store huge amounts of data and perform quick and flexible queries on it?
+ Amazon DynamoDB
+ Amazon ElastiCache
+ Amazon RDS
+ Amazon Redshift

<details close>
<summary>Answer</summary>
d
</details>

---

A start-up company has an EC2 instance that is hosting a web application. The volume of users is expected to grow in the coming months, and hence, you need to add more elasticity and scalability in your AWS architecture to cope with the demand.

Which of the following options can satisfy the above requirement for the given scenario? (Select TWO.)

+ Set up two EC2 instances and then put them behind an Elastic Load balancer (ELB).
+ Set up an S3 Cache in front of the EC2 instance.
+ Set up two EC2 instances and use Route 53 to route traffic based on a Weighted Routing Policy.
+ Set up an AWS WAF behind your EC2 Instance.
+ Set up two EC2 instances deployed using Launch Templates and integrated with AWS Glue. 

<details close>
<summary>Answer</summary>
a,c
</details>

---

An accounting application uses an RDS database configured with Multi-AZ deployments to improve availability. What would happen to RDS if the primary database instance fails?
+ The IP address of the primary DB instance is switched to the standby DB instance.
+ The primary database instance will reboot.
+ A new database instance is created in the standby Availability Zone.
+ The canonical name record (CNAME) is switched from the primary to standby instance.

<details close>
<summary>Answer</summary>
d
</details>

---

A company plans to conduct a network security audit. The web application is hosted on an Auto Scaling group of EC2 Instances with an Application Load Balancer in front to evenly distribute the incoming traffic. A Solutions Architect has been tasked to enhance the security posture of the company’s cloud infrastructure and minimize the impact of DDoS attacks on its resources.

Which of the following is the most effective solution that should be implemented?
+ Configure Amazon CloudFront distribution and set Application Load Balancer as the origin. Create a rate-based web ACL rule using AWS WAF and associate it with Amazon CloudFront.
+ Configure Amazon CloudFront distribution and set a Network Load Balancer as the origin. Use VPC Flow Logs to monitor abnormal traffic patterns. Set up a custom AWS Lambda function that processes the flow logs and invokes Amazon SNS for notification.
+ Configure Amazon CloudFront distribution and set an Application Load Balancer as the origin. Create a security group rule and deny all the suspicious addresses. Use Amazon SNS for notification.
+ Configure Amazon CloudFront distribution and set a Network Load Balancer as the origin. Use Amazon GuardDuty to block suspicious hosts based on its security findings. Set up a custom AWS Lambda function that processes the security logs and invokes Amazon SNS for notification.

<details close>
<summary>Answer</summary>
a
</details>

---

A DevOps Engineer is required to design a cloud architecture in AWS. The Engineer is planning to develop a highly available and fault-tolerant architecture consisting of an Elastic Load Balancer and an Auto Scaling group of EC2 instances deployed across multiple Availability Zones. This will be used by an online accounting application that requires path-based routing, host-based routing, and bi-directional streaming using Remote Procedure Call (gRPC).

Which configuration will satisfy the given requirement?
+ Configure an Application Load Balancer in front of the auto-scaling group. Select gRPC as the protocol version.
+ Configure a Network Load Balancer in front of the auto-scaling group. Use a UDP listener for routing.
+ Configure a Gateway Load Balancer in front of the auto-scaling group. Ensure that the IP Listener Routing uses the GENEVE protocol on port 6081 to allow gRPC response traffic.
+ Configure a Network Load Balancer in front of the auto-scaling group. Create an AWS Global Accelerator accelerator and set the load balancer as an endpoint.

<details close>
<summary>Answer</summary>
a
</details>

---

A start-up company that offers an intuitive financial data analytics service has consulted you about their AWS architecture. They have a fleet of Amazon EC2 worker instances that process financial data and then outputs reports which are used by their clients. You must store the generated report files in a durable storage. The number of files to be stored can grow over time as the start-up company is expanding rapidly overseas and hence, they also need a way to distribute the reports faster to clients located across the globe. 

Which of the following is a cost-efficient and scalable storage option that you should use for this scenario?
+ Use Amazon Redshift as the data storage and CloudFront as the CDN.
+ Use Amazon Glacier as the data storage and ElastiCache as the CDN.
+ Use Amazon S3 as the data storage and CloudFront as the CDN.
+ Use multiple EC2 instance stores for data storage and ElastiCache as the CDN.

<details close>
<summary>Answer</summary>
c
</details>

---

An advertising company is currently working on a proof of concept project that automatically provides SEO analytics for its clients. Your company has a VPC in AWS that operates in a dual-stack mode in which IPv4 and IPv6 communication is allowed. You deployed the application to an Auto Scaling group of EC2 instances with an Application Load Balancer in front that evenly distributes the incoming traffic. You are ready to go live but you need to point your domain name (tutorialsdojo.com) to the Application Load Balancer.

In Route 53, which record types will you use to point the DNS name of the Application Load Balancer? (Select TWO.)
+ Non-Alias with a type "A" record set
+ Alias with a type "AAAA" record set
+ Alias with a type "CNAME" record set
+ Alias with a type "A" record set
+ Alias with a type of “MX” record set

<details close>
<summary>Answer</summary>
b,d
</details>

<details close>
<summary>Note</summary>
AAAA -> IPv6
Non-Alias with a type “A” record set for IP addresses.
</details>

---
A company is building an internal application that serves as a repository for images uploaded by a couple of users. Whenever a user uploads an image, it would be sent to Kinesis Data Streams for processing before it is stored in an S3 bucket. If the upload was successful, the application will return a prompt informing the user that the operation was successful. The entire processing typically takes about 5 minutes to finish.

Which of the following options will allow you to asynchronously process the request to the application from upload request to Kinesis, S3, and return a reply in the most cost-effective manner?

+ Use a combination of Lambda and Step Functions to orchestrate service components and asynchronously process the requests.
+ Use a combination of SQS to queue the requests and then asynchronously process them using On-Demand EC2 Instances.
+ Replace the Kinesis Data Streams with an Amazon SQS queue. Create a Lambda function that will asynchronously process the requests.
+ Use a combination of SNS to buffer the requests and then asynchronously process them using On-Demand EC2 Instances.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has a cryptocurrency exchange portal that is hosted in an Auto Scaling group of EC2 instances behind an Application Load Balancer and is deployed across multiple AWS regions. The users can be found all around the globe, but the majority are from Japan and Sweden. Because of the compliance requirements in these two locations, you want the Japanese users to connect to the servers in the `ap-northeast-1` Asia Pacific (Tokyo) region, while the Swedish users should be connected to the servers in the `eu-west-1` EU (Ireland) region.

Which of the following services would allow you to easily fulfill this requirement?

+ Use Route 53 Geolocation Routing policy.
+ Set up an Application Load Balancers that will automatically route the traffic to the proper AWS region.
+ Set up a new CloudFront web distribution with the geo-restriction feature enabled.
+ Use Route 53 Weighted Routing policy.

<details close>
<summary>Answer</summary>
a
</details>

---

A company is hosting its web application in an Auto Scaling group of EC2 instances behind an Application Load Balancer. Recently, the Solutions Architect identified a series of SQL injection attempts and cross-site scripting attacks to the application, which had adversely affected their production data.

Which of the following should the Architect implement to mitigate this kind of attack?
+ Use Amazon Guard​Duty to prevent any further SQL injection and cross-site scripting attacks in your application.
+ Using AWS Firewall Manager, set up security rules that block SQL injection and cross-site scripting attacks. Associate the rules to the Application Load Balancer.
+ Block all the IP addresses where the SQL injection and cross-site scripting attacks originated using the Network Access Control List.
+ Set up security rules that block SQL injection and cross-site scripting attacks in AWS Web Application Firewall (WAF). Associate the rules to the Application Load Balancer.

<details close>
<summary>Answer</summary>
d
</details>

---

A solutions architect is instructed to host a website that consists of HTML, CSS, and some Javascript files. The web pages will display several high-resolution images. The website should have optimal loading times and be able to respond to high request rates.

Which of the following architectures can provide the most cost-effective and fastest loading experience?

+ Upload the HTML, CSS, Javascript, and the images in a single bucket. Then enable website hosting. Create a CloudFront distribution and point the domain on the S3 website endpoint.
+ Host the website using an Nginx server in an EC2 instance. Upload the images in an S3 bucket. Use CloudFront as a CDN to deliver the images closer to end-users.
+ Launch an Auto Scaling Group using an AMI that has a pre-configured Apache web server, then configure the scaling policy accordingly. Store the images in an Elastic Block Store. Then, point your instance’s endpoint to AWS Global Accelerator.
+ Host the website in an AWS Elastic Beanstalk environment. Upload the images in an S3 bucket. Use CloudFront as a CDN to deliver the images closer to your end-users.

<details close>
<summary>Answer</summary>
a
</details>

---

Both historical records and frequently accessed data are stored on an on-premises storage system. The amount of current data is growing at an exponential rate. As the storage’s capacity is nearing its limit, the company’s Solutions Architect has decided to move the historical records to AWS to free up space for the active data.

Which of the following architectures deliver the best solution in terms of cost and operational management?
+ Use AWS DataSync to move the historical records from on-premises to AWS. Choose Amazon S3 Glacier Deep Archive to be the destination for the data.
+ Use AWS Storage Gateway to move the historical records from on-premises to AWS. Choose Amazon S3 Glacier Deep Archive to be the destination for the data.
+ Use AWS DataSync to move the historical records from on-premises to AWS. Choose Amazon S3 Standard to be the destination for the data. Modify the S3 lifecycle configuration to move the data from the Standard tier to Amazon S3 Glacier Deep Archive after 30 days.
+ Use AWS Storage Gateway to move the historical records from on-premises to AWS. Choose Amazon S3 Glacier to be the destination for the data. Modify the S3 lifecycle configuration to move the data from the Standard tier to Amazon S3 Glacier Deep Archive after 30 days.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
AWS DataSync makes it simple and fast to move large amounts of data online between on-premises storage and Amazon S3, Amazon Elastic File System (Amazon EFS), or Amazon FSx for Windows File Server. Manual tasks related to data transfers can slow down migrations and burden IT operations. DataSync eliminates or automatically handles many of these tasks, including scripting copy jobs, scheduling, and monitoring transfers, validating data, and optimizing network utilization. The DataSync software agent connects to your Network File System (NFS), Server Message Block (SMB) storage, and your self-managed object storage, so you don’t have to modify your applications.

DataSync can transfer hundreds of terabytes and millions of files at speeds up to 10 times faster than open-source tools, over the Internet or AWS Direct Connect links. You can use DataSync to migrate active data sets or archives to AWS, transfer data to the cloud for timely analysis and processing, or replicate data to AWS for business continuity. Getting started with DataSync is easy: deploy the DataSync agent, connect it to your file system, select your AWS storage resources, and start moving data between them. You pay only for the data you move.
</details>

---

All objects uploaded to an Amazon S3 bucket must be encrypted for security compliance. The bucket will use server-side encryption with Amazon S3-Managed encryption keys (SSE-S3) to encrypt data using 256-bit Advanced Encryption Standard (AES-256) block cipher.

Which of the following request headers must be used?
+ `x-amz-server-side-encryption-customer-key`
+ `x-amz-server-side-encryption-customer-algorithm`
+ `x-amz-server-side-encryption-customer-key-MD5`
+ `x-amz-server-side-encryption`

<details close>
<summary>Answer</summary>
d
</details>

---

A company runs a messaging application in the `ap-northeast-1` and `ap-southeast-2` region. A Solutions Architect needs to create a routing policy wherein a larger portion of traffic from the Philippines and North India will be routed to the resource in the `ap-northeast-1` region.

Which Route 53 routing policy should the Solutions Architect use?
+ Geoproximity Routing
+ Geolocation Routing
+ Latency Routing
+ Weighted Routing

<details close>
<summary>Answer</summary>
a
</details>

---

An organization stores and manages financial records of various companies in its on-premises data center, which is almost out of space. The management decided to move all of their existing records to a cloud storage service. All future financial records will also be stored in the cloud. For additional security, all records must be prevented from being deleted or overwritten.

Which of the following should you do to meet the above requirement?
+ Use AWS Storage Gateway to establish hybrid cloud storage. Store all of your data in Amazon S3 and enable object lock.
+ Use AWS DataSync to move the data. Store all of your data in Amazon S3 and enable object lock.
+ Use AWS DataSync to move the data. Store all of your data in Amazon EFS and enable object lock.
+ Use AWS Storage Gateway to establish hybrid cloud storage. Store all of your data in Amazon EBS and enable object lock.

<details close>
<summary>Answer</summary>
b
</details>

---

An organization is currently using a tape backup solution to store its application data on-premises. They plan to use a cloud storage service to preserve the backup data for up to 10 years that may be accessed about once or twice a year.

Which of the following is the most cost-effective option to implement this solution?
+ Use AWS Storage Gateway to backup the data directly to Amazon S3 Glacier.
+ Order an AWS Snowball Edge appliance to import the backup directly to Amazon S3 Glacier.
+ Use AWS Storage Gateway to backup the data directly to Amazon S3 Glacier Deep Archive.
+ Use Amazon S3 to store the backup data and add a lifecycle rule to transition the current version to Amazon S3 Glacier.

<details close>
<summary>Answer</summary>
c
</details>

---

An insurance company plans to implement a message filtering feature in their web application. To implement this solution, they need to create separate Amazon SQS queues for each type of quote request. The entire message processing should not exceed 24 hours.

As the Solutions Architect of the company, which of the following should you do to meet the above requirement?
+ Create one Amazon SNS topic and configure the Amazon SQS queues to subscribe to the SNS topic. Set the filter policies in the SNS subscriptions to publish the message to the designated SQS queue based on its quote request type.
+ Create one Amazon SNS topic and configure the Amazon SQS queues to subscribe to the SNS topic. Publish the same messages to all SQS queues. Filter the messages in each queue based on the quote request type.
+ Create multiple Amazon SNS topics and configure the Amazon SQS queues to subscribe to the SNS topics. Publish the message to the designated SQS queue based on the quote request type.
+ Create a data stream in Amazon Kinesis Data Streams. Use the Amazon Kinesis Client Library to deliver all the records to the designated SQS queues based on the quote request type.

<details close>
<summary>Answer</summary>
a
</details>

---

An organization needs to control the access for several S3 buckets. They plan to use a gateway endpoint to allow access to trusted buckets.

Which of the following could help you achieve this requirement?
+ Associate an Elastic IP address to a Network Load Balancer.
+ Create a CloudFront distribution whose origin points to the private IP addresses of your web servers.
+ Associate an Elastic IP address to an Application Load Balancer.
+ Create an Alias Record in Route 53 which maps to the DNS name of the load balancer.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
Based on the given scenario, web service clients can only access trusted IP addresses. To resolve this requirement, you can use the Bring Your Own IP (BYOIP) feature to use the trusted IPs as Elastic IP addresses (EIP) to a Network Load Balancer (NLB). This way, there's no need to re-establish the whitelists with new IP addresses.
</details>

---

A company is running a custom application in an Auto Scaling group of Amazon EC2 instances. Several instances are failing due to insufficient swap space. The Solutions Architect has been instructed to troubleshoot the issue and effectively monitor the available swap space of each EC2 instance.

Which of the following options fulfills this requirement?

+ Enable detailed monitoring on each instance and monitor the `SwapUtilization` metric.
+ Create a new trail in AWS CloudTrail and configure Amazon CloudWatch Logs to monitor your trail logs.
+ Install the CloudWatch agent on each instance and monitor the `SwapUtilization` metric.
+ Create a CloudWatch dashboard and monitor the `SwapUsed` metric.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has multiple VPCs with IPv6 enabled for its suite of web applications. The Solutions Architect tried to deploy a new Amazon EC2 instance but she received an error saying that there is no IP address available on the subnet.

How should the Solutions Architect resolve this problem?

+ Set up a new IPv4 subnet with a larger CIDR range. Associate the new subnet with the VPC and then launch the instance.
+ Ensure that the VPC has IPv6 CIDRs only. Remove any IPv4 CIDRs associated with the VPC.
+ Set up a new IPv6-only subnet with a large CIDR range. Associate the new subnet with the VPC then launch the instance.
+ Disable the IPv4 support in the VPC and use the available IPv6 addresses.

<details close>
<summary>Answer</summary>
a
</details>

---

A company is receiving semi-structured and structured data from different sources every day. The Solutions Architect plans to use big data processing frameworks to analyze vast amounts of data and access it using various business intelligence tools and standard SQL queries.

Which of the following provides the MOST high-performing solution that fulfills this requirement?
+ Use AWS Glue and store the processed data in Amazon S3.
+ Create an Amazon EMR cluster and store the processed data in Amazon Redshift.
+ Use Amazon Kinesis Data Analytics and store the processed data in Amazon DynamoDB.
+ Create an Amazon EC2 instance and store the processed data in Amazon EBS.

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
Amazon EMR is a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark, on AWS to process and analyze vast amounts of data. By using these frameworks and related open-source projects, such as Apache Hive and Apache Pig, you can process data for analytics purposes and business intelligence workloads. Additionally, you can use Amazon EMR to transform and move large amounts of data into and out of other AWS data stores and databases.

The key phrases in the scenario are "big data processing frameworks" and "various business intelligence tools and standard SQL queries" to analyze the data. To leverage big data processing frameworks, you need to use Amazon EMR. The cluster will perform data transformations (ETL) and load the processed data into Amazon Redshift for analytic and business intelligence applications.
</details>

---

A company wants to organize the way it tracks its spending on AWS resources. A report that summarizes the total billing accrued by each department must be generated at the end of the month.

Which solution will meet the requirements?
+ Tag resources with the department name and enable cost allocation tags.
+ Tag resources with the department name and configure a budget action in AWS Budget.
+ Use AWS Cost Explorer to view spending and filter usage data by `Resource`.
+ Create a Cost and Usage report for AWS services that each department is using.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>

The `Resource` filter just lets you track costs on EC2 instances. This is quite limited compared with using the Cost Allocation Tags method.

A tag is a label that you or AWS assigns to an AWS resource. Each tag consists of a key and a value. For each resource, each tag key must be unique, and each tag key can have only one value. You can use tags to organize your resources and cost allocation tags to track your AWS costs on a detailed level.

</details>

---

A business has a network of surveillance cameras installed within the premises of its data center. Management wants to leverage Artificial Intelligence to monitor and detect unauthorized personnel entering restricted areas. Should an unauthorized person be detected, the security team must be alerted via SMS.

Which solution satisfies the requirement?
+ Use Amazon Kinesis Video to stream live feeds from the cameras. Use Amazon Rekognition to detect authorized personnel. Set the phone numbers of the security as subscribers to an SNS topic.
+ Configure Amazon Elastic Transcoder to stream live feeds from the cameras. Use Amazon Kendra to detect authorized personnel. Set the phone numbers of the security as subscribers to an SNS topic.
+ Replace the existing cameras with AWS IoT. Upload a face detection model to the AWS IoT devices and send them over to AWS Control Tower for checking and notification
+ Set up Amazon Managed Service for Prometheus to stream live feeds from the cameras. Use Amazon Fraud Detector to detect unauthorized personnel. Set the phone numbers of the security as subscribers to an SNS topic.

<details close>
<summary>Answer</summary>
a
</details>

---

A company hosts its web application on a set of Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer (ALB). The application has an embedded NoSQL database. As the application receives more traffic, the application becomes overloaded mainly due to database requests. The management wants to ensure that the database is eventually consistent and highly available.

Which of the following options can meet the company requirements with the least operational overhead?
+ Change the ALB with a Network Load Balancer (NLB) to handle more traffic and integrate AWS Global Accelerator to ensure high availability. Configure replication of the NoSQL database on the set of Amazon EC2 instances to spread the database load.
+ Configure the Auto Scaling group to spread the Amazon EC2 instances across three Availability Zones. Use the AWS Database Migration Service (DMS) with a replication server and an ongoing replication task to migrate the embedded NoSQL database to Amazon DynamoDB
+ Change the ALB with a Network Load Balancer (NLB) to handle more traffic. Use the AWS Migration Service (DMS) to migrate the embedded NoSQL database to Amazon DynamoDB.
+ Configure the Auto Scaling group to spread the Amazon EC2 instances across three Availability Zones. Configure replication of the NoSQL database on the set of Amazon EC2 instances to spread the database load.

<details close>
<summary>Answer</summary>
b
</details>