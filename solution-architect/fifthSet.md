# Solution Architect Exam#5 Practice Set

A financial analytics application that collects, processes and analyzes stock data in real-time is using Kinesis Data Streams. The producers continually push data to Kinesis Data Streams while the consumers process the data in real time. In Amazon Kinesis, where can the consumers store their results? (Select TWO.)

+ Amazon S3
+ Glacier Select
+ Amazon Redshift
+ AWS Glue
+ Amazon Athena


<details close>
<summary>Answer</summary>
a,c
</details>

<br>

---

A company has recently adopted a hybrid cloud architecture and is planning to migrate a database hosted on-premises to AWS. The database currently has over 50 TB of consumer data, handles highly transactional (OLTP) workloads, and is expected to grow. The Solutions Architect should ensure that the database is ACID-compliant and can handle complex queries of the application.

Which type of database service should the Architect use?
+ Amazon Aurora
+ Amazon Redshift
+ Amazon DynamoDB
+ Amazon RDS

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company needs to accelerate the performance of its AI-powered medical diagnostic application by running its machine learning workloads on the edge of telecommunication carriers' 5G networks. The application must be deployed to a Kubernetes cluster and have role-based access control (RBAC) access to IAM users and roles for cluster authentication.

Which of the following should the Solutions Architect implement to ensure single-digit millisecond latency for the application?
+ Launch the application to an Amazon Elastic Kubernetes Service (Amazon EKS) cluster. Create node groups in Wavelength Zones for the Amazon EKS cluster via the AWS Wavelength service. Apply the AWS authenticator configuration map (`aws-auth ConfigMap`) to your cluster.
+ Host the application to an Amazon Elastic Kubernetes Service (Amazon EKS) cluster. Set up node groups in AWS Wavelength Zones for the Amazon EKS cluster. Attach the Amazon EKS connector agent role (`AmazonECSConnectorAgentRole`) to your cluster and use AWS Control Tower for RBAC access.
+ Launch the application to an Amazon Elastic Kubernetes Service (Amazon EKS) cluster. Create VPC endpoints for the AWS Wavelength Zones and apply them to the Amazon EKS cluster. Install the AWS IAM Authenticator for Kubernetes (`aws-iam-authenticator`) to your cluster.
+ Host the application to an Amazon EKS cluster and run the Kubernetes pods on AWS Fargate. Create node groups in AWS Wavelength Zones for the Amazon EKS cluster. Add the EKS pod execution IAM role (`AmazonEKSFargatePodExecutionRole`) to your cluster and ensure that the Fargate profile has the same IAM role as your Amazon EC2 node groups.

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
AWS Wavelength combines the high bandwidth and ultralow latency of 5G networks with AWS compute and storage services so that developers can innovate and build a new class of applications.

Amazon EKS uses IAM to provide authentication to your Kubernetes cluster, but it still relies on native Kubernetes Role-Based Access Control (RBAC) for authorization. This means that IAM is only used for the authentication of valid IAM entities. All permissions for interacting with your Amazon EKS cluster’s Kubernetes API are managed through the native Kubernetes RBAC system.

Access to your cluster using AWS Identity and Access Management (IAM) entities is enabled by the AWS IAM Authenticator for Kubernetes, which runs on the Amazon EKS control plane. The authenticator gets its configuration information from the aws-auth ConfigMap (AWS authenticator configuration map).

The aws-auth ConfigMap is automatically created and applied to your cluster when you create a managed node group or when you create a node group using eksctl. It is initially created to allow nodes to join your cluster, but you also use this ConfigMap to add role-based access control (RBAC) access to IAM users and roles.

</details>

<br>

---

A data analytics startup is collecting clickstream data and stores them in an S3 bucket. You need to launch an AWS Lambda function to trigger the ETL jobs to run as soon as new data becomes available in Amazon S3.

Which of the following services can you use as an extract, transform, and load (ETL) service in this scenario?
+ S3 Select
+ Redshift Spectrum
+ AWS Step Functions
+ AWS Glue

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A company has 10 TB of infrequently accessed financial data files that would need to be stored in AWS. These data would be accessed infrequently during specific weeks when they are retrieved for auditing purposes. The retrieval time is not strict as long as it does not exceed 24 hours.

Which of the following would be a secure, durable, and cost-effective solution for this scenario?
+ Upload the data to S3 then use a lifecycle policy to transfer data to S3-IA.
+ Upload the data to S3 and set a lifecycle policy to transition data to Glacier after 
+ Upload the data to Amazon FSx for Windows File Server using the Server Message Block (SMB) protocol.
+ Upload the data to S3 then use a lifecycle policy to transfer data to S3 One Zone-IA.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company is using AWS IAM to manage access to AWS services. The Solutions Architect of the company created the following IAM policy for AWS Lambda:
```json
{ 
  "Version": "2012-10-17", 
  "Statement": [
   { 
    "Effect": "Allow", 
    "Action": [ 
     "lambda:CreateFunction",
     "lambda:DeleteFunction"
   ], 
   "Resource": "*"
}, 
{ 
  "Effect": "Deny", 
  "Action": [ 
   "lambda:CreateFunction",
   "lambda:DeleteFunction",
   "lambda:InvokeFunction",
   "lambda:TagResource"
],
  "Resource": "*",
  "Condition": {
    "IpAddress": {
     "aws:SourceIp": "187.5.104.11/32"
    }
   }
  } 
 ] 
} 
```

Which of the following options are allowed by this policy?
+ Delete an AWS Lambda function using the `187.5.104.11/32` address.
+ Create an AWS Lambda function using the `100.220.0.11/32` address.
+ Delete an AWS Lambda function from any network address.
+ Create an AWS Lambda function using the `187.5.104.11/32` address.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A Solutions Architect is working for a multinational telecommunications company. The IT Manager wants to consolidate their log streams including the access, application, and security logs in one single system. Once consolidated, the company will analyze these logs in real-time based on heuristics. There will be some time in the future where the company will need to validate heuristics, which requires going back to data samples extracted from the last 12 hours.

What is the best approach to meet this requirement?
+ First, set up an Auto Scaling group of EC2 servers then store the logs on Amazon S3 then finally, use EMR to apply heuristics on the logs.
+ First, send all of the log events to Amazon Kinesis then afterwards, develop a client process to apply heuristics on the logs.
+ First, configure Amazon Cloud Trail to receive custom logs and then use EMR to apply heuristics on the logs.
+ First, send all the log events to Amazon SQS then set up an Auto Scaling group of EC2 servers to consume the logs and finally, apply the heuristics.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A leading e-commerce company is in need of a storage solution that can be simultaneously accessed by 1000 Linux servers in multiple availability zones. The servers are hosted in EC2 instances that use a hierarchical directory structure via the NFSv4 protocol. The service should be able to handle the rapidly changing data at scale while still maintaining high performance. It should also be highly durable and highly available whenever the servers will pull data from it, with little need for management.

As the Solutions Architect, which of the following services is the most cost-effective choice that you should use to meet the above requirement?
+ S3
+ EFS
+ EBS
+ Storage Gateway

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has an infrastructure that allows EC2 instances from a private subnet to fetch objects from Amazon S3 via a NAT Instance. The company’s Solutions Architect was instructed to lower down the cost incurred by the current solution.

How should the Solutions Architect redesign the architecture in the most cost-efficient manner?

+ Replace the NAT instance with NAT Gateway to access S3 objects.
+ Remove the NAT instance and create an S3 gateway endpoint to access S3 objects.
+ Use a smaller instance type for the NAT instance.
+ Remove the NAT instance and create an S3 interface endpoint to access S3 objects.

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
As a rule of thumb, most AWS services use VPC Interface Endpoint except for S3 and DynamoDB, which use VPC Gateway Endpoint

There is no additional charge for using gateway endpoints. However, standard charges for data transfer and resource usage still apply.

There is no data processing or hourly charges for using Gateway Type VPC endpoints.

</details>

---

A company plans to implement a hybrid architecture. They need to create a dedicated connection from their Amazon Virtual Private Cloud (VPC) to their on-premises network. The connection must provide high bandwidth throughput and a more consistent network experience than Internet-based solutions.

Which of the following can be used to create a private connection between the VPC and the company's on-premises network?

+ AWS Direct Connect
+ Transit VPC
+ Transit Gateway with equal-cost multipath routing (ECMP)
+ AWS Site-to-Site VPN

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A Solutions Architect needs to ensure that all of the AWS resources in Amazon VPC don’t go beyond their respective service limits. The Architect should prepare a system that provides real-time guidance in provisioning resources that adheres to the AWS best practices.

Which of the following is the MOST appropriate service to use to satisfy this task?
+ AWS Cost Explorer
+ AWS Budgets
+ AWS Trusted Advisor
+ Amazon Inspector

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An online shopping platform is hosted on an Auto Scaling group of On-Demand EC2 instances with a default Auto Scaling termination policy and no instance protection configured. The system is deployed across three Availability Zones in the US West region (us-west-1) with an Application Load Balancer in front to provide high availability and fault tolerance for the shopping platform. The us-west-1a, us-west-1b, and us-west-1c Availability Zones have 10, 8 and 7 running instances respectively. Due to the low number of incoming traffic, the scale-in operation has been triggered.   

Which of the following will the Auto Scaling group do to determine which instance to terminate first in this scenario? (Select THREE.)

+ Choose the Availability Zone with the most number of instances, which is the us-west-1a Availability Zone in this scenario.
+ Choose the Availability Zone with the least number of instances, which is the us-west-1c Availability Zone in this scenario.
+ Select the instances with the most recent launch configuration.
+ Select the instances with the oldest launch configuration.
+ Select the instance that is closest to the next billing hour.
+ Select the instance that is farthest to the next billing hour. 

<details close>
<summary>Answer</summary>
a,d,e
</details>

<br>

---

An application is hosted in an Auto Scaling group of EC2 instances. To improve the monitoring process, you have to configure the current capacity to increase or decrease based on a set of scaling adjustments. This should be done by specifying the scaling metrics and threshold values for the CloudWatch alarms that trigger the scaling process.

Which of the following is the most suitable type of scaling policy that you should use?
+ Target tracking scaling
+ Step scaling
+ Simple scaling
+ Scheduled Scaling


<details close>
<summary>Answer</summary>
b
</details>

<br>

A set of metrics!

---

A company has an application hosted in an Amazon ECS Cluster behind an Application Load Balancer. The Solutions Architect is building a sophisticated web filtering solution that allows or blocks web requests based on the country that the requests originate from. However, the solution should still allow specific IP addresses from that country.

Which combination of steps should the Architect implement to satisfy this requirement? (Select TWO.)
+ Using AWS WAF, create a web ACL with a rule that explicitly allows requests from approved IP addresses declared in an IP Set.
+ Add another rule in the AWS WAF web ACL with a geo match condition that blocks requests that originate from a specific country.
+ In the Application Load Balancer, create a listener rule that explicitly allows requests from approved IP addresses.
+ Set up a geo match condition in the Application Load Balancer that blocks requests from a specific country.
+ Place a Transit Gateway in front of the VPC where the application is hosted and set up Network ACLs that block requests that originate from a specific country.
<details close>
<summary>Answer</summary>
a,b
</details>

<br>

---

An application is hosted on an EC2 instance with multiple EBS Volumes attached and uses Amazon Neptune as its database. To improve data security, you encrypted all of the EBS volumes attached to the instance to protect the confidential data stored in the volumes. 

Which of the following statements are true about encrypted Amazon Elastic Block Store volumes? (Select TWO.)
+ All data moving between the volume and the instance are encrypted.
+ Snapshots are automatically encrypted.
+ Snapshots are not automatically encrypted.
+ Only the data in the volume is encrypted and not all the data moving between the volume and the instance.
+ The volumes created from the encrypted snapshot are not encrypted.

<details close>
<summary>Answer</summary>
a,b
</details>

<br>

---

A company has a UAT and production EC2 instances running on AWS. They want to ensure that employees who are responsible for the UAT instances don't have access to work on the production instances to minimize security risks.

Which of the following would be the best way to achieve this?

+ Launch the UAT and production EC2 instances in separate VPC's connected by VPC peering.
+ Provide permissions to the users via the AWS Resource Access Manager (RAM) service to only access EC2 instances that are used for production or development.
+ Launch the UAT and production instances in different Availability Zones and use Multi Factor Authentication.
+ Define the tags on the UAT and production servers and add a condition to the IAM policy which allows access to specific tags. 

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A top IT Consultancy has a VPC with two On-Demand EC2 instances with Elastic IP addresses. You were notified that the EC2 instances are currently under SSH brute force attacks over the Internet. The IT Security team has identified the IP addresses where these attacks originated. You have to immediately implement a temporary fix to stop these attacks while the team is setting up AWS WAF, GuardDuty, and AWS Shield Advanced to permanently fix the security vulnerability.

Which of the following provides the quickest way to stop the attacks to the instances?
+ Place the EC2 instances into private subnets
+ Remove the Internet Gateway from the VPC
+ Block the IP addresses in the Network Access Control List
+ Assign a static Anycast IP address to each EC2 instance

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company plans to design a highly available architecture in AWS. They have two target groups with three EC2 instances each, which are added to an Application Load Balancer. In the security group of the EC2 instance, you have verified that port 80 for HTTP is allowed. However, the instances are still showing out of service from the load balancer.

What could be the root cause of this issue?

+ The instances are using the wrong AMI.
+ The health check configuration is not properly defined.
+ The wrong instance type was used for the EC2 instance.
+ The wrong subnet was used in your VPC
<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has an application hosted in an Auto Scaling group of Amazon EC2 instances across multiple Availability Zones behind an Application Load Balancer. There are several occasions where some instances are automatically terminated after failing the HTTPS health checks in the ALB and then purges all the ephemeral logs stored in the instance. A Solutions Architect must implement a solution that collects all of the application and server logs effectively. She should be able to perform a root cause analysis based on the logs, even if the Auto Scaling group immediately terminated the instance.

What is the EASIEST way for the Architect to automate the log collection from the Amazon EC2 instances?
+ Add a lifecycle hook to your Auto Scaling group to move instances in the `Terminating` state to the `Pending:Wait` state to delay the termination of the unhealthy Amazon EC2 instances. Configure a CloudWatch Events rule for the `EC2 Instance-terminate Lifecycle Action` Auto Scaling Event with an associated Lambda function. Set up an AWS Systems Manager Automation script that collects and uploads the application logs from the instance to a CloudWatch Logs group. Configure the solution to only resume the instance termination once all the logs were successfully sent.
+ Add a lifecycle hook to your Auto Scaling group to move instances in the `Terminating` state to the `Terminating:Wait` state to delay the termination of the unhealthy Amazon EC2 instances. Set up AWS Step Functions to collect the application logs and send them to a CloudWatch Log group. Configure the solution to resume the instance termination as soon as all the logs were successfully sent to CloudWatch Logs.
+ Add a lifecycle hook to your Auto Scaling group to move instances in the `Terminating` state to the `Terminating:Wait` state to delay the termination of unhealthy Amazon EC2 instances. Configure a CloudWatch Events rule for the `EC2 Instance-terminate Lifecycle Action` Auto Scaling Event with an associated Lambda function. Trigger the CloudWatch agent to push the application logs and then resume the instance termination once all the logs are sent to CloudWatch Logs.
+ Add a lifecycle hook to your Auto Scaling group to move instances in the `Terminating` state to the `Terminating:Wait` state to delay the termination of the unhealthy Amazon EC2 instances. Configure a CloudWatch Events rule for the `EC2 Instance Terminate Successful` Auto Scaling Event with an associated Lambda function. Set up the AWS Systems Manager Run Command service to run a script that collects and uploads the application logs from the instance to a CloudWatch Logs group. Resume the instance termination once all the logs are sent.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A leading media company has recently adopted a hybrid cloud architecture which requires them to migrate their application servers and databases in AWS. One of their applications requires a heterogeneous database migration in which you need to transform your on-premises Oracle database to PostgreSQL in AWS. This entails a schema and code transformation before the proper data migration starts.   

Which of the following options is the most suitable approach to migrate the database in AWS? 
+ Configure a Launch Template that automatically converts the source schema and code to match that of the target database. Then, use the AWS Database Migration Service to migrate data from the source database to the target database.  
+ First, use the AWS Schema Conversion Tool to convert the source schema and application code to match that of the target database, and then use the AWS Database Migration Service to migrate data from the source database to the target database.
+ Use Amazon Neptune to convert the source schema and code to match that of the target database in RDS. Use the AWS Batch to effectively migrate the data from the source database to the target database in a batch process.  
+ Heterogeneous database migration is not supported in AWS. You have to transform your database first to PostgreSQL and then migrate it to RDS.  


<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A startup launched a fleet of on-demand EC2 instances to host a massively multiplayer online role-playing game (MMORPG). The EC2 instances are configured with Auto Scaling and AWS Systems Manager.

What can be used to configure the EC2 instances without having to establish an RDP or SSH connection to each instance?
+ AWS Config
+ AWS CodePipeline
+ Run Command
+ EC2Config

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An e-commerce application is using a fanout messaging pattern for its order management system. For every order, it sends an Amazon SNS message to an SNS topic, and the message is replicated and pushed to multiple Amazon SQS queues for parallel asynchronous processing. A Spot EC2 instance retrieves the message from each SQS queue and processes the message. There was an incident that while an EC2 instance is currently processing a message, the instance was abruptly terminated, and the processing was not completed in time.

In this scenario, what happens to the SQS message?
+ When the message visibility timeout expires, the message becomes available for processing by other EC2 instances
+ The message will automatically be assigned to the same EC2 instance when it comes back online within or after the visibility timeout.
+ The message is deleted and becomes duplicated in the SQS when the EC2 instance comes online.
+ The message will be sent to a Dead Letter Queue in AWS DataSync.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A top investment bank is in the process of building a new Forex trading platform. To ensure high availability and scalability, you designed the trading platform to use an Elastic Load Balancer in front of an Auto Scaling group of On-Demand EC2 instances across multiple Availability Zones. For its database tier, you chose to use a single Amazon Aurora instance to take advantage of its distributed, fault-tolerant, and self-healing storage system.

In the event of system failure on the primary database instance, what happens to Amazon Aurora during the failover?

+ Amazon Aurora flips the canonical name record (CNAME) for your DB Instance to point at the healthy replica, which in turn is promoted to become the new primary.
+ Aurora will attempt to create a new DB Instance in the same Availability Zone as the original instance and is done on a best-effort basis.
+ Amazon Aurora flips the A record of your DB Instance to point at the healthy replica, which in turn is promoted to become the new primary.
+ Aurora will first attempt to create a new DB Instance in a different Availability Zone of the original instance. If unable to do so, Aurora will attempt to create a new DB Instance in the original Availability Zone in which the instance was first launched.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has a web application hosted on a fleet of EC2 instances located in two Availability Zones that are all placed behind an Application Load Balancer. As a Solutions Architect, you have to add a health check configuration to ensure your application is highly-available.

Which health checks will you implement?

+ HTTP or HTTPS health check
+ ICMP health check
+ FTP health check
+ TCP health check

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

In a startup company you are working for, you are asked to design a web application that requires a NoSQL database that has no limit on the storage size for a given table. The startup is still new in the market and it has very limited human resources who can take care of the database infrastructure.

Which is the most suitable service that you can implement that provides a fully managed, scalable and highly available NoSQL service?
+ DynamoDB
+ Amazon Neptune
+ Amazon Aurora
+ SimpleDB

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A news company is planning to use a Hardware Security Module (CloudHSM) in AWS for secure key storage of their web applications. You have launched the CloudHSM cluster but after just a few hours, a support staff mistakenly attempted to log in as the administrator three times using an invalid password in the Hardware Security Module. This has caused the HSM to be zeroized, which means that the encryption keys on it have been wiped. Unfortunately, you did not have a copy of the keys stored anywhere else.

How can you obtain a new copy of the keys that you have stored on Hardware Security Module?
+ Restore a snapshot of the Hardware Security Module.
+ Contact AWS Support and they will provide you a copy of the keys.
+ The keys are lost permanently if you did not have a copy.
+ Use the Amazon CLI to get a copy of the keys.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A business plans to deploy an application on EC2 instances within an Amazon VPC and is considering adopting a Network Load Balancer to distribute incoming traffic among the instances. A solutions architect needs to suggest a solution that will enable the security team to inspect traffic entering and exiting their VPC.

Which approach satisfies the requirements?
+ Create a firewall using the AWS Network Firewall service at the VPC level then add custom rule groups for inspecting ingress and egress traffic. Update the necessary VPC route tables.
+ Use the Network Access Analyzer service on the application’s VPC for inspecting ingress and egress traffic. Create a new Network Access Scope to filter and analyze all incoming and outgoing requests.
+ Create a firewall at the subnet level using the Amazon Detective service. Inspect the ingress and egress traffic using the VPC Reachability Analyzer.
+ Enable Traffic Mirroring on the Network Load Balancer and forward traffic to the instances. Create a traffic mirror filter to inspect the ingress and egress of data that traverses your Amazon VPC.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company needs to use Amazon S3 to store irreproducible financial documents. For their quarterly reporting, the files are required to be retrieved after a period of 3 months. There will be some occasions when a surprise audit will be held, which requires access to the archived data that they need to present immediately.

What will you do to satisfy this requirement in a cost-effective way?
+ Use Amazon S3 Standard
+ Use Amazon S3 Standard - Infrequent Access
+ Use Amazon S3 -Intelligent Tiering
+ Use Amazon Glacier Deep Archive

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

An On-Demand EC2 instance is launched into a VPC subnet with the Network ACL configured to allow all inbound traffic and deny all outbound traffic. The instance’s security group has an inbound rule to allow SSH from any IP address and does not have any outbound rules. 

In this scenario, what are the changes needed to allow SSH connection to the instance?
+ The outbound security group needs to be modified to allow outbound traffic.
+ The network ACL needs to be modified to allow outbound traffic.
+ No action needed. It can already be accessed from any IP address using SSH.
+ Both the outbound security group and outbound network ACL need to be modified to allow outbound traffic.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

An investment bank has a distributed batch processing application which is hosted in an Auto Scaling group of Spot EC2 instances with an SQS queue. You configured your components to use client-side buffering so that the calls made from the client will be buffered first and then sent as a batch request to SQS. What is a period of time during which the SQS queue prevents other consuming components from receiving and processing a message?
+ Component Timeout
+ Visibility Timeout
+ Processing Timeout
+ Receiving Timeout

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A multimedia company needs to deploy web services to an AWS region that they have never used before. The company currently has an IAM role for its Amazon EC2 instance that permits the instance to access Amazon DynamoDB. They want their EC2 instances in the new region to have the exact same privileges.

What should be done to accomplish this?

+ In the new Region, create a new IAM role and associated policies then assign it to the new instance.
+ Assign the existing IAM role to instances in the new region.
+ Duplicate the IAM role and associated policies to the new region and attach it to the instances.
+ Create an Amazon Machine Image (AMI) of the instance and copy it to the new region.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A financial company wants to store their data in Amazon S3 but at the same time, they want to store their frequently accessed data locally on their on-premises server. This is due to the fact that they do not have the option to extend their on-premises storage, which is why they are looking for a durable and scalable storage service to use in AWS.

What is the best solution for this scenario?
+ Use a fleet of EC2 instance with EBS volumes to store the commonly used data.
+ Use both Elasticache and S3 for frequently accessed data.
+ Use the Amazon Storage Gateway -  Cached Volumes.
+ Use Amazon Glacier.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company troubleshoots the operational issues of their cloud architecture by logging the AWS API call history of all AWS resources. The Solutions Architect must implement a solution to quickly identify the most recent changes made to resources in their environment, including creation, modification, and deletion of AWS resources. One of the requirements is that the generated log files should be encrypted to avoid any security issues.

Which of the following is the most suitable approach to implement the encryption?
+ Use CloudTrail and configure the destination Amazon Glacier archive to use Server-Side Encryption (SSE).
+ Use CloudTrail and configure the destination S3 bucket to use Server-Side Encryption (SSE).
+ Use CloudTrail and configure the destination S3 bucket to use Server Side Encryption (SSE) with AES-128 encryption algorithm.
+ Use CloudTrail with its default settings

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A company has a running m5ad.large EC2 instance with a default attached 75 GB SSD instance-store backed volume. You shut it down and then start the instance. You noticed that the data which you have saved earlier on the attached volume is no longer available.

What might be the cause of this?
+ The volume of the instance was not big enough to handle all of the processing data.
+ The EC2 instance was using EBS backed root volumes, which are ephemeral and only live for the life of the instance.
+ The EC2 instance was using instance store volumes, which are ephemeral and only live for the life of the instance.
+ The instance was hit by a virus that wipes out all data.
<details close>
<summary>Answer</summary>
c
</details>

<br>

---


A Solutions Architect is working for a fast-growing startup that just started operations during the past 3 months. They currently have an on-premises Active Directory and 10 computers. To save costs in procuring physical workstations, they decided to deploy virtual desktops for their new employees in a virtual private cloud in AWS. The new cloud infrastructure should leverage the existing security controls in AWS but can still communicate with their on-premises network.

Which set of AWS services will the Architect use to meet these requirements?
+ AWS Directory Services, VPN connection, and ClassicLink
+ AWS Directory Services, VPN connection, and Amazon Workspaces
+ AWS Directory Services, VPN connection, and AWS Identity and Access Management
+ AWS Directory Services, VPN connection, and Amazon S3
<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A client is hosting their company website on a cluster of web servers that are behind a public-facing load balancer. The client also uses Amazon Route 53 to manage their public DNS.   

How should the client configure the DNS zone apex record to point to the load balancer?

+ Create an A record pointing to the IP address of the load balancer.
+ Create a CNAME record pointing to the load balancer DNS name.
+ Create an alias for CNAME record to the load balancer DNS name.
+ Create an A record aliased to the load balancer DNS name.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A web application is hosted on an EC2 instance that processes sensitive financial information which is launched in a private subnet. All of the data are stored in an Amazon S3 bucket. Financial information is accessed by users over the Internet. The security team of the company is concerned that the Internet connectivity to Amazon S3 is a security risk.

In this scenario, what will you do to resolve this security vulnerability in the most cost-effective manner?
+ Change the web architecture to access the financial data through a Gateway VPC Endpoint.
+ Change the web architecture to access the financial data in your S3 bucket through a VPN connection. 
+ Change the web architecture to access the financial data hosted in your S3 bucket by creating a custom VPC endpoint service.
+ Change the web architecture to access the financial data in S3 through an interface VPC endpoint, which is powered by AWS PrivateLink.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company has an On-Demand EC2 instance with an attached EBS volume. There is a scheduled job that creates a snapshot of this EBS volume every midnight at 12 AM when the instance is not used. One night, there has been a production incident where you need to perform a change on both the instance and on the EBS volume at the same time when the snapshot is currently taking place.

Which of the following scenario is true when it comes to the usage of an EBS volume while the snapshot is in progress?
+ The EBS volume can be used while the snapshot is in progress.
+ The EBS volume cannot be detached or attached to an EC2 instance until the snapshot completes
+ The EBS volume can be used in read-only mode while the snapshot is in progress.
+ The EBS volume cannot be used until the snapshot completes.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

The start-up company that you are working for has a batch job application that is currently hosted on an EC2 instance. It is set to process messages from a queue created in SQS with default settings. You configured the application to process the messages once a week. After 2 weeks, you noticed that not all messages are being processed by the application.

What is the root cause of this issue?
+ The batch job application is configured to long polling.
+ Amazon SQS has automatically deleted the messages that have been in a queue for more than the maximum message retention period.
+ The SQS queue is set to short-polling.
+ Missing permissions in SQS.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A Solutions Architect joined a large tech company with an existing Amazon VPC. When reviewing the Auto Scaling events, the Architect noticed that their web application is scaling up and down multiple times within the hour.

What design change could the Architect make to optimize cost while preserving elasticity?
+ Change the cooldown period of the Auto Scaling group and set the CloudWatch metric to a higher threshold
+ Increase the instance type in the launch configuration
+ Increase the base number of Auto Scaling instances for the Auto Scaling group
+ Add provisioned IOPS to the instances

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A health organization is using a large Dedicated EC2 instance with multiple EBS volumes to host its health records web application. The EBS volumes must be encrypted due to the confidentiality of the data that they are handling and also to comply with the HIPAA (Health Insurance Portability and Accountability Act) standard.   

In EBS encryption, what service does AWS use to secure the volume's data at rest? (Select TWO.)
+ By using your own keys in AWS Key Management Service (KMS).
+ By using S3 Server-Side Encryption.
+ By using Amazon-managed keys in AWS Key Management Service (KMS).
+ By using S3 Client-Side Encryption.
+ By using a password stored in CloudHSM.
+ By using the SSL certificates provided by the AWS Certificate Manager (ACM).

<details close>
<summary>Answer</summary>
a,c
</details>

<br>

---
A company plans to deploy a Docker-based batch application in AWS. The application will be used to process both mission-critical data as well as non-essential batch jobs.

Which of the following is the most cost-effective option to use in implementing this architecture?
+ Use ECS as the container management service then set up a combination of Reserved and Spot EC2 Instances for processing mission-critical and non-essential batch jobs respectively.  
+ Use ECS as the container management service then set up Reserved EC2 Instances for processing both mission-critical and non-essential batch jobs.  
+ Use ECS as the container management service then set up On-Demand EC2 Instances for processing both mission-critical and non-essential batch jobs.  
+ Use ECS as the container management service then set up Spot EC2 Instances for processing both mission-critical and non-essential batch jobs.  

<details close>
<summary>Answer</summary>
a
</details>

<br>

---
A company is running a batch job on an EC2 instance inside a private subnet. The instance gathers input data from an S3 bucket in the same region through a NAT Gateway. The company is looking for a solution that will reduce costs without imposing risks on redundancy or availability.

Which solution will accomplish this?
+ Replace the NAT Gateway with a NAT instance hosted on a burstable instance type.
+ Deploy a Transit Gateway to peer connection between the instance and the S3 bucket.
+ Remove the NAT Gateway and use a Gateway VPC endpoint to access the S3 bucket from the instance. 
+ Re-assign the NAT Gateway to a lower EC2 instance type.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company plans to use Route 53 instead of an ELB to load balance the incoming request to the web application. The system is deployed to two EC2 instances to which the traffic needs to be distributed. You want to set a specific percentage of traffic to go to each instance.

Which routing policy would you use?
+ Latency
+ Failover
+ Weighted
+ Geolocation

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company is planning to launch a High Performance Computing (HPC) cluster in AWS that does Computational Fluid Dynamics (CFD) simulations. The solution should scale-out their simulation jobs to experiment with more tunable parameters for faster and more accurate results. The cluster is composed of Windows servers hosted on t3a.medium EC2 instances. As the Solutions Architect, you should ensure that the architecture provides higher bandwidth, higher packet per second (PPS) performance, and consistently lower inter-instance latencies.

Which is the MOST suitable and cost-effective solution that the Architect should implement to achieve the above requirements?
+ Enable Enhanced Networking with Elastic Network Adapter (ENA) on the Windows EC2 Instances.
+ Enable Enhanced Networking with Elastic Fabric Adapter (EFA) on the Windows EC2 Instances.
+ Enable Enhanced Networking with Intel 82599 Virtual Function (VF) interface on the Windows EC2 Instances.
+ Use AWS ParallelCluster to deploy and manage the HPC cluster to provide higher bandwidth, higher packet per second (PPS) performance, and lower inter-instance latencies.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A social media company needs to capture the detailed information of all HTTP requests that went through their public-facing Application Load Balancer every five minutes. The client's IP address and network latencies must also be tracked. They want to use this data for analyzing traffic patterns and for troubleshooting their Docker applications orchestrated by the Amazon ECS Anywhere service.

Which of the following options meets the customer requirements with the LEAST amount of overhead?
+ Enable AWS CloudTrail for their Application Load Balancer. Use the AWS CloudTrail Lake to analyze and troubleshoot the application traffic.
+ Enable access logs on the Application Load Balancer. Integrate the Amazon ECS cluster with Amazon CloudWatch Application Insights to analyze traffic patterns and simplify troubleshooting.
+ Install and run the AWS X-Ray daemon on the Amazon ECS cluster. Use the Amazon CloudWatch ServiceLens to analyze the traffic that goes through the application.
+ Integrate Amazon EventBridge (Amazon CloudWatch Events) metrics on the Application Load Balancer to capture the client IP address. Use Amazon CloudWatch Container Insights to analyze traffic patterns.


<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A healthcare company stores sensitive patient health records in their on-premises storage systems. These records must be kept indefinitely and protected from any type of modifications once they are stored. Compliance regulations mandate that the records must have granular access control and each data access must be audited at all levels. Currently, there are millions of obsolete records that are not accessed by their web application, and their on-premises storage is quickly running out of space. The Solutions Architect must design a solution to immediately move existing records to AWS and support the ever-growing number of new health records.

Which of the following is the most suitable solution that the Solutions Architect should implement to meet the above requirements?

+ Set up AWS Storage Gateway to move the existing health records from the on-premises network to the AWS Cloud. Launch a new Amazon S3 bucket to store existing and new records. Enable AWS CloudTrail with Management Events and Amazon S3 Object Lock in the bucket.
+ Set up AWS DataSync to move the existing health records from the on-premises network to the AWS Cloud. Launch a new Amazon S3 bucket to store existing and new records. Enable AWS CloudTrail with Data Events and Amazon S3 Object Lock in the bucket.
+ Set up AWS Storage Gateway to move the existing health records from the on-premises network to the AWS Cloud. Launch an Amazon EBS-backed EC2 instance to store both the existing and new records. Enable Amazon S3 server access logging and S3 Object Lock in the bucket.
+ Set up AWS DataSync to move the existing health records from the on-premises network to the AWS Cloud. Launch a new Amazon S3 bucket to store existing and new records. Enable AWS CloudTrail with Management Events and Amazon S3 Object Lock in the bucket.


<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
AWS DataSync is an online data transfer service that simplifies, automates, and accelerates moving data between on-premises storage systems and AWS Storage services, as well as between AWS Storage services. You can use DataSync to migrate active datasets to AWS, archive data to free up on-premises storage capacity, replicate data to AWS for business continuity, or transfer data to the cloud for analysis and processing.

Both AWS Storage Gateway and AWS DataSync can send data from your on-premises data center to AWS and vice versa. However, AWS Storage Gateway is more suitable to be used in integrating your storage services by replicating your data while AWS DataSync is better for workloads that require you to move or migrate your data.
</details>

<br>

---

An application is hosted in an On-Demand EC2 instance and is using Amazon SDK to communicate to other AWS services such as S3, DynamoDB, and many others. As part of the upcoming IT audit, you need to ensure that all API calls to your AWS resources are logged and durably stored. 

Which is the most suitable service that you should use to meet this requirement?
+ Amazon CloudWatch
+ AWS CloudTrail
+ AWS X-Ray
+ Amazon API Gateway

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has both on-premises data center as well as AWS cloud infrastructure. They store their graphics, audios, videos, and other multimedia assets primarily in their on-premises storage server and use an S3 Standard storage class bucket as a backup. Their data is heavily used for only a week (7 days) but after that period, it will only be infrequently used by their customers. The Solutions Architect is instructed to save storage costs in AWS yet maintain the ability to fetch a subset of their media assets in a matter of minutes for a surprise annual data audit, which will be conducted on their cloud storage.

Which of the following are valid options that the Solutions Architect can implement to meet the above requirement? (Select TWO.)
+ Set a lifecycle policy in the bucket to transition the data to Glacier after one week (7 days).
+ Set a lifecycle policy in the bucket to transition the data to S3 - Standard IA storage class after one week (7 days).
+ Set a lifecycle policy in the bucket to transition the data to S3 - One Zone-Infrequent Access storage class after one week (7 days).
+ Set a lifecycle policy in the bucket to transition the data to S3 Glacier Deep Archive storage class after one week (7 days).
+ Set a lifecycle policy in the bucket to transition to S3 - Standard IA after 30 days

<details close>
<summary>Answer</summary>
a,e
</details>

<br>

---

A company has a web-based ticketing service that utilizes Amazon SQS and a fleet of EC2 instances. The EC2 instances that consume messages from the SQS queue are configured to poll the queue as often as possible to keep end-to-end throughput as high as possible. The Solutions Architect noticed that polling the queue in tight loops is using unnecessary CPU cycles, resulting in increased operational costs due to empty responses.

In this scenario, what should the Solutions Architect do to make the system more cost-effective?
+ Configure Amazon SQS to use long polling by setting the ReceiveMessageWaitTimeSeconds to zero.
+ Configure Amazon SQS to use long polling by setting the ReceiveMessageWaitTimeSeconds to a number greater than zero.
+ Configure Amazon SQS to use short polling by setting the ReceiveMessageWaitTimeSeconds to a number greater than zero.
+ Configure Amazon SQS to use short polling by setting the ReceiveMessageWaitTimeSeconds to zero.

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
The ReceiveMessageWaitTimeSeconds is the queue attribute that determines whether you are using Short or Long polling. By default, its value is zero which means it is using Short polling. If it is set to a value greater than zero, then it is Long polling.
</details>
<br>

---

A local bank has an in-house application that handles sensitive financial data in a private subnet. After the data is processed by the EC2 worker instances, they will be delivered to S3 for ingestion by other services.

How should you design this solution so that the data does not pass through the public Internet?
+ Create an Internet gateway in the public subnet with a corresponding route entry that directs the data to S3.
+ Configure a Transit gateway along with a corresponding route entry that directs the data to S3.
+ Configure a VPC Endpoint along with a corresponding route entry that directs the data to S3.
+ Provision a NAT gateway in the private subnet with a corresponding route entry that directs the data to S3.


<details close>
<summary>Answer</summary>
c
</details>

---
A data analytics company keeps a massive volume of data that they store in their on-premises data center. To scale their storage systems, they are looking for cloud-backed storage volumes that they can mount using Internet Small Computer System Interface (iSCSI) devices from their on-premises application servers. They have an on-site data analytics application that frequently accesses the latest data subsets locally while the older data are rarely accessed. You are required to minimize the need to scale the on-premises storage infrastructure while still providing their web application with low-latency access to the data.

Which type of AWS Storage Gateway service will you use to meet the above requirements?
+ Volume Gateway in stored mode
+ Tape Gateway
+ Volume Gateway in cached mode
+ File Gateway

<details close>
<summary>Answer</summary>
c
</details>

---

A company deployed a web application that stores static assets in an Amazon Simple Storage Service (S3) bucket. The Solutions Architect expects the S3 bucket to immediately receive over 2000 PUT requests and 3500 GET requests per second at peak hour.

What should the Solutions Architect do to ensure optimal performance?
+ Use Byte-Range Fetches to retrieve multiple ranges of an object data per GET request.
+ Add a random prefix to the key names.
+ Do nothing. Amazon S3 will automatically manage performance at this scale.
+ Use a predictable naming scheme in the key names such as sequential numbers or date time sequences.


<details close>
<summary>Answer</summary>
c
</details>


<details close>
<summary>Note</summary>
Amazon S3 now provides increased performance to support at least 3,500 requests per second to add data and 5,500 requests per second to retrieve data, which can save significant processing time for no additional charge. Each S3 prefix can support these request rates, making it simple to increase performance significantly.
</details>

---

A Solutions Architect is migrating several Windows-based applications to AWS that require a scalable file system storage for high-performance computing (HPC). The storage service must have full support for the SMB protocol and Windows NTFS, Active Directory (AD) integration, and Distributed File System (DFS).

Which of the following is the MOST suitable storage service that the Architect should use to fulfill this scenario?
+ Amazon FSx for Windows File Server
+ Amazon S3 Glacier Deep Archive
+ AWS DataSync
+ Amazon FSx for Lustre

<details close>
<summary>Answer</summary>
a
</details>

---


A company has a web application hosted in their on-premises infrastructure that they want to migrate to AWS cloud. Your manager has instructed you to ensure that there is no downtime while the migration process is on-going. In order to achieve this, your team decided to divert 50% of the traffic to the new application in AWS and the other 50% to the application hosted in their on-premises infrastructure. Once the migration is over and the application works with no issues, a full diversion to AWS will be implemented. The company's VPC is connected to its on-premises network via an AWS Direct Connect connection.

Which of the following are the possible solutions that you can implement to satisfy the above requirement? (Select TWO.)

+ Use a Network Load balancer with Weighted Target Groups to divert the traffic between the on-premises and AWS-hosted application. Divert 50% of the traffic to the new application in AWS and the other 50% to the application hosted in their on-premises infrastructure.
+ Use an Application Elastic Load balancer with Weighted Target Groups to divert and proportion the traffic between the on-premises and AWS-hosted application. Divert 50% of the traffic to the new application in AWS and the other 50% to the application hosted in their on-premises infrastructure.
+ Use Route 53 with Failover routing policy to divert and proportion the traffic between the on-premises and AWS-hosted application. Divert 50% of the traffic to the new application in AWS and the other 50% to the application hosted in their on-premises infrastructure.
+ Use Route 53 with Weighted routing policy to divert the traffic between the on-premises and AWS-hosted application. Divert 50% of the traffic to the new application in AWS and the other 50% to the application hosted in their on-premises infrastructure.
+ Use AWS Global Accelerator to divert and proportion the HTTP and HTTPS traffic between the on-premises and AWS-hosted application. Ensure that the on-premises network has an AnyCast static IP address and is connected to your VPC via a Direct Connect Gateway.

<details close>
<summary>Answer</summary>
b,d
</details>

---

A company needs secure access to its Amazon RDS for MySQL database that is used by multiple applications. Each IAM user must use a short-lived authentication token to connect to the database.

Which of the following is the most suitable solution in this scenario?
+ Use AWS SSO to access the RDS database.
+ Use IAM DB Authentication and create database accounts using the AWS-provided `AWSAuthenticationPlugin` plugin in MySQL.
+ Use AWS Secrets Manager to generate and store short-lived authentication tokens.
+ Use an MFA token to access and connect to a database.

<details close>
<summary>Answer</summary>
b
</details>

---
An organization plans to run an application in a dedicated physical server that doesn’t use virtualization. The application data will be stored in a storage solution that uses an NFS protocol. To prevent data loss, you need to use a durable cloud storage service to store a copy of your data.

Which of the following is the most suitable solution to meet the requirement?
+ Use an AWS Storage Gateway hardware appliance for your compute resources. Configure Volume Gateway to store the application data and backup data.
+  Use an AWS Storage Gateway hardware appliance for your compute resources. Configure File Gateway to store the application data and create an Amazon S3 bucket to store a backup of your data.
+ Use an AWS Storage Gateway hardware appliance for your compute resources. Configure Volume Gateway to store the application data and create an Amazon S3 bucket to store a backup of your data.
+ Use AWS Storage Gateway with a gateway VM appliance for your compute resources. Configure File Gateway to store the application data and backup data.

<details close>
<summary>Answer</summary>
b
</details>

---

A startup needs to use a shared file system for its .NET web application running on an Amazon EC2 Windows instance. The file system must provide a high level of throughput and IOPS that can also be integrated with Microsoft Active Directory.

Which is the MOST suitable service that you should use to achieve this requirement?
+ Amazon EBS Provisioned IOPS SSD volumes
+ Amazon FSx for Windows File Server
+ Amazon Elastic File System
+ AWS Storage Gateway - File Gateway

<details close>
<summary>Answer</summary>
b
</details>

---

A web application hosted in an Auto Scaling group of EC2 instances in AWS. The application receives a burst of traffic every morning, and a lot of users are complaining about request timeouts. The EC2 instance takes 1 minute to boot up before it can respond to user requests. The cloud architecture must be redesigned to better respond to the changing traffic of the application.

How should the Solutions Architect redesign the architecture?
+ Create a Network Load Balancer with slow-start mode.
+ Create a new launch template and upgrade the size of the instance.
+ Create a step scaling policy and configure an instance warm-up time condition.
+ Create a CloudFront distribution and set the EC2 instance as the origin.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has several microservices that send messages to an Amazon SQS queue and a backend application that poll the queue to process the messages. The company also has a Service Level Agreement (SLA) which defines the acceptable amount of time that can elapse from the point when the messages are received until a response is sent. The backend operations are I/O-intensive as the number of messages is constantly growing, causing the company to miss its SLA. The Solutions Architect must implement a new architecture that improves the application's processing time and load management.

Which of the following is the MOST effective solution that can satisfy the given requirement?
+ Create an AMI of the backend application's EC2 instance. Use the image to set up an Auto Scaling group and configure a target tracking scaling policy based on the `CPUUtilization` metric with a target value of 80%.
+ Create an AMI of the backend application's EC2 instance and replace it with a larger instance size.
+ Create an AMI of the backend application's EC2 instance. Use the image to set up an Auto Scaling group and configure a target tracking scaling policy based on the `ApproximateAgeOfOldestMessage` metric.
+ Create an AMI of the backend application's EC2 instance and launch it to a cluster placement group.

<details close>
<summary>Answer</summary>
c
</details>

---
An operations team has an application running on EC2 instances inside two custom VPCs. The VPCs are located in the Ohio and N.Virginia Region respectively. The team wants to transfer data between the instances without traversing the public internet.

Which combination of steps will achieve this? (Select TWO.) 
+ Set up a VPC peering connection between the VPCs.
+ Create an Egress-only Internet Gateway.
+ Re-configure the route table’s target and destination of the instances’ subnet.
+ Launch a NAT Gateway in the public subnet of each VPC.
+ Deploy a VPC endpoint on each region to enable a private connection.

<details close>
<summary>Answer</summary>
a,c
</details>

---

A company has multiple AWS Site-to-Site VPN connections placed between their VPCs and their remote network. During peak hours, many employees are experiencing slow connectivity issues, which limits their productivity. The company has asked a solutions architect to scale the throughput of the VPN connections.

Which solution should the architect carry out?
+ Associate the VPCs to an Equal Cost Multipath Routing (ECMR)-enabled transit gateway and attach additional VPN tunnels.
+ Add more virtual private gateways to a VPC and enable Equal Cost Multipath Routing (ECMR) to get higher VPN bandwidth.
+ Modify the VPN configuration by increasing the number of tunnels to scale the throughput.
+ Re-route some of the VPN connections to a secondary customer gateway device on the remote network’s end.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
AWS Transit Gateway also enables you to scale the IPsec VPN throughput with equal-cost multi-path (ECMP) routing support over multiple VPN tunnels. A single VPN tunnel still has a maximum throughput of 1.25 Gbps. If you establish multiple VPN tunnels to an ECMP-enabled transit gateway, it can scale beyond the default limit of 1.25 Gbps.
</details>

---

A company needs to accelerate the development of its GraphQL APIs for its new customer service portal. The solution must be serverless to lower the monthly operating cost of the business. Their GraphQL APIs must be accessible via HTTPS and have a custom domain.

What solution should the Solutions Architect implement to meet the above requirements?
+ Launch an AWS Elastic Beanstalk environment and use Amazon Route 53 for the custom domain. Configure Domain Name System Security Extensions (DNSSEC) in the Route 53 hosted zone to enable HTTPS communication.
+ Host the application in the VMware Cloud on AWS service. Associate a custom domain to the GraphSQL APIs via the AWS Directory Service for Microsoft Active Directory and provide multiple domain controllers to enable HTTPS communication.
+ Deploy the GraphQL APIs as Kubernetes pods to AWS Fargate and AWS Outposts using Amazon EKS Anywhere for deployment. Create a custom domain using Amazon CloudFront and enable the Origin Shield feature to allow HTTPS communication to the GraphQL APIs.
+ Develop the application using the AWS AppSync service and use its built-in custom domain feature. Associate an SSL certificate to the AWS AppSync API using the AWS Certificate Manager (ACM) service to enable HTTPS communication.

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
AWS AppSync is a serverless GraphQL and Pub/Sub API service that simplifies building modern web and mobile applications. It provides a robust, scalable GraphQL interface for application developers to combine data from multiple sources, including Amazon DynamoDB, AWS Lambda, and HTTP APIs.


</details>

---
A logistics company based in the USA runs its web application on a fleet of Amazon EC2 instances in an Auto Scaling group. It runs the same application in multiple AWS regions to cater to clients across several countries. A recent government policy has been enacted that prohibits the company from servicing a specific country.

Which of the following options is the recommended action to comply with the government requirement?
+ Create a Web ACL rule in AWS WAF to block the specified country. Associate the rule to the Application Load Balancers.
+ Update the route tables to forward all outbound traffic to AWS Network Firewall and configure a stateful domain list rule group to block the specified country
+ Update the Network Access Control Lists of all subnets used by the Amazon EC2 instances to “deny” all IP addresses from the specific country.
+ Update the Network Access Control Lists of all subnets used by the Application Load Balancers to “deny” all IP addresses from the specific country.

<details close>
<summary>Answer</summary>
a
</details>

---

A company has multiple research departments that have deployed several resources to the AWS cloud. The departments are free to provision their own resources as they are needed. To ensure normal operations, the company wants to track its AWS resource usage so that it is not reaching the AWS service quotas unexpectedly.

Which combination of actions should the Solutions Architect implement to meet the company requirements? (Select TWO.)
+ Create an Amazon Simple Notification Service (Amazon SNS) topic and configure it as a target for notifications.
+ Capture the events using Amazon EventBridge (Amazon CloudWatch Events) and use an Amazon Simple Notification Service (Amazon SNS) topic as the target for notifications.
+ Query the AWS Trusted Advisor Service Limits check every 24 hours by calling the `DescribeTrustedAdvisorChecks` API operation. Ensure that your AWS account has a Developer support plan.
+ Write an AWS Lambda function that refreshes the AWS Trusted Advisor Service Limits checks and set it to run every 24 hours.
+ Utilize the AWS managed rule on AWS Config to monitor AWS resource service quotas. Schedule this checking using an AWS Lambda function.

<details close>
<summary>Answer</summary>
b,d
</details>

