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

5-13