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

---
A developer is configuring an Amazon API Gateway as a front door to expose backend business logic. To keep the solution cost-effective, the developer has opted for HTTP APIs.

Which of the following services are not available as an HTTP API via Amazon API Gateway?

+ AWS Web Application Firewall (AWS WAF)
+ AWS Lambda
+ AWS Identity and Access Management (IAM)
+ Amazon Cognito

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A banking application needs to send real-time alerts and notifications based on any updates from the backend services. The company wants to avoid implementing complex polling mechanisms for these notifications.

Which of the following types of APIs supported by the Amazon API Gateway is the right fit?

+ REST APIs
+ WebSocket APIs
+ HTTP APIs
+ REST or HTTP APIs

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A development team has deployed a REST API in Amazon API Gateway to two different stages - a test stage and a prod stage. The test stage is used as a test build and the prod stage as a stable build. After the updates have passed the test, the team wishes to promote the test stage to the prod stage.

Which of the following represents the optimal solution for this use-case?

+ Deploy the API without choosing a stage. This way, the working deployment will be updated in all stages
+ Delete the existing prod stage. Create a new stage with the same name (prod) and deploy the tested version on this stage
+ API performance is optimized in a different way for prod environments. Hence, promoting test to prod is not correct. The promotion should be done by redeploying the API to the prod stage
+ Update stage variable value from the stage name of test to that of prod

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
Stages enable robust version control of your API. In our current use-case, after the updates pass the test, you can promote the test stage to the prod stage. The promotion can be done by redeploying the API to the prod stage or updating a stage variable value from the stage name of test to that of prod.

</details>

---

A company follows collaborative development practices. The engineering manager wants to isolate the development effort by setting up simulations of API components owned by various development teams.

Which API integration type is best suited for this requirement?
+ AWS_PROXY
+ MOCK
+ HTTP_PROXY
+ HTTP

<details close>
<summary>Answer</summary>
b
</details>

---

A company has more than 100 million members worldwide enjoying 125 million hours of TV shows and movies each day. The company uses AWS for nearly all its computing and storage needs, which use more than 10,000 server instances on AWS. This results in an extremely complex and dynamic networking environment where applications are constantly communicating inside AWS and across the Internet. Monitoring and optimizing its network is critical for the company.

The company needs a solution for ingesting and analyzing the multiple terabytes of real-time data its network generates daily in the form of flow logs. Which technology/service should the company use to ingest this data economically and has the flexibility to direct this data to other downstream systems?
+ Amazon Simple Queue Service (SQS)
+ Amazon Kinesis Firehose
+ AWS Glue
+ Amazon Kinesis Data Streams

<details close>
<summary>Answer</summary>
d
</details>


---

A junior developer working on ECS instances terminated a container instance in Amazon Elastic Container Service (Amazon ECS) as per instructions from the team lead. But the container instance continues to appear as a resource in the ECS cluster.

As a Developer Associate, which of the following solutions would you recommend to fix this behavior?

+ You terminated the container instance while it was in RUNNING state, that lead to this synchronization issues
+ The container instance has been terminated with AWS CLI, whereas, for ECS instances, Amazon ECS CLI should be used to avoid any synchronization issues
+ A custom software on the container instance could have failed and resulted in the container hanging in an unhealthy state till restarted again
+ You terminated the container instance while it was in STOPPED state, that lead to this synchronization issues


<details close>
<summary>Answer</summary>
d
</details>

---
A multi-national enterprise uses AWS Organizations to manage its users across different divisions. Even though CloudTrail is enabled on the member accounts, managers have noticed that access issues to CloudTrail logs across different divisions and AWS Regions is becoming a bottleneck in troubleshooting issues. They have decided to use the organization trail to keep things simple.

What are the important points to remember when configuring an organization trail? (Select two)

+ There is nothing called Organization Trail. The master account can, however, enable CloudTrail logging, to keep track of all activities across AWS accounts
+ By default, CloudTrail tracks only bucket-level actions. To track object-level actions, you need to enable Amazon S3 data events
+ Member accounts do not have access to organization trail, neither do they have access to the Amazon S3 bucket that logs the files
+ Member accounts will be able to see the Organization trail, but cannot modify or delete it
+ By default, CloudTrail event log files are not encrypted

<details close>
<summary>Answer</summary>
b,d
</details>

---
A developer from your team has configured the load balancer to route traffic equally between instances or across Availability Zones. However, Elastic Load Balancing (ELB) routes more traffic to one instance or Availability Zone than the others.

Why is this happening and how can it be fixed? (Select two)
+ There could be short-lived TCP connections between clients and instances
+ For Application Load Balancers, cross-zone load balancing is disabled by default
+ Sticky sessions are enabled for the load balancer
+ Instances of a specific capacity type aren’t equally distributed across Availability Zones
+ After you disable an Availability Zone, the targets in that Availability Zone remain registered with the load balancer, thereby receiving random bursts of traffic

<details close>
<summary>Answer</summary>
c,d
</details>

---

A large firm stores its static data assets on Amazon S3 buckets. Each service line of the firm has its own AWS account. For a business use case, the Finance department needs to give access to their S3 bucket's data to the Human Resources department.

Which of the below options is NOT feasible for cross-account access of S3 bucket objects?
+ Use IAM roles and resource-based policies delegate access across accounts within different partitions via programmatic access only
+ Use Resource-based policies and AWS Identity and Access Management (IAM) policies for programmatic-only access to S3 bucket objects
+ Use Access Control List (ACL) and IAM policies for programmatic-only access to S3 bucket objects
+ Use Cross-account IAM roles for programmatic and console access to S3 bucket objects

<details close>
<summary>Answer</summary>
a
</details>

---

You are working for a shipping company that is automating the creation of ECS clusters with an Auto Scaling Group using an AWS CloudFormation template that accepts cluster name as its parameters. Initially, you launch the template with input value 'MainCluster', which deployed five instances across two availability zones. The second time, you launch the template with an input value 'SecondCluster'. However, the instances created in the second run were also launched in 'MainCluster' even after specifying a different cluster name.

+ The EC2 instance is missing IAM permissions to join the other clusters
+ The ECS agent Docker image must be re-built to connect to the other clusters
+ The cluster name Parameter has not been updated in the file /etc/ecs/ecs.config during bootstrap
+ The security groups on the EC2 instance are pointing to the wrong ECS cluster

What is the root cause of this issue?

<details close>
<summary>Answer</summary>
c
</details>

---

A company has a workload that requires 14,000 consistent IOPS for data that must be durable and secure. The compliance standards of the company state that the data should be secure at every stage of its lifecycle on all of the EBS volumes they use.

Which of the following statements are true regarding data security on EBS?

+ EBS volumes support in-flight encryption but does not support encryption at rest
+ EBS volumes do not support in-flight encryption but do support encryption at rest using KMS
+ EBS volumes support both in-flight encryption and encryption at rest using KMS
+ EBS volumes don't support any encryption

<details close>
<summary>Answer</summary>
c
</details>

---

AWS CloudFormation helps model and provision all the cloud infrastructure resources needed for your business.

Which of the following services rely on CloudFormation to provision resources (Select two)?

+ AWS Lambda
+ AWS Autoscaling
+ AWS Elastic Beanstalk
+ AWS CodeBuild
+ AWS Serverless Application Model (AWS SAM)

<details close>
<summary>Answer</summary>
c,e
</details>

---

You team maintains a public API Gateway that is accessed by clients from another domain. Usage has been consistent for the last few months but recently it has more than doubled. As a result, your costs have gone up and would like to prevent other unauthorized domains from accessing your API.

Which of the following actions should you take?

+ Use Account-level throttling
+ Use Mapping Templates
+ Assign a Security Group to your API Gateway
+ Restrict access by using CORS

<details close>
<summary>Answer</summary>
d
</details>

---

You have migrated an on-premise SQL Server database to an Amazon Relational Database Service (RDS) database attached to a VPC inside a private subnet. Also, the related Java application, hosted on-premise, has been moved to an Amazon Lambda function.

Which of the following should you implement to connect AWS Lambda function to its RDS instance?

+ Use Lambda layers to connect to the internet and RDS separately
+ Configure lambda to connect to the public subnet that will give internet access and use Security Group to access RDS inside the private subnet
+ Use Environment variables to pass in the RDS connection string
+ Configure Lambda to connect to VPC with private subnet and Security Group needed to access RDS

<details close>
<summary>Answer</summary>
d
</details>

---
A mobile gaming company is experiencing heavy read traffic to its Amazon Relational Database Service (RDS) database that retrieves player’s scores and stats. The company is using RDS database instance type db.m5.12xlarge, which is not cost-effective for their budget. They would like to implement a strategy to deal with the high volume of read traffic, reduce latency, and also downsize the instance size to cut costs.

As a Developer, which of the following solutions do you recommend?

+ Setup RDS Read Replicas
+ Setup ElastiCache in front of RDS
+ Move to Amazon Redshift
+ Switch application code to AWS Lambda for better performance

<details close>
<summary>Answer</summary>
b
</details>

---

Your web application reads and writes data to your DynamoDB table. The table is provisioned with 400 Write Capacity Units (WCU’s) shared across 4 partitions. One of the partitions receives 250 WCU/second while others receive much less. You receive the error 'ProvisionedThroughputExceededException'.

What is the likely cause of this error?

+ CloudWatch monitoring is lagging
+ Configured IAM policy is wrong
+ Write Capacity Units (WCU’s) are applied across to all your DynamoDB tables and this needs reconfiguration
+ You have a hot partition

<details close>
<summary>Answer</summary>
d
</details>

---

You have a three-tier web application consisting of a web layer using AngularJS, an application layer using an AWS API Gateway and a data layer in an Amazon Relational Database Service (RDS) database. Your web application allows visitors to look up popular movies from the past. The company is looking at reducing the number of calls made to endpoint and improve latency to the API.

What can you do to improve performance?

+ Use Mapping Templates
+ Enable API Gateway Caching
+ Use Stage Variables
+ Use Amazon Kinesis Data Streams to stream incoming data and reduce the burden on Gateway APIs

<details close>
<summary>Answer</summary>
b
</details>

---

Two policies are attached to an IAM user. The first policy states that the user has explicitly been denied all access to EC2 instances. The second policy states that the user has been allowed permission for EC2:Describe action.

When the user tries to use 'Describe' action on an EC2 instance using the CLI, what will be the output?

+ The IAM user stands in an invalid state, because of conflicting policies
+ The user will get access because it has an explicit allow
+ The user will be denied access because one of the policies has an explicit deny on it
+ The order of the policy matters. If policy 1 is before 2, then the user is denied access. If policy 2 is before 1, then the user is allowed access

<details close>
<summary>Answer</summary>
c
</details>

---

Your team lead has requested code review of your code for Lambda functions. Your code is written in Python and makes use of the Amazon Simple Storage Service (S3) to upload logs to an S3 bucket. After the review, your team lead has recommended reuse of execution context to improve the Lambda performance.

Which of the following actions will help you implement the recommendation?

+ Use environment variables to pass operational parameters
+ Assign more RAM to the function
+ Move the Amazon S3 client initialization, out of your function handler
+ Enable X-Ray integration

<details close>
<summary>Answer</summary>
c
</details>

---

As a Senior Developer, you manage 10 Amazon EC2 instances that make read-heavy database requests to the Amazon RDS for PostgreSQL. You need to make this architecture resilient for disaster recovery.

Which of the following features will help you prepare for database disaster recovery? (Select two)

+ Use cross-Region Read Replicas
+ Enable the automated backup feature of Amazon RDS  in a multi-AZ deployment that creates backups across multiple Regions
+ Use RDS Provisioned IOPS (SSD) Storage in place of General Purpose (SSD) Storage
+ Enable the automated backup feature of Amazon RDS in a multi-AZ deployment that creates backups in a single AWS Region
+ Use database cloning feature of the RDS DB cluster

<details close>
<summary>Answer</summary>
a,d
</details>

---
You have deployed a traditional 3-tier web application architecture with a Classic Load Balancer, an Auto Scaling group, and an Amazon Relational Database Service (RDS) database. Users are reporting that they have to re-authenticate into the website often.

Which of the following represents a scalable solution to make the application tier stateless and outsource the session information?

+ Use Elastic IP
+ Enable RDS read replicas
+ Enable Load Balancer stickiness
+ Add an ElastiCache Cluster

<details close>
<summary>Answer</summary>
d
</details>

---

A media company uses Amazon Simple Queue Service (SQS) queue to manage their transactions. With changing business needs, the payload size of the messages is increasing. The Team Lead of the project is worried about the 256 KB message size limit that SQS has.

What can be done to make the queue accept messages of a larger size?

+ Use the MultiPart API
+ Get a service limit increase from AWS
+ Use gzip compression
+ Use the SQS Extended Client

<details close>
<summary>Answer</summary>
d
</details>

---

A company has their entire stack integrated with AWS X-Ray. A manager at the company noticed the skyrocketing AWS monthly usage charges for the X-Ray service. He tracked the abnormal bills to the high volume of input data going into X-Ray. As a Developer, you have been given the responsibility to fix this issue as quickly as possible, with minimal disruptions.

Which of the below is the optimal choice for this issue?
+ Enable X-Ray Sampling
+ Send only the required data from client-side
+ Custom configuration of the X-Ray agents
+ Enable X-Ray Deep linking to send only the most useful data to X-Ray

<details close>
<summary>Answer</summary>
a
</details>

---

A development team has created a new IAM user that has `s3:putObject` permission to write to an S3 bucket. This S3 bucket uses server-side encryption with AWS KMS managed keys (SSE-KMS) as the default encryption. Using the access key ID and the secret access key of the IAM user, the application received an access denied error when calling the `PutObject` API.

As a Developer Associate, how would you resolve this issue?

+ Correct the policy of the IAM user to allow the `s3:Encrypt` action
+ Correct the bucket policy of the S3 bucket to allow the IAM user to upload encrypted objects
+ Correct the policy of the IAM user to allow the `kms:GenerateDataKey` action
+ Correct the ACL of the S3 bucket to allow the IAM user to upload encrypted objects

<details close>
<summary>Answer</summary>
c
</details>

---

The development team at a company wants to encrypt a 111 GB object using AWS KMS.

Which of the following represents the best solution?

+ Make a `GenerateDataKeyWithPlaintext`  API call that returns an encrypted copy of a data key. Use a plaintext key to encrypt the data
+ Make an `Encryption`  API call to encrypt the plaintext data as ciphertext using a customer master key (CMK) with imported key material
+ Make a `GenerateDataKey` API call that returns a plaintext key and an encrypted copy of a data key. Use a plaintext key to encrypt the data
+ Make a `GenerateDataKeyWithoutPlaintext` API call that returns an encrypted copy of a data key. Use an encrypted key to encrypt the data

<details close>
<summary>Answer</summary>
c
</details>

---

As part of employee skills upgrade, the developers of your team have been delegated few responsibilities of DevOps engineers. Developers now have full control over modeling the entire software delivery process, from coding to deployment. As the team lead, you are now responsible for any manual approvals needed in the process.

Which of the following approaches supports the given workflow?

+ Create one CodePipeline for your entire flow and add a manual approval step
+ Create multiple CodePipelines for each environment and link them using AWS Lambda
+ Create deeply integrated AWS CodePipelines for each environment
+ Use CodePipeline with Amazon Virtual Private Cloud

<details close>
<summary>Answer</summary>
a
</details>

---

A company’s e-commerce website is expecting hundreds of thousands of visitors on Black Friday. The marketing department is concerned that high volumes of orders might stress SQS leading to message failures. The company has approached you for the steps to be taken as a precautionary measure against the high volumes.

What step will you suggest as a Developer Associate?

+ Amazon SQS is highly scalable and does not need any intervention to handle the expected high volumes
+ Pre-configure the SQS queue to increase the capacity when messages hit a certain threshold
+ Enable auto-scaling in the SQS queue
+ Convert the queue into FIFO ordered queue, since messages to the down system will be processed faster once they are ordered

<details close>
<summary>Answer</summary>
a
</details>

---

An intern at an IT company is getting started with AWS Cloud and wants to understand the following Amazon S3 bucket access policy:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ListAllS3Buckets",
            "Effect": "Allow",
            "Action": ["s3:ListAllMyBuckets"],
            "Resource": "arn:aws:s3:::*"
        },
        {
            "Sid": "AllowBucketLevelActions",
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetBucketLocation"
            ],
            "Resource": "arn:aws:s3:::*"
        },
        {
            "Sid": "AllowBucketObjectActions",
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:PutObjectAcl",
                "s3:GetObject",
                "s3:GetObjectAcl",
                "s3:DeleteObject"
            ],
            "Resource": "arn:aws:s3:::*/*"
        },
        {
            "Sid": "RequireMFAForProductionBucket",
            "Effect": "Deny",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::Production/*",
                "arn:aws:s3:::Production"
            ],
            "Condition": {
                "NumericGreaterThanIfExists": {"aws:MultiFactorAuthAge": "1800"}
            }
        }
    ]
}

```
As a Developer Associate, can you help him identify what the policy is for?

+ Allows a user to manage a single Amazon S3 bucket and denies every other AWS action and resource if the user is not signed in using MFA within last thirty minutes
+ Allows full S3 access to an Amazon Cognito user, but explicitly denies access to the Production bucket if the Cognito user is not authenticated
+ Allows IAM users to access their own home directory in Amazon S3, programmatically and in the console
+ Allows full S3 access, but explicitly denies access to the Production bucket if the user has not signed in using MFA within the last thirty minutes


<details close>
<summary>Answer</summary>
d
</details>

---

An organization is moving its on-premises resources to the cloud. Source code will be moved to AWS CodeCommit and AWS CodeBuild will be used for compiling the source code using Apache Maven as a build tool. The organization wants the build environment should allow for scaling and running builds in parallel.

Which of the following options should the organization choose for their requirement?

+ Choose a high-performance instance type for your CodeBuild instances
+ CodeBuild scales automatically, the organization does not have to do anything for scaling or for parallel builds
+ Run CodeBuild in an Auto Scaling group
+ Enable CodeBuild Auto Scaling

<details close>
<summary>Answer</summary>
b
</details>

---


Your company has a three-year contract with a healthcare provider. The contract states that monthly database backups must be retained for the duration of the contract for compliance purposes. Currently, the limit on backup retention for automated backups, on Amazon Relational Database Service (RDS), does not meet your requirements.

Which of the following solutions can help you meet your requirements?

+ Create a cron event in CloudWatch, which triggers an AWS Lambda function that triggers the database snapshot
+ Enable RDS automatic backups
+ Enable RDS Read replicas
+ Enable RDS Multi-AZ


<details close>
<summary>Answer</summary>
a
</details>

---

A recruit has created an Amazon Simple Storage Service (S3) bucket. He needs assistance in getting the security principles right for this bucket.

Which of the following is NOT a security practice for access control to S3 buckets?
+ Use of IAM Roles
+ Use of Security Groups
+ Use of Access Control Lists (ACLs)
+ Use of Bucket Policies

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
S3 is a managed service. Security Groups is for instances.
</details>

---

You are running a cloud file storage website with an Internet-facing Application Load Balancer, which routes requests from users over the internet to 10 registered Amazon EC2 instances. Users are complaining that your website always asks them to re-authenticate when they switch pages. You are puzzled because this behavior is not seen in your local machine or dev environment.

What could be the reason?
+ The Load Balancer does not have stickiness enabled
+ Application Load Balancer is in slow-start mode, which gives ALB a little more time to read and write session data
+ The EC2 instances are logging out the users because the instances never have access to the client IPs because of the Load Balancer
+ The Load Balancer does not have TLS enabled

<details close>
<summary>Answer</summary>
a
</details>

---

You company runs business logic on smaller software components that perform various functions. Some functions process information in a few seconds while others seem to take a long time to complete. Your manager asked you to decouple components that take a long time to ensure software applications stay responsive under load. You decide to configure Amazon Simple Queue Service (SQS) to work with your Elastic Beanstalk configuration.

Which of the following Elastic Beanstalk environment should you choose to meet this requirement?

+ Single Instance Worker node
+ Load-balancing, Autoscaling environment
+ Dedicated worker environment
+ Single Instance with Elastic IP

<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
Single Instance Worker node is term in Kubernetes
</details>

---

Recently, you started an online learning platform using AWS Lambda and AWS Gateway API. Your first version was successful, and you began developing new features for the second version. You would like to gradually introduce the second version by routing only 10% of the incoming traffic to the new Lambda version.

Which solution should you opt for?

+ Use Tags to distinguish the different versions
+ Use environment variables
+ Use AWS Lambda aliases
+ Deploy your Lambda in a VPC

<details close>
<summary>Answer</summary>
c
</details>

---

Your application is deployed automatically using AWS Elastic Beanstalk. Your YAML configuration files are stored in the folder .ebextensions and new files are added or updated often. The DevOps team does not want to re-deploy the application every time there are configuration changes, instead, they would rather manage configuration externally, securely, and have it load dynamically into the application at runtime.

What option allows you to do this?

+ Use S3
+ Use Environment variables
+ Use Stage Variables
+ Use SSM Parameter Store

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
AWS Systems Manager Parameter Store provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, and license codes as parameter values. For the given use-case, as the DevOps team does not want to re-deploy the application every time there are configuration changes, so they can use the SSM Parameter Store to store the configuration externally.

S3 offers the same benefit as the SSM Parameter Store where there are no servers to manage. With S3 you have to set encryption and choose other security options and there are more chances of misconfiguring security if you share your S3 bucket with other objects. You would have to create a custom setup to come close to the parameter store. Use Parameter Store and let AWS handle the rest.

</details>

---
You are a developer working with the AWS CLI to create Lambda functions that contain environment variables. Your functions will require over 50 environment variables consisting of sensitive information of database table names.

What is the total set size/number of environment variables you can create for AWS Lambda?

+ The total size of all environment variables shouldn't exceed 8 KB. The maximum number of variables that can be created is 50
+ The total size of all environment variables shouldn't exceed 8 KB. There is no limit on the number of variables
+ The total size of all environment variables shouldn't exceed 4 KB. There is no limit on the number of variables
+ The total size of all environment variables shouldn't exceed 4 KB. The maximum number of variables that can be created is 35

<details close>
<summary>Answer</summary>
c
</details>

---

You are creating a mobile application that needs access to the AWS API Gateway. Users will need to register first before they can access your API and you would like the user management to be fully managed.

Which authentication option should you use for your API Gateway layer?

+ Use Lambda Authorizer
+ Use IAM permissions with sigv4
+ Use Cognito User Pools
+ Use API Gateway User Pools


<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
Use Lambda Authorizer- A Lambda authorizer (formerly known as a custom authorizer) is an API Gateway feature that uses a Lambda function to control access to your API. A Lambda authorizer is useful if you want to implement a custom authorization scheme that uses a bearer token authentication strategy such as OAuth or SAML, or that uses request parameters to determine the caller's identity. This won't be a fully managed user management solution but it would allow you to check for access at the AWS API Gateway level.

</details>

---

A new member of your team is working on creating Dead Letter Queue (DLQ) for AWS Lambda functions.

As a Developer Associate, can you help him identify the use cases, wherein AWS Lambda will add a message into a DLQ after being processed? (Select two)


+ The Lambda function invocation is synchronous
+ The event has been processed successfully
+ The Lambda function invocation is asynchronous
+ The event fails all processing attempts
+ The Lambda function invocation failed only once but succeeded thereafter

<details close>
<summary>Answer</summary>
c,d
</details>

---

You have an Auto Scaling group configured to a minimum capacity of 1 and a maximum capacity of 5, designed to launch EC2 instances across 3 Availability Zones. During a low utilization period, an entire Availability Zone went down and your application experienced downtime.

What can you do to ensure that your application remains highly available?

+ Change the scaling metric of auto-scaling policy to network bytes
+ Increase the minimum instance capacity of the Auto Scaling Group to 2
+ Configure ASG fast failover
+ Enable RDS Multi-AZ


<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
You configure the size of your Auto Scaling group by setting the minimum, maximum, and desired capacity. The minimum and maximum capacity are required to create an Auto Scaling group, while the desired capacity is optional. If you do not define your desired capacity upfront, it defaults to your minimum capacity.

Since a minimum capacity of 1 was defined, an instance was launched in only one AZ. This AZ went down, taking the application with it. If the minimum capacity is set to 2. As per Auto Scale AZ configuration, it would have launched 2 instances- one in each AZ, making the architecture disaster-proof and hence highly available.

</details>

