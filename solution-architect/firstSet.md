# Solution Architect Exam#1 Practice Set

A company hosted a web application in an Auto Scaling group of EC2 instances. The IT manager is concerned about the over-provisioning of the resources that can cause higher operating costs. A Solutions Architect has been instructed to create a cost-effective solution without affecting the performance of the application.

Which dynamic scaling policy should be used to satisfy this requirement?

+ Use simple scaling
+ Use scheduled scaling
+ Use suspend and resume scaling
+ Use target tracking scaling

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
Use simple scaling is incorrect because you need to wait for the cooldown period to complete before initiating additional scaling activities. Target tracking or step scaling policies can trigger a scaling activity immediately without waiting for the cooldown period to expire.

Use scheduled scaling is incorrect because this policy is mainly used for predictable traffic patterns. You need to use the target tracking scaling policy to optimize the cost of your infrastructure without affecting the performance.

Use suspend and resume scaling is incorrect because this type is used to temporarily pause scaling activities triggered by your scaling policies and scheduled actions.
</details>

<br>

---

An online medical system hosted in AWS stores sensitive Personally Identifiable Information (PII) of the users in an Amazon S3 bucket. Both the master keys and the unencrypted data should never be sent to AWS to comply with the strict compliance and regulatory requirements of the company.

Which S3 encryption technique should the Architect use?
+ Use S3 client-side encryption with a KMS-managed customer master key.
+ Use S3 client-side encryption with a client-side master key.
+ Use S3 server-side encryption with a KMS managed key.
+ Use S3 server-side encryption with customer provided key.

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A Solutions Architect is hosting a website in an Amazon S3 bucket named `tutorialsdojo`. The users load the website using the following URL: `http://tutorialsdojo.s3-website-us-east-1.amazonaws.com` and there is a new requirement to add a JavaScript on the webpages in order to make authenticated HTTP `GET` requests against the same bucket by using the Amazon S3 API endpoint (`tutorialsdojo.s3.amazonaws.com`). Upon testing, you noticed that the web browser blocks JavaScript from allowing those requests.

Which of the following options is the MOST suitable solution that you should implement for this scenario?

+ Enable cross-account access.
+ Enable Cross-Zone Load Balancing.
+ Enable Cross-origin resource sharing (CORS) configuration in the bucket.
+ Enable Cross-Region Replication (CRR).

<details close>
<summary>Answer</summary>
c
</details>

<br>


---

A company is in the process of migrating their applications to AWS. One of their systems requires a database that can scale globally and handle frequent schema changes. The application should not have any downtime or performance issues whenever there is a schema change in the database. It should also provide a low latency response to high-traffic queries.

Which is the most suitable database solution to use to achieve this requirement?
+ An Amazon RDS instance in Multi-AZ Deployments configuration
+ Amazon DynamoDB
+ An Amazon Aurora database with Read Replicas
+ Redshift

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A government entity is conducting a population and housing census in the city. Each household information uploaded on their online portal is stored in encrypted files in Amazon S3. The government assigned its Solutions Architect to set compliance policies that verify data containing personally identifiable information (PII) in a manner that meets their compliance standards. They should also be alerted if there are potential policy violations with the privacy of their S3 buckets.

Which of the following should the Architect implement to satisfy this requirement?
+ Set up and configure Amazon Macie to monitor their Amazon S3 data.
+ Set up and configure Amazon Kendra to monitor malicious activity on their Amazon S3 data
+ Set up and configure Amazon Polly to scan for usage patterns on Amazon S3 data
+ Set up and configure Amazon Fraud Detector to send out alert notifications whenever a security violation is detected on their Amazon S3 data.

<details close>
<summary>Answer</summary>
a
</details>

<br>


<details close>
<summary>Note</summary>
Macie:  ML-powered security service, preventing data loss by automatically discovering, classifying, and protecting sensitive data stored in Amazon S3. Uses machine learning to recognize sensitive data such as personally identifiable information (PII) or intellectual property, assigns a business value, and provides visibility into where this data is stored and how it is being used in your organization.
Amazon Macie generates two categories of findings: policy findings and sensitive data findings

Polly: turn text into lifelike speech
Kendra: enterprise search service that allows developers to add search capabilities to their applications
Fraud Detector: a fully managed service for identifying potentially fraudulent activities and for catching more online fraud faster. It does not check any S3 data containing personally identifiable information (PII), unlike Amazon Macie.
</details>

<br>

---

A global IT company with offices around the world has multiple AWS accounts. To improve efficiency and drive costs down, the Chief Information Officer (CIO) wants to set up a solution that centrally manages their AWS resources. This will allow them to procure AWS resources centrally and share resources such as AWS Transit Gateways, AWS License Manager configurations, or Amazon Route 53 Resolver rules across their various accounts.

As the Solutions Architect, which combination of options should you implement in this scenario? (Select TWO.)
+ Use the AWS Resource Access Manager (RAM) service to easily and securely share your resources with your AWS accounts.
+ Use the AWS Identity and Access Management service to set up cross-account access that will easily and securely share your resources with your AWS accounts.
+ Use AWS Control Tower to easily and securely share your resources with your AWS accounts.
+ Consolidate all of the company's accounts using AWS Organizations.
+ Consolidate all of the company's accounts using AWS ParallelCluster.

<details close>
<summary>Answer</summary>
a,d
</details>

<br>

---

A tech company has a CRM application hosted on an Auto Scaling group of On-Demand EC2 instances. The application is extensively used during office hours from 9 in the morning till 5 in the afternoon. Their users are complaining that the performance of the application is slow during the start of the day but then works normally after a couple of hours. 

Which of the following can be done to ensure that the application works properly at the beginning of the day?
+ Configure a Dynamic scaling policy for the Auto Scaling group to launch new instances based on the CPU utilization.
+ Configure a Dynamic scaling policy for the Auto Scaling group to launch new instances based on the Memory utilization.
+ Configure a Scheduled scaling policy for the Auto Scaling group to launch new instances before the start of the day.
+ Set up an Application Load Balancer (ALB) to your architecture to ensure that the traffic is properly distributed on the instances.

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A financial application is composed of an Auto Scaling group of EC2 instances, an Application Load Balancer, and a MySQL RDS instance in a Multi-AZ Deployments configuration. To protect the confidential data of your customers, you have to ensure that your RDS database can only be accessed using the profile credentials specific to your EC2 instances via an authentication token.

As the Solutions Architect of the company, which of the following should you do to meet the above requirement?
+ Enable the IAM DB Authentication.
+ Configure SSL in your application to encrypt the database connection to RDS.
+ Create an IAM Role and assign it to your EC2 instances which will grant exclusive access to your RDS instance.
+ Use a combination of IAM and STS to restrict access to your RDS instance via a temporary token.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

The company that you are working for has a highly available architecture consisting of an elastic load balancer and several EC2 instances configured with auto-scaling in three Availability Zones. You want to monitor your EC2 instances based on a particular metric, which is not readily available in CloudWatch.   

Which of the following is a custom metric in CloudWatch which you have to manually set up?
+ Memory Utilization of an EC2 instance
+ CPU Utilization of an EC2 instance
+ Disk Reads activity of an EC2 instance
+ Network packets out of an EC2 instance

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A software development company is using serverless computing with AWS Lambda to build and run applications without having to set up or manage servers. They have a Lambda function that connects to a MongoDB Atlas, which is a popular Database as a Service (DBaaS) platform and also uses a third party API to fetch certain data for their application. One of the developers was instructed to create the environment variables for the MongoDB database hostname, username, and password as well as the API credentials that will be used by the Lambda function for DEV, SIT, UAT, and PROD environments.

Considering that the Lambda function is storing sensitive database and API credentials, how can this information be secured to prevent other developers in the team, or anyone, from seeing these credentials in plain text? Select the best option that provides maximum security.

+ There is no need to do anything because, by default, AWS Lambda already encrypts the environment variables using the AWS Key Management Service.
+ Enable SSL encryption that leverages on AWS CloudHSM to store and encrypt the sensitive information.
+ AWS Lambda does not provide encryption for the environment variables. Deploy your code to an EC2 instance instead.
+ Create a new KMS key and use it to enable encryption helpers that leverage on AWS Key Management Service to store and encrypt the sensitive information.


<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A retail website has intermittent, sporadic, and unpredictable transactional workloads throughout the day that are hard to predict. The website is currently hosted on-premises and is slated to be migrated to AWS. A new relational database is needed that autoscales capacity to meet the needs of the application's peak load and scales back down when the surge of activity is over.

Which of the following option is the MOST cost-effective and suitable database setup in this scenario?
+ Launch an Amazon Aurora Serverless DB cluster then set the minimum and maximum capacity for the cluster.
+ Launch an Amazon Aurora Provisioned DB cluster with burstable performance DB instance class types.
+ Launch a DynamoDB Global table with Auto Scaling enabled.
+ Launch an Amazon Redshift data warehouse cluster with Concurrency Scaling.

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

There was an incident in your production environment where the user data stored in the S3 bucket has been accidentally deleted by one of the Junior DevOps Engineers. The issue was escalated to your manager and after a few days, you were instructed to improve the security and protection of your AWS resources.   

What combination of the following options will protect the S3 objects in your bucket from both accidental deletion and overwriting? (Select TWO.)
+ Enable Versioning
+ Provide access to S3 data strictly through pre-signed URL only
+ Disallow S3 Delete using an IAM bucket policy
+ Enable Amazon S3 Intelligence-Tiering
+ Enable Multi-Factor Authentication Delete

<details close>
<summary>Answer</summary>
a,e
</details>

<br>

---

A company is using Amazon S3 to store frequently accessed data. When an object is created or deleted, the S3 bucket will send an event notification to the Amazon SQS queue. A solutions architect needs to create a solution that will notify the development and operations team about the created or deleted objects.

Which of the following would satisfy this requirement?
+ Set up another Amazon SQS queue for the other team. Grant Amazon S3 permission to send a notification to the second SQS queue.
+ Create a new Amazon SNS FIFO topic for the other team. Grant Amazon S3 permission to send the notification to the second SNS topic
+ Set up an Amazon SNS topic and configure two Amazon SQS queues to poll the SNS topic. Grant Amazon S3 permission to send notifications to Amazon SNS and update the bucket to use the new SNS topic.
+ Create an Amazon SNS topic and configure two Amazon SQS queues to subscribe to the topic. Grant Amazon S3 permission to send notifications to Amazon SNS and update the bucket to use the new SNS topic.

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A government agency plans to store confidential tax documents on AWS. Due to the sensitive information in the files, the Solutions Architect must restrict the data access requests made to the storage solution to a specific Amazon VPC only. The solution should also prevent the files from being deleted or overwritten to meet the regulatory requirement of having a write-once-read-many (WORM) storage model.

Which combination of the following options should the Architect implement? (Select TWO.)

+ Set up a new Amazon S3 bucket to store the tax documents and integrate it with AWS Network Firewall. Configure the Network Firewall to only accept data access requests from a specific Amazon VPC.
+ Configure an Amazon S3 Access Point for the S3 bucket to restrict data access to a particular Amazon VPC only.
+ Create a new Amazon S3 bucket with the S3 Object Lock feature enabled. Store the documents in the bucket and set the Legal Hold option for object retention.
+ Store the tax documents in the Amazon S3 Glacier Instant Retrieval storage class to restrict fast data retrieval to a particular Amazon VPC of your choice.
+ Enable Object Lock but disable Object Versioning on the new Amazon S3 bucket to comply with the write-once-read-many (WORM) storage model requirement.

<details close>
<summary>Answer</summary>
b,c
</details>

<br>

<details close>
<summary>Note</summary>
Network Firewall apply on VPC not to an S3 bucket
</details>

<br>

---

A pharmaceutical company has resources hosted on both their on-premises network and in AWS cloud. They want all of their Software Architects to access resources on both environments using their on-premises credentials, which is stored in Active Directory.

In this scenario, which of the following can be used to fulfill this requirement?

+ Set up SAML 2.0-Based Federation by using a Web Identity Federation.
+ Set up SAML 2.0-Based Federation by using a Microsoft Active Directory Federation Service (AD FS).
+ Use IAM users
+ Use Amazon VPC

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A telecommunications company is planning to give AWS Console access to developers. Company policy mandates the use of identity federation and role-based access control. Currently, the roles are already assigned using groups in the corporate Active Directory.

In this scenario, what combination of the following services can provide developers access to the AWS console? (Select TWO.)
+ AWS Directory Service AD Connector
+ AWS Directory Service Simple AD
+ IAM Groups
+ IAM Roles
+ Lambda


<details close>
<summary>Answer</summary>
a,d
</details>

<br>

---

An application that records weather data every minute is deployed in a fleet of Spot EC2 instances and uses a MySQL RDS database instance. Currently, there is only one RDS instance running in one Availability Zone. You plan to improve the database to ensure high availability by synchronous data replication to another RDS instance.

Which of the following performs synchronous data replication in RDS?


+ RDS DB instance running as a Multi-AZ deployment
+ RDS Read Replica
+ DynamoDB Read Replica
+ CloudFront running as a Multi-AZ deployment

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A startup is using Amazon RDS to store data from a web application. Most of the time, the application has low user activity but it receives bursts of traffic within seconds whenever there is a new product announcement. The Solutions Architect needs to create a solution that will allow users around the globe to access the data using an API.

What should the Solutions Architect do meet the above requirement?

+ Create an API using Amazon API Gateway and use the Amazon ECS cluster with Service Auto Scaling to handle the bursts of traffic in seconds.
+ Create an API using Amazon API Gateway and use Amazon Elastic Beanstalk with Auto Scaling to handle the bursts of traffic in seconds.
+ Create an API using Amazon API Gateway and use AWS Lambda to handle the bursts of traffic in seconds.
+ Create an API using Amazon API Gateway and use an Auto Scaling group of Amazon EC2 instances to handle the bursts of traffic in seconds.

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
Lambda can scale faster than the regular Auto Scaling feature of Amazon EC2, Amazon Elastic Beanstalk, or Amazon ECS. This is because AWS Lambda is more lightweight than other computing services. Under the hood, Lambda can run your code to thousands of available AWS-managed EC2 instances (that could already be running) within seconds to accommodate traffic. This is faster than the Auto Scaling process of launching new EC2 instances that could take a few minutes or so. An alternative is to overprovision your compute capacity but that will incur significant costs. The best option to implement given the requirements is a combination of AWS Lambda and Amazon API Gateway.
</details>

<br>

---

An online cryptocurrency exchange platform is hosted in AWS which uses ECS Cluster and RDS in Multi-AZ Deployments configuration. The application is heavily using the RDS instance to process complex read and write database operations. To maintain the reliability, availability, and performance of your systems, you have to closely monitor how the different processes or threads on a DB instance use the CPU, including the percentage of the CPU bandwidth and total memory consumed by each process.   

Which of the following is the most suitable solution to properly monitor your database?

+ Use Amazon CloudWatch to monitor the CPU Utilization of your database.
+ Create a script that collects and publishes custom metrics to CloudWatch, which tracks the real-time CPU Utilization of the RDS instance, and then set up a custom CloudWatch dashboard to view the metrics.
+ Enable Enhanced Monitoring in RDS.
+ Check the `CPU%` and `MEM%` metrics which are readily available in the Amazon RDS console that shows the percentage of the CPU bandwidth and total memory consumed by each database process of your RDS instance.

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
Take note that there are certain differences between CloudWatch and Enhanced Monitoring Metrics. CloudWatch gathers metrics about CPU utilization from the hypervisor for a DB instance, and Enhanced Monitoring gathers its metrics from an agent on the instance. As a result, you might find differences between the measurements, because the hypervisor layer performs a small amount of work. Hence, enabling Enhanced Monitoring in RDS is the correct answer in this specific scenario.
</details>

<br>

---

A Solutions Architect needs to make sure that the On-Demand EC2 instance can only be accessed from this IP address (110.238.98.71) via an SSH connection. Which configuration below will satisfy this requirement?
+ Security Group Inbound Rule: Protocol – TCP. Port Range – 22, Source 110.238.98.71/32
+ Security Group Inbound Rule: Protocol – UDP, Port Range – 22, Source 110.238.98.71/32
+ Security Group Inbound Rule: Protocol – TCP. Port Range – 22, Source 110.238.98.71/0
+ Security Group Inbound Rule: Protocol – UDP, Port Range – 22, Source 110.238.98.71/0

<details close>
<summary>Answer</summary>
a
</details>

Take note that the SSH protocol uses TCP and port 22.

---

A tech company that you are working for has undertaken a Total Cost Of Ownership (TCO) analysis evaluating the use of Amazon S3 versus acquiring more storage hardware. The result was that all 1200 employees would be granted access to use Amazon S3 for the storage of their personal documents.

Which of the following will you need to consider so you can set up a solution that incorporates a single sign-on feature from your corporate AD or LDAP directory and also restricts access for each individual user to a designated user folder in an S3 bucket? (Select TWO.)

+ Use 3rd party Single Sign-On solutions such as Atlassian Crowd, OKTA, OneLogin and many others.
+ Set up a Federation proxy or an Identity provider, and use AWS Security Token Service to generate temporary tokens.
+ Map each individual user to a designated user folder in S3 using Amazon WorkDocs to access their personal documents.
+ Configure an IAM role and an IAM Policy to access the bucket.
+ Set up a matching IAM user for each of the 1200 users in your corporate directory that needs access to a folder in the S3 bucket.

<details close>
<summary>Answer</summary>
b,d
</details>

---

An application hosted in EC2 consumes messages from an SQS queue and is integrated with SNS to send out an email to you once the process is complete. The Operations team received 5 orders but after a few hours, they saw 20 email notifications in their inbox.

Which of the following could be the possible culprit for this issue?
+ The web application is set for long polling so the messages are being sent twice.
+ The web application is not deleting the messages in the SQS queue after it has processed them.
+ The web application is set to short polling so some messages are not being picked up
+ The web application does not have permission to consume messages in the SQS queue. 

<details close>
<summary>Answer</summary>
b
</details>

---

A company is using AWS Fargate to run a batch job whenever an object is uploaded to an Amazon S3 bucket. The minimum ECS task count is initially set to 1 to save on costs and should only be increased based on new objects uploaded to the S3 bucket.

Which is the most suitable option to implement with the LEAST amount of effort?
+ Set up an Amazon EventBridge rule to detect S3 object PUT operations and set the target to a Lambda function that will run the `StartTask` API command
+ Set up an Amazon EventBridge rule to detect S3 object PUT operations and set the target to the ECS cluster to run a new ECS task.
+ Set up an alarm in Amazon CloudWatch to monitor S3 object-level operations that are recorded on CloudTrail. Create an Amazon EventBridge rule that triggers the ECS cluster when new CloudTrail events are detected.
+ Set up an alarm in CloudWatch to monitor S3 object-level operations recorded on CloudTrail. Set two alarm actions to update the ECS task count to scale-out/scale-in depending on the S3 event.

<details close>
<summary>Answer</summary>
b
</details>

---

A Solutions Architect is working for a company which has multiple VPCs in various AWS regions. The Architect is assigned to set up a logging system which will track all of the changes made to their AWS resources in all regions, including the configurations made in IAM, CloudFront, AWS WAF, and Route 53. In order to pass the compliance requirements, the solution must ensure the security, integrity, and durability of the log data. It should also provide an event history of all API calls made in AWS Management Console and AWS CLI.

Which of the following solutions is the best fit for this scenario?
+ Set up a new CloudTrail trail in a new S3 bucket using the AWS CLI and also pass both the `--is-multi-region-trail` and `--include-global-service-events` parameters then encrypt log files using KMS encryption. Apply Multi Factor Authentication (MFA) Delete on the S3 bucket and ensure that only authorized users can access the logs by configuring the bucket policies.
+ Set up a new CloudWatch trail in a new S3 bucket using the AWS CLI and also pass both the `--is-multi-region-trail` and `--include-global-service-events` parameters then encrypt log files using KMS encryption. Apply Multi Factor Authentication (MFA) Delete on the S3 bucket and ensure that only authorized users can access the logs by configuring the bucket policies.
+ Set up a new CloudWatch trail in a new S3 bucket using the CloudTrail console and also pass the `--is-multi-region-trail` parameter then encrypt log files using KMS encryption. Apply Multi Factor Authentication (MFA) Delete on the S3 bucket and ensure that only authorized users can access the logs by configuring the bucket policies.
+ Set up a new CloudTrail trail in a new S3 bucket using the AWS CLI and also pass both the `--is-multi-region-trail` and `--no-include-global-service-events` parameters then encrypt log files using KMS encryption. Apply Multi Factor Authentication (MFA) Delete on the S3 bucket and ensure that only authorized users can access the logs by configuring the bucket policies.

<details close>
<summary>Answer</summary>
a
</details>

---

A content management system (CMS) is hosted on a fleet of auto-scaled, On-Demand EC2 instances that use Amazon Aurora as its database. Currently, the system stores the file documents that the users upload in one of the attached EBS Volumes. Your manager noticed that the system performance is quite slow and he has instructed you to improve the architecture of the system.

In this scenario, what will you do to implement a scalable, high-available POSIX-compliant shared file system?

+ Create an S3 bucket and use this as the storage for the CMS
+ Use EFS
+ Upgrading your existing EBS volumes to Provisioned IOPS SSD Volumes
+ Use ElastiCache

<details close>
<summary>Answer</summary>
b
</details>

---

A company needs to design an online analytics application that uses Redshift Cluster for its data warehouse. Which of the following services allows them to monitor all API calls in Redshift instance and can also provide secured data for auditing and compliance purposes?


+ AWS CloudTrail
+ Amazon CloudWatch
+ AWS X-Ray
+ Amazon Redshift Spectrum

<details close>
<summary>Answer</summary>
a
</details>

---

A popular social network is hosted in AWS and is using a DynamoDB table as its database. There is a requirement to implement a 'follow' feature where users can subscribe to certain updates made by a particular user and be notified via email. Which of the following is the most suitable solution that you should implement to meet the requirement?
+ Using the Kinesis Client Library (KCL), write an application that leverages on DynamoDB Streams Kinesis Adapter that will fetch data from the DynamoDB Streams endpoint. When there are updates made by a particular user, notify the subscribers via email using SNS.
+ Create a Lambda function that uses DynamoDB Streams Kinesis Adapter which will fetch data from the DynamoDB Streams endpoint. Set up an SNS Topic that will notify the subscribers via email when there is an update made by a particular user.
+ Set up a DAX cluster to access the source DynamoDB table. Create a new DynamoDB trigger and a Lambda function. For every update made in the user data, the trigger will send data to the Lambda function which will then notify the subscribers via email using SNS.
+ Enable DynamoDB Stream and create an AWS Lambda trigger, as well as the IAM role which contains all of the permissions that the Lambda function will need at runtime. The data from the stream record will be processed by the Lambda function which will then publish a message to SNS Topic that will notify the subscribers via email.

<details close>
<summary>Answer</summary>
d
</details>

---

A media company has an Amazon ECS Cluster, which uses the Fargate launch type, to host its news website. The application data are all stored in Amazon Keyspaces (for Apache Cassandra) with data-at-rest encryption enabled. The database credentials should be supplied using environment variables, to comply with strict security compliance. As the Solutions Architect, you have to ensure that the credentials are secure and that they cannot be viewed in plaintext on the cluster itself.

Which of the following is the most suitable solution in this scenario that you can implement with minimal effort?
+ In the ECS task definition file of the ECS Cluster, store the database credentials to Amazon ECS Anywhere to centrally manage these sensitive data and securely transmit it to only those containers that need access to it. Allocate an IAM Role to the cluster to ensure that the passwords are only accessible by the ECS service tasks. Run the AWS IAM Access Analyzer to verify that the credentials can’t be viewed in plaintext.
+ Store the database credentials in the ECS task definition file of the ECS Cluster and encrypt it with KMS. Store the task definition JSON file in Amazon Quantum Ledger Database (Amazon QLDB). Create an IAM role to the ECS task definition script that allows access to the Amazon QLDB and then pass the `--cli-input-json` parameter when calling the ECS `register-task-definition` action. Reference the task definition JSON file in the Amazon QLDB which contains the database credentials.
+ Use the AWS Secrets Manager to store the database credentials and then encrypt them using AWS Certificate Manager (ACM). Create a resource-based policy for your Amazon ECS task execution role (`taskRoleArn`) and reference it with your task definition which allows access to both ACM and AWS Secrets Manager. Within your container definition, specify secrets with the name of the environment variable to set in the container and the full ARN of the Secrets Manager secret which contains the sensitive data, to present to the container.
+ Use the AWS Systems Manager Parameter Store to keep the database credentials and then encrypt them using AWS KMS. Create an IAM Role for your Amazon ECS task execution role (`taskRoleArn`) and reference it with your task definition, which allows access to both KMS and the Parameter Store. Within your container definition, specify secrets with the name of the environment variable to set in the container and the full ARN of the Systems Manager Parameter Store parameter containing the sensitive data to present to the container.


<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
Although the use of Secrets Manager in securing sensitive data in ECS is valid, Amazon ECS doesn't support resource-based policies. An example of a resource-based policy is the S3 bucket policy. An ECS task assumes an execution role (IAM role) to be able to call other AWS services like AWS Secrets Manager on your behalf.
</details>

---


A cryptocurrency trading platform is using an API built in AWS Lambda and API Gateway. Due to the recent news and rumors about the upcoming price surge of Bitcoin, Ethereum and other cryptocurrencies, it is expected that the trading platform would have a significant increase in site visitors and new users in the coming days ahead.

In this scenario, how can you protect the backend systems of the platform from traffic spikes?

+ Switch from using AWS Lambda and API Gateway to a more scalable and highly available architecture using EC2 instances, ELB, and Auto Scaling.
+ Enable throttling limits and result caching in API Gateway.
+ Use CloudFront in front of the API Gateway to act as a cache.
+ Move the Lambda function in a VPC.

<details close>
<summary>Answer</summary>
b
</details>

---

A business has recently migrated its applications to AWS. The audit team must be able to assess whether the services the company is using meet common security and regulatory standards. A solutions architect needs to provide the team with a report of all compliance-related documents for their account.

Which action should a solutions architect consider?

+ Run an Amazon Inspector assessment job to download all of the AWS compliance-related information.
+ Use AWS Artifact to view the security reports as well as other AWS compliance-related information.
+ Run an Amazon Macie job to view the Service Organization Control (SOC), Payment Card Industry (PCI), and other compliance reports from AWS Certificate Manager (ACM).
+ View all of the AWS security compliance reports from AWS Security Hub.

<details close>
<summary>Answer</summary>
b
</details>

---

A company has a cloud architecture that is composed of Linux and Windows EC2 instances that process high volumes of financial data 24 hours a day, 7 days a week. To ensure high availability of the systems, the Solutions Architect needs to create a solution that allows them to monitor the memory and disk utilization metrics of all the instances.

Which of the following is the most suitable monitoring solution to implement?
+ Use the default CloudWatch configuration to EC2 instances where the memory and disk utilization metrics are already available. Install the AWS Systems Manager (SSM) Agent to all the EC2 instances.
+ Install the CloudWatch agent to all the EC2 instances that gathers the memory and disk utilization data. View the custom metrics in the Amazon CloudWatch console.
+ Enable the Enhanced Monitoring option in EC2 and install CloudWatch agent to all the EC2 instances to be able to view the memory and disk utilization in the CloudWatch dashboard.
+ Use Amazon Inspector and install the Inspector agent to all EC2 instances.

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
Enhanced monitoring is for RDS instances
</details>

---

A newly hired Solutions Architect is assigned to manage a set of CloudFormation templates that are used in the company's cloud architecture in AWS. The Architect accessed the templates and tried to analyze the configured IAM policy for an S3 bucket.
```json
{ 
 "Version": "2012-10-17", 
 "Statement": [ 
  { 
   "Effect": "Allow", 
   "Action": [ 
    "s3:Get*", 
    "s3:List*" 
   ], 
   "Resource": "*" 
  }, 
  { 
   "Effect": "Allow", 
   "Action": "s3:PutObject", 
   "Resource": "arn:aws:s3:::boracay/*" 
  } 
 ] 
}
```

What does the above IAM policy allow? (Select THREE.)
+ An IAM user with this IAM policy is allowed to read objects from all S3 buckets owned by the account.
+ An IAM user with this IAM policy is allowed to write objects into the `boracay` S3 bucket
+ An IAM user with this IAM policy is allowed to change access rights for the `boracay`  S3 bucket.
+ An IAM user with this IAM policy is allowed to read objects in the `boracay`  S3 bucket but not allowed to list the objects in the bucket.
+ An IAM user with this IAM policy is allowed to read objects from the `boracay` S3 bucket.
+ An IAM user with this IAM policy is allowed to read and delete objects from the `boracay`  S3 bucket.

<details close>
<summary>Answer</summary>
a,b,e
</details>

---

A company has a web application that uses Amazon CloudFront to distribute its images, videos, and other static contents stored in its S3 bucket to its users around the world. The company has recently introduced a new member-only access feature to some of its high-quality media files. There is a requirement to provide access to multiple private media files only to their paying subscribers without having to change their current URLs.

Which of the following is the most suitable solution that you should implement to satisfy this requirement?

+ Configure your CloudFront distribution to use Match Viewer as its Origin Protocol Policy which will automatically match the user request. This will allow access to the private content if the request is a paying member and deny it if it is not a member.
+ Create a Signed URL with a custom policy which only allows the members to see the private files.
+ Configure your CloudFront distribution to use Field-Level Encryption to protect your private data and only allow access to members.
+ Use Signed Cookies to control who can access the private files in your CloudFront distribution by modifying your application to determine whether a user should have access to your content. For members, send the required `Set-Cookie`  headers to the viewer which will unlock the content only to them.

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
Use signed URLs for the following cases:

- You want to use an RTMP distribution. Signed cookies aren't supported for RTMP distributions.

- You want to restrict access to individual files, for example, an installation download for your application.

- Your users are using a client (for example, a custom HTTP client) that doesn't support cookies.

Use signed cookies for the following cases:

- You want to provide access to multiple restricted files, for example, all of the files for a video in HLS format or all of the files in the subscribers' area of a website.

- You don't want to change your current URLs.
</details>

---

A suite of web applications is hosted in an Auto Scaling group of EC2 instances across three Availability Zones and is configured with default settings. There is an Application Load Balancer that forwards the request to the respective target group on the URL path. The scale-in policy has been triggered due to the low number of incoming traffic to the application.

Which EC2 instance will be the first one to be terminated by your Auto Scaling group?
+ The EC2 instance which has the least number of user sessions
+ The EC2 instance which has been running for the longest time
+ The EC2 instance launched from the oldest launch configuration
+ The instance will be randomly selected by the Auto Scaling group

<details close>
<summary>Answer</summary>
c
</details>

---

A travel photo sharing website is using Amazon S3 to serve high-quality photos to visitors of your website. After a few days, you found out that there are other travel websites linking and using your photos. This resulted in financial losses for your business.

What is the MOST effective method to mitigate this issue?
+ Configure your S3 bucket to remove public read access and use pre-signed URLs with expiry dates.
+ Use CloudFront distributions for your photos.
+ Block the IP addresses of the offending websites using NACL.
+ Store and privately serve the high-quality photos on Amazon WorkDocs instead.

<details close>
<summary>Answer</summary>
a
</details>

---

A Forex trading platform, which frequently processes and stores global financial data every minute, is hosted in your on-premises data center and uses an Oracle database. Due to a recent cooling problem in their data center, the company urgently needs to migrate their infrastructure to AWS to improve the performance of their applications. As the Solutions Architect, you are responsible in ensuring that the database is properly migrated and should remain available in case of database server failure in the future. 

Which of the following is the most suitable solution to meet the requirement?
+ Launch an Oracle database instance in RDS with Recovery Manager (RMAN) enabled.
+ Launch an Oracle Real Application Clusters (RAC) in RDS.
+ Create an Oracle database in RDS with Multi-AZ deployments.
+ Convert the database schema using the AWS Schema Conversion Tool and AWS Database Migration Service. Migrate the Oracle database to a non-cluster Amazon Aurora with a single instance.

<details close>
<summary>Answer</summary>
c
</details>

---

A company is using a combination of API Gateway and Lambda for the web services of the online web portal that is being accessed by hundreds of thousands of clients each day. They will be announcing a new revolutionary product and it is expected that the web portal will receive a massive number of visitors all around the globe.

How can you protect the backend systems and applications from traffic spikes?

+ Use throttling limits in API Gateway
+ API Gateway will automatically scale and handle massive traffic spikes so you do not have to do anything.
+ Manually upgrade the EC2 instances being used by API Gateway
+ Deploy Multi-AZ in API Gateway with Read Replica

<details close>
<summary>Answer</summary>
a
</details>

---

An online shopping platform is hosted on an Auto Scaling group of Spot EC2 instances and uses Amazon Aurora PostgreSQL as its database. There is a requirement to optimize your database workloads in your cluster where you have to direct the write operations of the production traffic to your high-capacity instances and point the reporting queries sent by your internal staff to the low-capacity instances.

Which is the most suitable configuration for your application as well as your Aurora database cluster to achieve this requirement?

+ Configure your application to use the reader endpoint for both production traffic and reporting queries, which will enable your Aurora database to automatically perform load-balancing among all the Aurora Replicas.
+ In your application, use the instance endpoint of your Aurora database to handle the incoming production traffic and use the cluster endpoint to handle reporting queries.
+ Create a custom endpoint in Aurora based on the specified criteria for the production traffic and another custom endpoint to handle the reporting queries.
+ Do nothing since by default, Aurora will automatically direct the production traffic to your high-capacity instances and the reporting queries to your low-capacity instances.

<details close>
<summary>Answer</summary>
c
</details>

---

A company has 3 DevOps engineers that are handling its software development and infrastructure management processes. One of the engineers accidentally deleted a file hosted in Amazon S3 which has caused disruption of service.

What can the DevOps engineers do to prevent this from happening again?

+ Use S3 Infrequently Accessed storage to store the data.
+ Enable S3 Versioning and Multi-Factor Authentication Delete on the bucket.
+ Set up a signed URL for all users.
+ Create an IAM bucket policy that disables delete operation.

<details close>
<summary>Answer</summary>
b
</details>

---

There are a lot of outages in the Availability Zone of your RDS database instance to the point that you have lost access to the database. What could you do to prevent losing access to your database in case that this event happens again?

+ Make a snapshot of the database
+ Enabled Multi-AZ failover 
+ Increase the database instance size
+ Create a read replica

<details close>
<summary>Answer</summary>
b
</details>

---

A popular social media website uses a CloudFront web distribution to serve their static contents to their millions of users around the globe. They are receiving a number of complaints recently that their users take a lot of time to log into their website. There are also occasions when their users are getting HTTP 504 errors. You are instructed by your manager to significantly reduce the user's login time to further optimize the system.

Which of the following options should you use together to set up a cost-effective solution that can improve your application's performance? (Select TWO.)
+ Customize the content that the CloudFront web distribution delivers to your users using Lambda@Edge, which allows your Lambda functions to execute the authentication process in AWS locations closer to the users.
+ Use multiple and geographically disperse VPCs to various AWS regions then create a transit VPC to connect all of your resources. In order to handle the requests faster, set up Lambda functions in each region using the AWS Serverless Application Model (SAM) service.
+ Configure your origin to add a `Cache-Control max-age`  directive to your objects, and specify the longest practical value for `max-age`  to increase the cache hit ratio of your CloudFront distribution.
+ Deploy your application to multiple AWS regions to accommodate your users around the world. Set up a Route 53 record with latency routing policy to route incoming traffic to the region that provides the best latency to the user.
+ Set up an origin failover by creating an origin group with two origins. Specify one as the primary origin and the other as the second origin which CloudFront automatically switches to when the primary origin returns specific HTTP status code failure responses.

<details close>
<summary>Answer</summary>
a,e
</details>

---

A company has a hybrid cloud architecture that connects their on-premises data center and cloud infrastructure in AWS. They require a durable storage backup for their corporate documents stored on-premises and a local cache that provides low latency access to their recently accessed data to reduce data egress charges. The documents must be stored to and retrieved from AWS via the Server Message Block (SMB) protocol. These files must immediately be accessible within minutes for six months and archived for another decade to meet the data compliance.

Which of the following is the best and most cost-effective approach to implement in this scenario?

+ Launch a new file gateway that connects to your on-premises data center using AWS Storage Gateway. Upload the documents to the file gateway and set up a lifecycle policy to move the data into Glacier for data archival.
+ Launch a new tape gateway that connects to your on-premises data center using AWS Storage Gateway. Upload the documents to the tape gateway and set up a lifecycle policy to move the data into Glacier for archival.
+ Establish a Direct Connect connection to integrate your on-premises network to your VPC. Upload the documents on Amazon EBS Volumes and use a lifecycle policy to automatically move the EBS snapshots to an S3 bucket, and then later to Glacier for archival.
+ Use AWS Snowmobile to migrate all of the files from the on-premises network. Upload the documents to an S3 bucket and set up a lifecycle policy to move the data into Glacier for archival.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
File Gateway: support SMB protocol.
Volume Gateway: support iSCSI, on-prem, primary data, cloud : async backups
Cached Gateway: on-prem, cached most freq accessed files, cloud: primary data
</details>

---

A company conducted a surprise IT audit on all of the AWS resources being used in the production environment. During the audit activities, it was noted that you are using a combination of Standard and Convertible Reserved EC2 instances in your applications.

Which of the following are the characteristics and benefits of using these two types of Reserved EC2 instances? (Select TWO.)
+ Unused Convertible Reserved Instances can later be sold at the Reserved Instance Marketplace.
+ It can enable you to reserve capacity for your Amazon EC2 instances in multiple Availability Zones and multiple AWS Regions for any duration.
+ Unused Standard Reserved Instances can later be sold at the Reserved Instance Marketplace.
+ It runs in a VPC on hardware that's dedicated to a single customer.
+ Convertible Reserved Instances allow you to exchange for another convertible reserved instance of a different instance family.

<details close>
<summary>Answer</summary>
c,e
</details>

---

A Docker application, which is running on an Amazon ECS cluster behind a load balancer, is heavily using DynamoDB. You are instructed to improve the database performance by distributing the workload evenly and using the provisioned throughput efficiently.   

Which of the following would you consider to implement for your DynamoDB table?
+ Reduce the number of partition keys in the DynamoDB table.
+ Use partition keys with high-cardinality attributes, which have a large number of distinct values for each item.
+ Use partition keys with low-cardinality attributes, which have a few number of distinct values for each item.
+ Avoid using a composite primary key, which is composed of a partition key and a sort key.

<details close>
<summary>Answer</summary>
b
</details>

---

A company is designing a banking portal that uses Amazon ElastiCache for Redis as its distributed session management component. Since the other Cloud Engineers in your department have access to your ElastiCache cluster, you have to secure the session data in the portal by requiring them to enter a password before they are granted permission to execute Redis commands.

As the Solutions Architect, which of the following should you do to meet the above requirement?

+ Set up an IAM Policy and MFA which requires the Cloud Engineers to enter their IAM credentials and token before they can access the ElastiCache cluster.
+ Set up a Redis replication group and enable the `AtRestEncryptionEnabled`  parameter.
+ Authenticate the users using Redis AUTH by creating a new Redis Cluster with both the `--transit-encryption-enabled` and `--auth-token` parameters enabled.
+ Enable the in-transit encryption for Redis replication groups.

<details close>
<summary>Answer</summary>
c
</details>

---

A Solutions Architect identified a series of DDoS attacks while monitoring the VPC. The Architect needs to fortify the current cloud infrastructure to protect the data of the clients.

Which of the following is the most suitable solution to mitigate these kinds of attacks?
+ Use AWS Shield Advanced to detect and mitigate DDoS attacks.
+ Using the AWS Firewall Manager, set up a security layer that will prevent SYN floods, UDP reflection attacks, and other DDoS attacks.
+ Set up a web application firewall using AWS WAF to filter, monitor, and block HTTP traffic.
+ A combination of Security Groups and Network Access Control Lists to only allow authorized traffic to access your VPC.

<details close>
<summary>Answer</summary>
a
</details>

---

An AI-powered Forex trading application consumes thousands of data sets to train its machine learning model. The application’s workload requires a high-performance, parallel hot storage to process the training datasets concurrently. It also needs cost-effective cold storage to archive those datasets that yield low profit.

Which of the following Amazon storage services should the developer use?
+ Use Amazon FSx For Lustre and Amazon EBS Provisioned IOPS SSD (io1) volumes for hot and cold storage respectively.
+ Use Amazon FSx For Lustre and Amazon S3 for hot and cold storage respectively.
+ Use Amazon Elastic File System and Amazon S3 for hot and cold storage respectively.
+ Use Amazon FSx For Windows File Server and Amazon S3 for hot and cold storage respectively.

<details close>
<summary>Answer</summary>
b
</details>


<details close>
<summary>Note</summary>
Amazon FSx For Lustre is a high-performance file system for fast processing of workloads. Lustre is a popular open-source parallel file system which stores data across multiple network file servers to maximize performance and reduce bottlenecks.
</details>

---

An application consists of multiple EC2 instances in private subnets in different availability zones. The application uses a single NAT Gateway for downloading software patches from the Internet to the instances. There is a requirement to protect the application from a single point of failure when the NAT Gateway encounters a failure or if its availability zone goes down.

How should the Solutions Architect redesign the architecture to be more highly available and cost-effective
+ Create a NAT Gateway in each availability zone. Configure the route table in each private subnet to ensure that instances use the NAT Gateway in the same availability zone
+ Create a NAT Gateway in each availability zone. Configure the route table in each public subnet to ensure that instances use the NAT Gateway in the same availability zone.
+ Create two NAT Gateways in each availability zone. Configure the route table in each public subnet to ensure that instances use the NAT Gateway in the same availability zone.
+ Create three NAT Gateways in each availability zone. Configure the route table in each private subnet to ensure that instances use the NAT Gateway in the same availability zone.


<details close>
<summary>Answer</summary>
a
</details>

---

A company plans to launch an Amazon EC2 instance in a private subnet for its internal corporate web portal. For security purposes, the EC2 instance must send data to Amazon DynamoDB and Amazon S3 via private endpoints that don't pass through the public Internet.

Which of the following can meet the above requirements?
+ Use VPC endpoints to route all access to S3 and DynamoDB via private endpoints.
+ Use AWS VPN CloudHub to route all access to S3 and DynamoDB via private endpoints.
+ Use AWS Transit Gateway to route all access to S3 and DynamoDB via private endpoints.
+ Use AWS Direct Connect to route all access to S3 and DynamoDB via private endpoints.

<details close>
<summary>Answer</summary>
a
</details>

---
An organization needs a persistent block storage volume that will be used for mission-critical workloads. The backup data will be stored in an object storage service and after 30 days, the data will be stored in a data archiving storage service.

What should you do to meet the above requirement?
+ Attach an EBS volume in your EC2 instance. Use Amazon S3 to store your backup data and configure a lifecycle policy to transition your objects to Amazon S3 Glacier.
+ Attach an EBS volume in your EC2 instance. Use Amazon S3 to store your backup data and configure a lifecycle policy to transition your objects to Amazon S3 One Zone-IA.
+ Attach an instance store volume in your existing EC2 instance. Use Amazon S3 to store your backup data and configure a lifecycle policy to transition your objects to Amazon S3 Glacier.
+ Attach an instance store volume in your EC2 instance. Use Amazon S3 to store your backup data and configure a lifecycle policy to transition your objects to Amazon S3 One Zone-IA.

<details close>
<summary>Answer</summary>
a
</details>

---

A Solutions Architect designed a serverless architecture that allows AWS Lambda to access an Amazon DynamoDB table named `tutorialsdojo` in the `US East (N. Virginia)` region. The IAM policy attached to a Lambda function allows it to put and delete items in the table. The policy must be updated to only allow two operations in the `tutorialsdojo` table and prevent other DynamoDB tables from being modified.

Which of the following IAM policies fulfill this requirement and follows the principle of granting the least privilege?
```json
{

 "Version": "2012-10-17",

 "Statement": [

 {

 "Sid": "TutorialsdojoTablePolicy",

 "Effect": "Allow",

 "Action": [

 "dynamodb:PutItem",

 "dynamodb:DeleteItem"

 ],

 "Resource": "arn:aws:dynamodb:us-east-1:120618981206:table/tutorialsdojo"

 }

 ]

}
```
```json
{

 "Version": "2012-10-17",

 "Statement": [

 {

 "Sid": "TutorialsdojoTablePolicy",

 "Effect": "Allow",

 "Action": [

 "dynamodb:PutItem",

 "dynamodb:DeleteItem"

 ],

 "Resource": "arn:aws:dynamodb:us-east-1:120618981206:table/*"

 }

 ]

}

```
```json
{
"Version": "2012-10-17",
"Statement": [
{
"Sid": "TutorialsdojoTablePolicy1",
"Effect": "Allow",
"Action": [
"dynamodb:PutItem",
"dynamodb:DeleteItem"
],
"Resource": "arn:aws:dynamodb:us-east-1:1206189812061898:table/tutorialsdojo"
},
{
"Sid": "TutorialsdojoTablePolicy2",
"Effect": "Allow",
"Action": "dynamodb:*",
"Resource": "arn:aws:dynamodb:us-east-1:1206189812061898:table/tutorialsdojo"
}
]
}

```
```json
{
"Version": "2012-10-17",
"Statement": [
{
"Sid": "TutorialsdojoTablePolicy1",
"Effect": "Allow",
"Action": [
"dynamodb:PutItem",
"dynamodb:DeleteItem"
],
"Resource": "arn:aws:dynamodb:us-east-1:1206189812061898:table/tutorialsdojo"
},
{
"Sid": "TutorialsdojoTablePolicy2",
"Effect": "Deny",
"Action": "dynamodb:*",
"Resource": "arn:aws:dynamodb:us-east-1:1206189812061898:table/*"
}
]
}
```



<details close>
<summary>Answer</summary>
a
</details>

---

A company requires all the data stored in the cloud to be encrypted at rest. To easily integrate this with other AWS services, they must have full control over the encryption of the created keys and also the ability to immediately remove the key material from AWS KMS. The solution should also be able to audit the key usage independently of AWS CloudTrail.

Which of the following options will meet this requirement?
+ Use AWS Key Management Service to create AWS-owned CMKs and store the non-extractable key material in AWS CloudHSM.
+ Use AWS Key Management Service to create a CMK in a custom key store and store the non-extractable key material in Amazon S3.
+ Use AWS Key Management Service to create AWS-managed CMKs and store the non-extractable key material in AWS CloudHSM.
+ Use AWS Key Management Service to create a CMK in a custom key store and store the non-extractable key material in AWS CloudHSM.

<details close>
<summary>Answer</summary>
d
</details>

---

A company wishes to query data that resides in multiple AWS accounts from a central data lake. Each account has its own Amazon S3 bucket that stores data unique to its business function. Users from different accounts must be granted access to the data lake based on their roles.

Which solution will minimize overhead and costs while meeting the required access patterns?
+ Use AWS Lake Formation to consolidate data from multiple accounts into a single account.
+ Use AWS Kinesis Firehose to consolidate data from multiple accounts into a single account.
+ Create a scheduled Lambda function for transferring data from multiple accounts to the S3 buckets of a central account
+ Use AWS Control Tower to centrally manage each account's S3 buckets.

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>

AWS Lake Formation is a service that makes it easy to set up a secure data lake in days. A data lake is a centralized, curated, and secured repository that stores all your data, both in its original form and prepared for analysis. A data lake enables you to break down data silos and combine different types of analytics to gain insights and guide better business decisions.

Amazon S3 forms the storage layer for Lake Formation. If you already use S3, you typically begin by registering existing S3 buckets that contain your data. Lake Formation creates new buckets for the data lake and import data into them. AWS always stores this data in your account, and only you have direct access to it.

</details>

---

A company needs to deploy at least 2 EC2 instances to support the normal workloads of its application and automatically scale up to 6 EC2 instances to handle the peak load. The architecture must be highly available and fault-tolerant as it is processing mission-critical workloads.

As the Solutions Architect of the company, what should you do to meet the above requirement?

+ Create an Auto Scaling group of EC2 instances and set the minimum capacity to 2 and the maximum capacity to 6. Deploy 4 instances in Availability Zone A.
+ Create an Auto Scaling group of EC2 instances and set the minimum capacity to 4 and the maximum capacity to 6. Deploy 2 instances in Availability Zone A and another 2 instances in Availability Zone B.
+ Create an Auto Scaling group of EC2 instances and set the minimum capacity to 2 and the maximum capacity to 6. Use 2 Availability Zones and deploy 1 instance for each AZ.
+ Create an Auto Scaling group of EC2 instances and set the minimum capacity to 2 and the maximum capacity to 4. Deploy 2 instances in Availability Zone A and 2 instances in Availability Zone B.

<details close>
<summary>Answer</summary>
b
</details>

---

A company has a web application that uses Internet Information Services (IIS) for Windows Server. A file share is used to store the application data on the network-attached storage of the company’s on-premises data center. To achieve a highly available system, they plan to migrate the application and file share to AWS.

Which of the following can be used to fulfill this requirement?
+ Migrate the existing file share configuration to AWS Storage Gateway.
+ Migrate the existing file share configuration to Amazon FSx for Windows File Server.
+ Migrate the existing file share configuration to Amazon EFS.
+ Migrate the existing file share configuration to Amazon EBS.

<details close>
<summary>Answer</summary>
b
</details>

Remember that Amazon EFS only supports Linux workloads.

---

A Solutions Architect needs to set up a relational database and come up with a disaster recovery plan to mitigate multi-region failure. The solution requires a Recovery Point Objective (RPO) of 1 second and a Recovery Time Objective (RTO) of less than 1 minute.

Which of the following AWS services can fulfill this requirement?

+ Amazon Quantum Ledger Database (Amazon QLDB)
+ Amazon RDS for PostgreSQL with cross-region read replicas
+ Amazon Timestream
+ Amazon Aurora Global Database

<details close>
<summary>Answer</summary>
d
</details>

---

A company plans to host a web application in an Auto Scaling group of Amazon EC2 instances. The application will be used globally by users to upload and store several types of files. Based on user trends, files that are older than 2 years must be stored in a different storage class. The Solutions Architect of the company needs to create a cost-effective and scalable solution to store the old files yet still provide durability and high availability.

Which of the following approach can be used to fulfill this requirement? (Select TWO.)
+ Use Amazon S3 and create a lifecycle policy that will move the objects to Amazon S3 Glacier after 2 years.
+ Use Amazon EFS and create a lifecycle policy that will move the objects to Amazon EFS-IA after 2 years.
+ Use Amazon S3 and create a lifecycle policy that will move the objects to Amazon S3 Standard-IA after 2 years.
+ Use Amazon EBS volumes to store the files. Configure the Amazon Data Lifecycle Manager (DLM) to schedule snapshots of the volumes after 2 years.
+ Use a RAID 0 storage configuration that stripes multiple Amazon EBS volumes together to store the files. Configure the Amazon Data Lifecycle Manager (DLM) to schedule snapshots of the volumes after 2 years.

<details close>
<summary>Answer</summary>
a,c
</details>

---

A company collects atmospheric data such as temperature, air pressure, and humidity from different countries. Each site location is equipped with various weather instruments and a high-speed Internet connection. The average collected data in each location is around 500 GB and will be analyzed by a weather forecasting application hosted in Northern Virginia. As the Solutions Architect, you need to aggregate all the data in the fastest way.

Which of the following options can satisfy the given requirement?

+ Enable Transfer Acceleration in the destination bucket and upload the collected data using Multipart Upload.
+ Upload the data to the closest S3 bucket. Set up a cross-region replication and copy the objects to the destination bucket.
+ Use AWS Snowball Edge to transfer large amounts of data.
+ Set up a Site-to-Site VPN connection.

<details close>
<summary>Answer</summary>
a
</details>

---

A company plans to migrate its on-premises workload to AWS. The current architecture is composed of a Microsoft SharePoint server that uses a Windows shared file storage. The Solutions Architect needs to use a cloud storage solution that is highly available and can be integrated with Active Directory for access control and authentication.

Which of the following options can satisfy the given requirement?
+ Launch an Amazon EC2 Windows Server to mount a new S3 bucket as a file volume.
+ Create a file system using Amazon EFS and join it to an Active Directory domain.
+ Create a Network File System (NFS) file share using AWS Storage Gateway.
+ Create a file system using Amazon FSx for Windows File Server and join it to an Active Directory domain in AWS.

<details close>
<summary>Answer</summary>
d
</details>

---

A company hosted an e-commerce website on an Auto Scaling group of EC2 instances behind an Application Load Balancer. The Solutions Architect noticed that the website is receiving a large number of illegitimate external requests from multiple systems with IP addresses that constantly change. To resolve the performance issues, the Solutions Architect must implement a solution that would block the illegitimate requests with minimal impact on legitimate traffic.

Which of the following options fulfills this requirement?
+ Create a regular rule in AWS WAF and associate the web ACL to an Application Load Balancer.
+ Create a custom network ACL and associate it with the subnet of the Application Load Balancer to block the offending requests.
+ Create a rate-based rule in AWS WAF and associate the web ACL to an Application Load Balancer.
+ Create a custom rule in the security group of the Application Load Balancer to block the offending requests.

<details close>
<summary>Answer</summary>
c
</details>

---

A car dealership website hosted in Amazon EC2 stores car listings in an Amazon Aurora database managed by Amazon RDS. Once a vehicle has been sold, its data must be removed from the current listings and forwarded to a distributed processing system.

Which of the following options can satisfy the given requirement?
+ Create an RDS event subscription and send the notifications to Amazon SQS. Configure the SQS queues to fan out the event notifications to multiple Amazon SNS topics. Process the data using Lambda functions.
+ Create an RDS event subscription and send the notifications to AWS Lambda. Configure the Lambda function to fan out the event notifications to multiple Amazon SQS queues to update the processing system.
+ Create an RDS event subscription and send the notifications to Amazon SNS. Configure the SNS topic to fan out the event notifications to multiple Amazon SQS queues. Process the data using Lambda functions.
+ Create a native function or a stored procedure that invokes a Lambda function. Configure the Lambda function to send event notifications to an Amazon SQS queue for the processing system to consume.

<details close>
<summary>Answer</summary>
d
</details>

---

A logistics company plans to automate its order management application. The company wants to use SFTP file transfer in uploading business-critical documents. Since the files are confidential, the files need to be highly available and must be encrypted at rest. The files must also be automatically deleted a month after they are created.

Which of the following options should be implemented to meet the company requirements with the least operation overhead?

+ Create an Amazon S3 bucket with encryption enabled. Configure AWS Transfer for SFTP to securely upload files to the S3 bucket. Configure the retention policy on the SFTP server to delete files after a month.
+ Create an Amazon Elastic Filesystem (EFS) file system and enable encryption. Configure AWS Transfer for SFTP to securely upload files to the EFS file system. Apply an EFS lifecycle policy to delete files after 30 days.
+ Provision an Amazon EC2 instance and install the SFTP service. Mount an encrypted EFS file system on the EC2 instance to store the uploaded files. Add a cron job to delete the files older than a month.
+ Create an Amazon S3 bucket with encryption enabled. Launch an AWS Transfer for SFTP endpoint to securely upload files to the S3 bucket. Configure an S3 lifecycle rule to delete files after a month.

<details close>
<summary>Answer</summary>
d
</details>

---

A company uses an Application Load Balancer (ALB) for its public-facing multi-tier web applications. The security team has recently reported that there has been a surge of SQL injection attacks lately, which causes critical data discrepancy issues. The same issue is also encountered by its other web applications in other AWS accounts that are behind an ALB. An immediate solution is required to prevent the remote injection of unauthorized SQL queries and protect their applications hosted across multiple accounts.

As a Solutions Architect, what solution would you recommend?

+ Use AWS Network Firewall to filter web vulnerabilities and brute force attacks using stateful rule groups across all Application Load Balancers on all AWS accounts. Refactor the web application to be less susceptible to SQL injection attacks based on the security assessment.
+ Use AWS WAF and set up a managed rule to block request patterns associated with the exploitation of SQL databases, like SQL injection attacks. Associate it with the Application Load Balancer. Integrate AWS WAF with AWS Firewall Manager to reuse the rules across all the AWS accounts.
+ Use Amazon Macie to scan for vulnerabilities and unintended network exposure. Refactor the web application to be less susceptible to SQL injection attacks based on the security assessment. Utilize the AWS Audit Manager to reuse the security assessment across all AWS accounts.
+ Use Amazon GuardDuty and set up a managed rule to block request patterns associated with the exploitation of SQL databases, like SQL injection attacks. Associate it with the Application Load Balancer and utilize the AWS Security Hub service to reuse the managed rules across all the AWS accounts

<details close>
<summary>Answer</summary>
b
</details>

---

A payment processing company plans to migrate its on-premises application to an Amazon EC2 instance. An IPv6 CIDR block is attached to the company’s Amazon VPC. Strict security policy mandates that the production VPC must only allow outbound communication over IPv6 between the instance and the internet but should prevent the internet from initiating an inbound IPv6 connection. The new architecture should also allow traffic flow inspection and traffic filtering.

What should a solutions architect do to meet these requirements?
+ Launch the EC2 instance to a public subnet and attach an Internet Gateway to the VPC to allow outbound IPv6 communication to the internet. Use Traffic Mirroring to set up the required rules for traffic inspection and traffic filtering.
+ Launch the EC2 instance to a private subnet and attach AWS PrivateLink interface endpoint to the VPC to control outbound IPv6 communication to the internet. Use Amazon GuardDuty to set up the required rules for traffic inspection and traffic filtering.
+ Launch the EC2 instance to a private subnet and attach a NAT Gateway to the VPC to allow outbound IPv6 communication to the internet. Use AWS Firewall Manager to set up the required rules for traffic inspection and traffic filtering.
+ Launch the EC2 instance to a private subnet and attach an Egress-Only Internet Gateway to the VPC to allow outbound IPv6 communication to the internet. Use AWS Network Firewall to set up the required rules for traffic inspection and traffic filtering.

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
NAT is only for IPv4

An egress-only internet gateway is a horizontally scaled, redundant, and highly available VPC component that allows outbound communication over IPv6 from instances in your VPC to the internet and prevents it from initiating an IPv6 connection with your instances.
</details>

---

An online learning company hosts its Microsoft .NET e-Learning application on a Windows Server in its on-premises data center. The application uses an Oracle Database Standard Edition as its backend database.

The company wants a high-performing solution to migrate this workload to the AWS cloud to take advantage of the cloud’s high availability. The migration process should minimize development changes, and the environment should be easier to manage.

Which of the following options should be implemented to meet the company requirements? (Select TWO.)
+ Migrate the Oracle database to Amazon RDS for Oracle in a Multi-AZ deployment by using AWS Database Migration Service (AWS DMS).
+ Refactor the application to .NET Core and run it as a serverless container service using Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate.
+ Use AWS Application Migration Service (AWS MGN) to migrate the on-premises Oracle database server to a new Amazon EC2 instance.
+ Rehost the on-premises .NET application to an AWS Elastic Beanstalk Multi-AZ environment which runs in multiple Availability Zones.
+ Provision and replatform the application to Amazon Elastic Container Service (Amazon ECS) with Amazon EC2 worker nodes. Use the Windows Server Amazon Machine Image (AMI) and deploy the .NET application using to the ECS cluster via the Amazon ECS Anywhere service.


<details close>
<summary>Answer</summary>
a,d
</details>

<details close>
<summary>Note</summary>
Refactor the application to .NET Core and run it as a serverless container service using Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate is incorrect. This will take significant changes to the application as you will refactor, or do a code change to, the codebase in order for it to become a serverless container application. Remember that the scenario explicitly mentioned that the migration process should minimize development changes. A better solution is to rehost the on-premises .NET application to an AWS Elastic Beanstalk Multi-AZ environment, which doesn't require any code changes.
</details>














