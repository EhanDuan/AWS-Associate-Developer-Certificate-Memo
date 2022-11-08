# Exam#3 Practice Set

A high-frequency stock trading firm is migrating their messaging queues from self-managed message-oriented middleware systems to Amazon SQS. The development team at the company wants to minimize the costs of using SQS.

As a Developer Associate, which of the following options would you recommend to address the given use-case?
+ Use SQS short polling to retrieve messages from your Amazon SQS queues
+ Use SQS visibility timeout to retrieve messages from your Amazon SQS queues
+ Use SQS long polling to retrieve messages from your Amazon SQS queues
+ Use SQS message timer to retrieve messages from your Amazon SQS queues

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A cybersecurity company is running a serverless backend with several compute-heavy workflows running on Lambda functions. The development team has noticed a performance lag after analyzing the performance metrics for the Lambda functions.

As a Developer Associate, which of the following options would you suggest as the BEST solution to address the compute-heavy workloads?

+ Increase the amount of memory available to the Lambda functions
+ Invoke the Lambda functions asynchronously to process the compute-heavy workflows
+ Use reserved concurrency to account for the compute-heavy workflows
+ Use provisioned concurrency to account for the compute-heavy workflows

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

The development team at a social media company is considering using Amazon ElastiCache to boost the performance of their existing databases.

As a Developer Associate, which of the following use-cases would you recommend as the BEST fit for ElastiCache? (Select two)

+ Use ElastiCache to improve latency and throughput for read-heavy application workloads
+ Use ElastiCache to improve latency and throughput for write-heavy application workloads
+ Use ElastiCache to improve performance of Extract-Transform-Load (ETL) workloads
+ Use ElastiCache to improve performance of compute-intensive workloads
+ Use ElastiCache to run highly complex JOIN queries

<details close>
<summary>Answer</summary>
a,d
</details>

<br>

---

A digital marketing company has its website hosted on an Amazon S3 bucket A. The development team notices that the web fonts that are hosted on another S3 bucket B are not loading on the website.

Which of the following solutions can be used to address this issue?

+ Enable versioning on both the buckets to facilitate correct functioning of the website
+ Update bucket policies on both bucket A and bucket B to allow successful loading of the web fonts on the website
+ Configure CORS on the bucket B that is hosting the web fonts to allow Bucket A origin to make the requests
+ Configure CORS on the bucket A that is hosting the website to allow any origin to respond to requests

<details close>
<summary>Answer</summary>
b
</details>

<br>


<details close>
<summary>Note</summary>
A === request ===> B ,   configure on B.
</details>

<br>

---

As part of their on-boarding, the employees at an IT company need to upload their profile photos in a private S3 bucket. The company wants to build an in-house web application hosted on an EC2 instance that should display the profile photos in a secure way when the employees mark their attendance.

As a Developer Associate, which of the following solutions would you suggest to address this use-case?

+ Save the S3 key for each user's profile photo in a DynamoDB table and use a lambda function to dynamically generate a pre-signed URL. Reference this URL for display via the web application
+ Make the S3 bucket public so that the application can reference the image URL for display
+ Keep each user's profile image encoded in base64 format in a DynamoDB table and reference it from the application for display
+ Keep each user's profile image encoded in base64 format in an RDS table and reference it from the application for display

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A leading financial services company offers data aggregation services for Wall Street trading firms. The company bills its clients based on per unit of clickstream data provided to the clients. As the company operates in a regulated industry, it needs to have the same ordered clickstream data available for auditing within a window of 7 days.

As a Developer Associate, which of the following AWS services do you think provides the ability to run the billing process and auditing process on the given clickstream data in the same order?

+ Amazon SQS
+ AWS Kinesis Data Firehose
+ AWS Kinesis Data Analytics
+ AWS Kinesis Data Streams

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A financial services company wants to ensure that the customer data is always kept encrypted on Amazon S3 but wants a fully managed solution to create, rotate and remove the encryption keys.

As a Developer Associate, which of the following would you recommend to address the given use-case?

+ Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3)
+ Server-Side Encryption with Customer Master Keys (CMKs) Stored in AWS Key Management Service (SSE-KMS)
+ Server-Side Encryption with Customer-Provided Keys (SSE-C)
+ Server-Side Encryption with Secrets Manager

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

An e-commerce company has an order processing workflow with several tasks to be done in parallel as well as decision steps to be evaluated for successful processing of the order. All the tasks are implemented via Lambda functions.

Which of the following is the BEST solution to meet these business requirements?

+ Use AWS Step Functions state machines to orchestrate the workflow
+ Use AWS Glue to orchestrate the workflow
+ Use AWS Batch to orchestrate the workflow
+ Use AWS Step Functions activities to orchestrate the workflow

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

An IT company has migrated to a serverless application stack on the AWS Cloud with the compute layer being implemented via Lambda functions. The engineering managers would like to actively troubleshoot any failures in the Lambda functions.

As a Developer Associate, which of the following solutions would you suggest for this use-case?

+ Use CloudWatch Events to identify and notify any failures in the Lambda code
+ Use CodeCommit to identify and notify any failures in the Lambda code
+ The developers should insert logging statements in the Lambda function code which are then available via CloudWatch logs
+ Use CodeDeploy to identify and notify any failures in the Lambda code

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A HealthCare mobile app uses proprietary Machine Learning algorithms to provide early diagnosis using patient health metrics. To protect this sensitive data, the development team wants to transition to a scalable user management system with log-in/sign-up functionality that also supports Multi-Factor Authentication (MFA)

Which of the following options can be used to implement a solution with the LEAST amount of development effort? (Select two)
+ Use Amazon Cognito for user-management and facilitating the log-in/sign-up process
+ Use Amazon SNS to send Multi-Factor Authentication (MFA) code via SMS to mobile app users
+ Use Lambda functions and DynamoDB to create a custom solution for user management
+ Use Lambda functions and RDS to create a custom solution for user management
+ Use Amazon Cognito to enable Multi-Factor Authentication (MFA) when users log-in

<details close>
<summary>Answer</summary>
a,e
</details>

<br>

---

A telecommunications company that provides internet service for mobile device users maintains over 100 c4.large instances in the us-east-1 region. The EC2 instances run complex algorithms. The manager would like to track CPU utilization of the EC2 instances as frequently as every 10 seconds.

Which of the following represents the BEST solution for the given use-case?

+ Enable EC2 detailed monitoring
+ Create a high-resolution custom metric and push the data using a script triggered every 10 seconds
+ Simply get it from the CloudWatch Metrics
+ Open a support ticket with AWS

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

An application runs on an EC2 instance and processes orders on a nightly basis. This EC2 instance needs to access the orders that are stored in S3.

How would you recommend the EC2 instance access the orders securely?
+ Use EC2 User Data
+ Create an IAM programmatic user and store the access key and secret access key on the EC2 `~/.aws/credentials`  file.
+ Use an IAM role
+ Create an S3 bucket policy that authorises public access

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An IT company has its serverless stack integrated with AWS X-Ray. The developer at the company has noticed a high volume of data going into X-Ray and the AWS monthly usage charges have skyrocketed as a result. The developer has requested changes to mitigate the issue.

As a Developer Associate, which of the following solutions would you recommend to obtain tracing trends while reducing costs with minimal disruption?

+ Enable X-Ray sampling
+ Use Filter Expressions in the X-Ray console
+ Custom configuration for the X-Ray agents
+ Implement a network sampling rule

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company uses Amazon RDS as its database. For improved user experience, it has been decided that a highly reliable fully-managed caching layer has to be configured in front of RDS.

Which of the following is the right choice, keeping in mind that cache content regeneration is a costly activity?

+ Implement Amazon ElastiCache Redis in Cluster Mode
+ Install Redis on an Amazon EC2 instance
+ Implement Amazon ElastiCache Memcached
+ Migrate the database to Amazon Redshift

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

Your company is planning to move away from reserving EC2 instances and would like to adopt a more agile form of serverless architecture.

Which of the folloiwng is the simplest and the least effort way of deploying the Docker containers on this serverless architecture?

+ Amazon Elastic Container Service (Amazon ECS) on EC2
+ Amazon Elastic Kubernetes Service (Amazon EKS) on Fargate
+ Amazon Elastic Container Service (Amazon ECS) on Fargate
+ AWS Elastic Beanstalk

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

Your company hosts a static website on Amazon Simple Storage Service (S3) written in HTML5. The website targets aviation enthusiasts and it has grown a worldwide audience with hundreds of thousands of visitors accessing the website now on a monthly basis. While users in the United States have a great user experience, users from other parts of the world are experiencing slow responses and lag.

Which service can mitigate this issue?

+ Use Amazon ElastiCache for Redis
+ Use Amazon CloudFront
+ Use Amazon S3 Caching
+ Use Amazon S3 Transfer Acceleration

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

Your web application architecture consists of multiple Amazon EC2 instances running behind an Elastic Load Balancer with an Auto Scaling group having the desired capacity of 5 EC2 instances. You would like to integrate AWS CodeDeploy for automating application deployment. The deployment should re-route traffic from your application's original environment to the new environment.

Which of the following options will meet your deployment criteria?

+ Opt for Rolling deployment
+ Opt for Immutable deployment
+ Opt for In-place deployment
+ Opt for Blue/Green deployment

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

Your company uses an Application Load Balancer to route incoming end-user traffic to applications hosted on Amazon EC2 instances. The applications capture incoming request information and store it in the Amazon Relational Database Service (RDS) running on Microsoft SQL Server DB engines.

As part of new compliance rules, you need to capture the client's IP address. How will you achieve this?

+ You can get the Client IP addresses from server access logs
+ Use the header X-Forwarded-For
+ Use the header X-Forwarded-From
+ You can get the Client IP addresses from Elastic Load Balancing logs

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

You have been asked by your Team Lead to enable detailed monitoring of the Amazon EC2 instances your team uses. As a Developer working on AWS CLI, which of the below command will you run?
+ aws ec2 monitor-instances --instance-ids i-1234567890abcdef0
+ aws ec2 run-instances --image-id ami-09092360 --monitoring Enabled=true
+ aws ec2 run-instances --image-id ami-09092360 --monitoring State=enabled
+ aws ec2 monitor-instances --instance-id i-1234567890abcdef0

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>i
ids is due to ability to offer a list of ids
</details>

<br>

---

As a developer, you are looking at creating a custom configuration for Amazon EC2 instances running in an Auto Scaling group. The solution should allow the group to auto-scale based on the metric of 'average RAM usage' for your Amazon EC2 instances.

Which option provides the best solution?

+ Migrate your application to AWS Lambda
+ Create a custom alarm for your ASG and make your instances trigger the alarm using PutAlarmData API
+ Enable detailed monitoring for EC2 and ASG to get the RAM usage data and create a CloudWatch Alarm on top of it
+ Create a custom metric in CloudWatch and make your instances send data to it using PutMetricData. Then, create an alarm based on this metric

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A team is checking the viability of using AWS Step Functions for creating a banking workflow for loan approvals. The web application will also have human approval as one of the steps in the workflow.

As a developer associate, which of the following would you identify as the key characteristics for AWS Step Function? (Select two)

+ Standard Workflows on AWS Step Functions are suitable for long-running, durable, and auditable workflows that can also support any human approval steps
+ Standard Workflows on AWS Step Functions are suitable for long-running, durable, and auditable workflows that do not support any human approval steps
+ You should use Express Workflows for workloads with high event rates and short duration
+ Express Workflows have a maximum duration of five minutes and Standard workflows have a maximum duration of 180 days or 6 months
+ Both Standard and Express Workflows support all service integrations, activities, and design patterns

<details close>
<summary>Answer</summary>
a,c
</details>

<br>

---
A telecom service provider stores its critical customer data on Amazon Simple Storage Service (Amazon S3).

Which of the following options can be used to control access to data stored on Amazon S3? (Select two)

+ Permissions boundaries, Identity and Access Management (IAM) policies
+ Query String Authentication, Permissions boundaries
+ Bucket policies, Identity and Access Management (IAM) policies
+ Query String Authentication, Access Control Lists (ACLs)
+ IAM database authentication, Bucket policies

<details close>
<summary>Answer</summary>
c,d
</details>

<br>

<details close>
<summary>Note</summary>
Permissions boundary - A Permissions boundary is an advanced feature for using a managed policy to set the maximum permissions that an identity-based policy can grant to an IAM entity. An entity's permissions boundary allows it to perform only the actions that are allowed by both its identity-based policies and its permissions boundaries. When you use a policy to set the permissions boundary for a user, it limits the user's permissions but does not provide permissions on its own.
</details>

<br>

---

A company has hosted its website on an Amazon S3 bucket and have used another Amazon S3 bucket for storing the rest of the assets like images, fonts, etc.

Which technique/mechanism will help the hosted website access its assets without access/permission issues?

+ S3 Transfer Acceleration
+ S3 Cross-Origin Resource Sharing (CORS)
+ S3 Access Analyzer
+ S3 Access Points

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A development team uses shared Amazon S3 buckets to upload files. Due to this shared access, objects in S3 buckets have different owners making it difficult to manage the objects.

As a developer associate, which of the following would you suggest to automatically make the S3 bucket owner, also the owner of all objects in the bucket, irrespective of the AWS account used for uploading the objects?

+ Use S3 CORS to make the S3 bucket owner, the owner of all objects in the bucket
+ Use S3 Access Analyzer to identify the owners of all objects and change the ownership to the bucket owner
+ Use S3 Object Ownership to default bucket owner to be the owner of all objects in the bucket
+ Use Bucket Access Control Lists (ACLs) to control access on S3 bucket and then define its owner

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

To meet compliance guidelines, a company needs to ensure replication of any data stored in its S3 buckets.

Which of the following characteristics are correct while configuring an S3 bucket for replication? (Select two)

+ Same-Region Replication (SRR) and Cross-Region Replication (CRR) can be configured at the S3 bucket level, a shared prefix level, or an object level using S3 object tags
+ Once replication is enabled on a bucket, all old and new objects will be replicated
+ S3 lifecycle actions are not replicated with S3 replication
+ Object tags cannot be replicated across AWS Regions using Cross-Region Replication
+ Replicated objects do not retain metadata

<details close>
<summary>Answer</summary>
a,c
</details>

<br>