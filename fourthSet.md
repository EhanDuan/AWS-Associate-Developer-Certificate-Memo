# Exam#4 Practice Set

A senior cloud engineer designs and deploys online fraud detection solutions for credit card companies processing millions of transactions daily. The Elastic Beanstalk application sends files to Amazon S3 and then sends a message to an Amazon SQS queue containing the path of the uploaded file in S3. The engineer wants to postpone the delivery of any new messages to the queue for at least 10 seconds.

Which SQS feature should the engineer leverage?

+ Implement application-side delay
+ Use DelaySeconds parameter
+ Use visibility timeout parameter
+ Enable LongPolling

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A communication platform serves millions of customers and deploys features in a production environment on AWS via CodeDeploy. You are reviewing scripts for the deployment process located in the AppSec file.

Which of the following options lists the correct order of lifecycle events?

+ DownloadBundle => BeforeInstall => ApplicationStart => ValidateService
+ BeforeInstall => ApplicationStart => DownloadBundle => ValidateService
+ ValidateService => BeforeInstall =>DownloadBundle => ApplicationStart
+ BeforeInstall => ValidateService =>DownloadBundle => ApplicationStart

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

You are assigned as the new project lead for a web application that processes orders for customers. You want to integrate event-driven processing anytime data is modified or deleted and use a serverless approach using AWS Lambda for processing stream events.

Which of the following databases should you choose from?

+ DynamoDB
+ RDS
+ ElastiCache
+ Kinesis

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
A DynamoDB stream is an ordered flow of information about changes to items in a DynamoDB table. When you enable a stream on a table, DynamoDB Streams captures a time-ordered sequence of item-level modifications in any DynamoDB table, and stores this information in a log for up to 24 hours. Applications can access this log and view the data items as they appeared before and after they were modified, in near real-time.

Whenever an application creates, updates, or deletes items in the table, DynamoDB Streams writes a stream record with the primary key attributes of the items that were modified.
</details>

---

An IT company is using AWS CloudFormation to manage its IT infrastructure. It has created a template to provision a stack with a VPC and a subnet. The output value of this subnet has to be used in another stack.

As a Developer Associate, which of the following options would you suggest to provide this information to another stack?

+ Use 'Expose' field in the Output section of the stack's template
+ Use 'Export' field in the Output section of the stack's template
+ Use Fn::ImportValue
+ Use Fn::Transform

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

Your company manages hundreds of EC2 instances running on Linux OS. The instances are configured in several Availability Zones in the eu-west-3 region. Your manager has requested to collect system memory metrics on all EC2 instances using a script.

Which of the following solutions will help you collect this data?

+ Use a cron job on the instances that pushes the EC2 RAM statistics as a Custom metric into CloudWatch
+ Extract RAM statistics using the instance metadata
+ Extract RAM statistics from the standard CloudWatch metrics for EC2 instances
+ Extract RAM statistics using X-Ray

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

An organization uses Alexa as its intelligent assistant to improve productivity throughout the organization. A group of developers manages custom Alexa Skills written in Node.Js to control conference-room equipment settings and start meetings using voice activation. The manager has requested developers that all functions code should be monitored for error rates with the possibility of creating alarms on top of them.

Which of the following options should be chosen? (select two)

+ CloudWatch Metrics
+ X-Ray
+ CloudWatch Alarms
+ CloudTrail
+ SSM

<details close>
<summary>Answer</summary>
a,c
</details>

<br>

---

You are working on a project that has over 100 dependencies. Every time your AWS CodeBuild runs a build step it has to resolve Java dependencies from external Ivy repositories which take a long time. Your manager wants to speed this process up in AWS CodeBuild.

Which of the following will help you do this with minimal effort?


+ Use Instance Store type of EC2 instances to facilitate internal dependency cache
+ Reduce the number of dependencies
+ Ship all the dependencies as part of the source code
+ Cache dependencies on S3


<details close>
<summary>Answer</summary>
d
</details>

<br>

---

An IT company has a web application running on Amazon EC2 instances that needs read-only access to an Amazon DynamoDB table.

As a Developer Associate, what is the best-practice solution you would recommend to accomplish this task?

+ Create an IAM role with an AmazonDynamoDBReadOnlyAccess policy and apply it to the EC2 instance profile
+ Create a new IAM user with access keys. Attach an inline policy to the IAM user with read-only access to DynamoDB. Place the keys in the code. For security, redeploy the code whenever the keys rotate
+ Create an IAM user with Administrator access and configure AWS credentials for this user on the given EC2 instance
+ Run application code with AWS account root user credentials to ensure full access to all AWS services

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A cybersecurity company is publishing critical log data to a log group in Amazon CloudWatch Logs, which was created 3 months ago. The company must encrypt the log data using an AWS KMS customer master key (CMK), so any future data can be encrypted to meet the company’s security guidelines.

How can the company address this use-case?


+ Enable the encrypt feature on the log group via the CloudWatch Logs console
+ Use the AWS CLI `describe-log-groups` command and specify the KMS key ARN
+ Use the AWS CLI `create-log-group` command and specify the KMS key ARN
Use the AWS CLI `associate-kms-key` command and specify the KMS key ARN

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A development team uses the AWS SDK for Java to maintain an application that stores data in AWS DynamoDB. The application makes use of Scan operations to return several items from a 25 GB table. There is no possibility of creating indexes to retrieve these items predictably. Developers are trying to get these specific rows from DynamoDB as fast as possible.

Which of the following options can be used to improve the performance of the Scan operation?

+ Use a Query
+ Use a ProjectionExpression
+ Use a FilterExpression
+ Use parallel scans

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A media company is building an application that needs to store video files in Amazon S3. Management requires that the files be encrypted before they are sent to Amazon S3 for storage. The encryption keys need to be managed by an in-house security team but the key itself is stored on AWS.

Which solution should the company use to meet these requirements?

+ Use server-side encryption with customer-provided encryption key (SSE-C)
+ Use client-side encryption with an AWS KMS managed customer master key (CMK)
+ Use server-side encryption with a client-side master key
+ Use client-side encryption with Amazon S3 managed key

<details close>
<summary>Answer</summary>
b
</details>

<br>


<details close>
<summary>Note</summary>
Before => client-side
</details>

<br>

---

You are a manager for a tech company that has just hired a team of developers to work on the company's AWS infrastructure. All the developers are reporting to you that when using the AWS CLI to execute commands it fails with the following exception: You are not authorized to perform this operation. Encoded authorization failure message: 6h34GtpmGjJJUm946eDVBfzWQJk6z5GePbbGDs9Z2T8xZj9EZtEduSnTbmrR7pMqpJrVYJCew2m8YBZQf4HRWEtrpncANrZMsnzk.

Which of the following actions will help developers decode the message?

+ AWS IAM decode-authorization-message
+ AWS STS decode-authorization-message
+ Use KMS decode-authorization-message
+ AWS Cognito Decoder


<details close>
<summary>Answer</summary>
b
</details>

<br>

---

After reviewing your monthly AWS bill you notice that the cost of using Amazon SQS has gone up substantially after creating new queues; however, you know that your queue clients do not have a lot of traffic and are receiving empty responses.

Which of the following actions should you take?
+ Use a FIFO queue
+ Increase the VisibilityTimeout
+ Use LongPolling
+ Decrease DelaySeconds

<details close>
<summary>Answer</summary>
c
</details>

<br>
---

The development team at a company wants to insert vendor records into an Amazon DynamoDB table as soon as the vendor uploads a new file into an Amazon S3 bucket.

As a Developer Associate, which set of steps would you recommend to achieve this?

+ Create an S3 event to invoke a Lambda function that inserts records into DynamoDB
+ Write a cron job that will execute a Lambda function at a scheduled time and insert the records into DynamoDB
+ Set up an event with Amazon CloudWatch Events that will monitor the S3 bucket and then insert the records into DynamoDB
+ Develop a Lambda function that will poll the S3 bucket and then insert the records into DynamoDB


<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
CloudWatch cannot directly insert sth into DynamoDB table. Need something like Lambda function
</details>

<br>

---

An IT company uses a blue/green deployment policy to provision new Amazon EC2 instances in an Auto Scaling group behind a new Application Load Balancer for each new application version. The current set up requires the users to log in after every new deployment.

As a Developer Associate, what advice would you give to the company for resolving this issue?

+ Use ElastiCache to maintain user sessions
+ Use rolling updates instead of a blue/green deployment
+ Enable sticky sessions in the Application Load Balancer
+ Use multicast to replicate session information

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
Sticky sessions in ALB will disappear when ALB is replaced during new deployment.
</details>

<br>

---

You have an Amazon Kinesis Data Stream with 10 shards, and from the metrics, you are well below the throughput utilization of 10 MB per second to send data. You send 3 MB per second of data and yet you are receiving ProvisionedThroughputExceededException errors frequently.

What is the likely cause of this?

+ Metrics are slow to update
+ The partition key that you have selected isn't distributed enough
+ You have too many shards
+ The data retention period is too long

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

An e-commerce company has implemented AWS CodeDeploy as part of its AWS cloud CI/CD strategy. The company has configured automatic rollbacks while deploying a new version of its flagship application to Amazon EC2.

What occurs if the deployment of the new version fails?

+ CodeDeploy switches the Route 53 alias records back to the known good green deployment and terminates the failed blue deployment
+ AWS CodePipeline promotes the most recent working deployment with a SUCCEEDED status to production
+ The last known working deployment is automatically restored using the snapshot stored in Amazon S3
+ A new deployment of the last known working version of the application is deployed with a new deployment ID

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
CodeDeploy rolls back deployments by redeploying a previously deployed revision of an application as a new deployment. These rolled-back deployments are technically new deployments, with new deployment IDs, rather than restored versions of a previous deployment.

To roll back an application to a previous revision, you just need to deploy that revision. AWS CodeDeploy keeps track of the files that were copied for the current revision and removes them before starting a new deployment, so there is no difference between redeploy and rollback. However, you need to make sure that the previous revisions are available for rollback.

</details>

---
A developer has pushed a Lambda function that pushes data into an RDS MySQL database with the following Python code:
```python
def handler(event, context):
    mysql = mysqlclient.connect()
    data = event['data']
    mysql.execute(f"INSERT INTO foo (bar) VALUES (${data});")
    mysql.close()
    return
```

On the first execution, the Lambda function takes 2 seconds to execute. On the second execution and all the subsequent ones, the Lambda function takes 1.9 seconds to execute.

What can be done to improve the execution time of the Lambda function?

+ Upgrade the MySQL instance type
+ Change the runtime to Node.js
+ Increase the Lambda function RAM
+ Move the database connection out of the handler

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A firm uses AWS DynamoDB to store information about people’s favorite sports teams and allow the information to be searchable from their home page. There is a daily requirement that all 10 million records in the table should be deleted then re-loaded at 2:00 AM each night.

Which option is an efficient way to delete with minimal costs?

+ Scan and call BatchDeleteItem
+ Scan and call DeleteItem
+ Delete then re-create the table
+ Call PurgeTable

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

You have a popular web application that accesses data stored in an Amazon Simple Storage Service (S3) bucket. Developers use the SDK to maintain the application and add new features. Security compliance requests that all new objects uploaded to S3 be encrypted using SSE-S3 at the time of upload. Which of the following headers must the developers add to their request?

+ 'x-amz-server-side-encryption': 'AES256'
+ 'x-amz-server-side-encryption': 'SSE-S3'
+ 'x-amz-server-side-encryption': 'SSE-KMS' 
+ 'x-amz-server-side-encryption': 'aws:kms'

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
SSE-S3 (Amazon S3-Managed Keys) is an option available but it's not a valid header value.
</details>

<br>

---

A data analytics company with its IT infrastructure on the AWS Cloud wants to build and deploy its flagship application as soon as there are any changes to the source code.

As a Developer Associate, which of the following options would you suggest to trigger the deployment? (Select two)

+ Keep the source code in Amazon EFS and start AWS CodePipeline whenever a file is updated
+ Keep the source code in an AWS CodeCommit repository and start AWS CodePipeline whenever a change is pushed to the CodeCommit repository
+ Keep the source code in an Amazon S3 bucket and start AWS CodePipeline whenever a file in the S3 bucket is updated
+ Keep the source code in an Amazon S3 bucket and set up AWS CodePipeline to recur at an interval of every 15 minutes
+ Keep the source code in an Amazon EBS volume and start AWS CodePipeline whenever there are updates to the source code


<details close>
<summary>Answer</summary>
b,c
</details>

<br>

<details close>
<summary>Note</summary>
EFS and EBS are not supported as valid source providers for CodePipeLine 
</details>

<br>

---

You are a system administrator whose company recently moved its production application to AWS and migrated data from MySQL to AWS DynamoDB. You are adding new tables to AWS DynamoDB and need to allow your application to query your data by the primary key and an alternate key. This option must be added when first creating tables otherwise changes cannot be made afterward.

Which of the following actions should you take?

+ Create a GSI
+ Call Scan
+ Create a LSI
+ Migrate away from DynamoDB

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

As part of internal regulations, you must ensure that all communications to Amazon S3 are encrypted.

For which of the following encryption mechanisms will a request get rejected if the connection is not using HTTPS?

+ SSE-KMS
+ SSE-C
+ Client Side Encryption
+ SSE-S3

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
Amazon S3 will reject any requests made over HTTP when using SSE-C. For security considerations, AWS recommends that you consider any key you send erroneously using HTTP to be compromised.
</details>

<br>

---

You have moved your on-premise infrastructure to AWS and are in the process of configuring an AWS Elastic Beanstalk deployment environment for production, development, and testing. You have configured your production environment to use a rolling deployment to prevent your application from becoming unavailable to users. For the development and testing environment, you would like to deploy quickly and are not concerned about downtime.

Which of the following deployment policies meet your needs?

+ Immutable
+ Rolling
+ Rolling with additional batches
+ All at once

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

You have uploaded a zip file to AWS Lambda that contains code files written in Node.Js. When your function is executed you receive the following output, 'Error: Memory Size: 10,240 MB Max Memory Used'.

Which of the following explains the problem?

+ The uncompressed zip file exceeds AWS Lambda limits
+ You have uploaded a zip file larger than 50 MB to AWS Lambda
+ Your Lambda function ran out of RAM
+ Your zip file is corrupt

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An organization recently began using AWS CodeCommit for its source control service. A compliance security team visiting the organization was auditing the software development process and noticed developers making many git push commands within their development machines. The compliance team requires that encryption be used for this activity.

How can the organization ensure source code is encrypted in transit and at rest?

+ Use a git command line hook to encrypt the code client side
+ Enable KMS encryption
+ Use AWS Lambda as a hook to encrypt the pushed code
+ Repositories are automatically encrypted at rest

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A voting system hosted on-premise was recently migrated to AWS to lower cost, gain scalability, and to better serve thousands of concurrent users. When one of the AWS resource state changes, it generates an event and will need to trigger AWS Lambda. The AWS resource whose state changes and AWS Lambda does not have direct integration.

Which of the following methods can be used to trigger AWS Lambda?
+ Open a support ticket with AWS
+ AWS Lambda Custom Sources
+ CloudWatch Events Rules with AWS Lambda
+ Cron jobs to trigger AWS Lambda to check the state of your service

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

You have a web application hosted on EC2 that makes GET and PUT requests for objects stored in Amazon Simple Storage Service (S3) using the SDK for PHP. As the security team completed the final review of your application for vulnerabilities, they noticed that your application uses hardcoded IAM access key and secret access key to gain access to AWS services. They recommend you leverage a more secure setup, which should use temporary credentials if possible.

Which of the following options can be used to address the given use-case?

+ Use the SSM parameter store
+ Use environment variables
+ Hardcode the credentials in the application code
+ Use an IAM Instance Role

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A developer is configuring an Application Load Balancer (ALB) to direct traffic to the application's EC2 instances and Lambda functions.

Which of the following characteristics of the ALB can be identified as correct? (Select two)
+ An ALB has three possible target types: Instance, IP and Lambda
+ If you specify targets using an instance ID, traffic is routed to instances using any private IP address from one or more network interfaces
+ If you specify targets using IP addresses, traffic is routed to instances using the primary private IP address
+ An ALB has three possible target types: Hostname, IP and Lambda
+ You can not specify publicly routable IP addresses to an ALB


<details close>
<summary>Answer</summary>
a,e
</details>

<br>

<details close>
<summary>Note</summary>

</details>

**An ALB has three possible target types: Instance, IP and Lambda**

When you create a target group, you specify its target type, which determines the type of target you specify when registering targets with this target group. After you create a target group, you cannot change its target type. The following are the possible target types:

`Instance` - The targets are specified by instance ID
`IP` - The targets are IP addresses
`Lambda` - The target is a Lambda function

**You can not specify publicly routable IP addresses to an ALB**

When the target type is IP, you can specify IP addresses from specific CIDR blocks only. You can't specify publicly routable IP addresses.

<br>

---


A company has several Linux-based EC2 instances that generate various log files which need to be analyzed for security and compliance purposes. The company wants to use Kinesis Data Streams (KDS) to analyze this log data.

Which of the following is the most optimal way of sending log data from the EC2 instances to KDS?

+ Use Kinesis Producer Library (KPL) to collect and ingest data from each EC2 instance
+ Run cron job on each of the instances to collect log data and send it to Kinesis Data Streams
+ Install and configure Kinesis Agent on each of the instances
+ Install AWS SDK on each of the instances and configure it to send the necessary files to Kinesis Data Streams

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An Amazon Simple Queue Service (SQS) has to be configured between two AWS accounts for shared access to the queue. AWS account A has the SQS queue in its account and AWS account B has to be given access to this queue.

Which of the following options need to be combined to allow this cross-account access? (Select three)

+ The account A administrator creates an IAM role and attaches a permissions policy
+ The account B administrator creates an IAM role and attaches a trust policy to the role with account B as the principal
+ The account A administrator attaches a trust policy to the role that identifies account B as the principal who can assume the role
+ The account A administrator delegates the permission to assume the role to any users in account A
+ The account B administrator delegates the permission to assume the role to any users in account B
+ The account A administrator attaches a trust policy to the role that identifies account B as the AWS service principal who can assume the role

<details close>
<summary>Answer</summary>
a,c,e
</details>

<br>

---

A user has an IAM policy as well as an Amazon SQS policy that apply to his account. The IAM policy grants his account permission for the `ReceiveMessage` action on `example_queue`, whereas the Amazon SQS policy gives his account permission for the `SendMessage` action on the same queue.

Considering the permissions above, which of the following options are correct? (Select two)

+ If the user sends a `SendMessage` request to `example_queue`, the IAM policy will deny this action 
+ Either of IAM policies or Amazon SQS policies should be used to grant permissions. Both cannot be used together
+ The user can send a `ReceiveMessage` request to `example_queue`, the IAM policy allows this action
+ Adding only an IAM policy to deny the user of all actions on the queue is not enough. The SQS policy should also explicitly deny all action
+ If you add a policy that denies the user access to all actions for the queue, the policy will override the other two policies and the user will not have access to `example_queue`

<details close>
<summary>Answer</summary>
c,e
</details>

<br>

---

An order management system uses a cron job to poll for any new orders. Every time a new order is created, the cron job sends this order data as a message to the message queues to facilitate downstream order processing in a reliable way. To reduce costs and improve performance, the company wants to move this functionality to AWS cloud.

Which of the following is the most optimal solution to meet this requirement?

+ Configure different Amazon Simple Queue Service (SQS) queues to poll for new orders
+ Use Amazon Simple Notification Service (SNS) to push notifications and use AWS Lambda functions to process the information received from SNS
+ Use Amazon Simple Notification Service (SNS) to push notifications to Kinesis Data Firehose delivery streams for processing the data for downstream applications
+ Use Amazon Simple Notification Service (SNS) to push notifications when an order is created. Configure different Amazon Simple Queue Service (SQS) queues to receive these messages for downstream processing


<details close>
<summary>Answer</summary>
d
</details>

<br>

---

You have configured a Network ACL and a Security Group for the load balancer and Amazon EC2 instances to allow inbound traffic on port 80. However, users are still unable to connect to your website after launch.

Which additional configuration is required to make the website accessible to all users over the internet?

+ Add a rule to the Network ACLs to allow outbound traffic on ports 1025 - 5000
+ Add a rule to the Network ACLs to allow outbound traffic on ports 1024 - 65535
+ Add a rule to the Security Group allowing outbound traffic on port 80
+ Add a rule to the Network ACLs to allow outbound traffic on ports 32768 - 61000

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
The client that initiates the request chooses the ephemeral port range. The range varies depending on the client's operating system. Requests originating from Elastic Load Balancing use ports 1024-65535. List of ephemeral port ranges:

Many Linux kernels (including the Amazon Linux kernel) use ports 32768-61000.

Requests originating from Elastic Load Balancing use ports 1024-65535.

Windows operating systems through Windows Server 2003 use ports 1025-5000.

Windows Server 2008 and later versions use ports 49152-65535.

A NAT gateway uses ports 1024-65535.

AWS Lambda functions use ports 1024-65535.
</details>

<br>

---

A development team had enabled and configured CloudTrail for all the Amazon S3 buckets used in a project. The project manager owns all the S3 buckets used in the project. However, the manager noticed that he did not receive any object-level API access logs when the data was read by another AWS account.

What could be the reason for this behavior/error?

+ The bucket owner also needs to be object owner to get the object access logs
+ CloudTrail needs to be configured on both the AWS accounts for receiving the access logs in cross-account access
+ CloudTrail always delivers object-level API access logs to the requester and not to object owner
+ The meta-data of the bucket is in an invalid state and needs to be corrected by the bucket owner from AWS console to fix the issue

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company wants to add geospatial capabilities to the cache layer, along with query capabilities and an ability to horizontally scale. The company uses Amazon RDS as the database tier.

Which solution is optimal for this use-case?

+ Leverage the capabilities offered by ElastiCache for Redis with cluster mode disabled
+ Use CloudFront caching to cater to demands of increasing workloads
+ Leverage the capabilities offered by ElastiCache for Redis with cluster mode enabled
+ Migrate to Amazon DynamoDB to utilize the automatically integrated DynamoDB Accelerator (DAX) along with query capability features


<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A development team is considering Amazon ElastiCache for Redis as its in-memory caching solution for its relational database.

Which of the following options are correct while configuring ElastiCache? (Select two)

+ All the nodes in a Redis cluster must reside in the same region
+ You can scale write capacity for Redis by adding replica nodes
+ While using Redis with cluster mode enabled, you cannot manually promote any of the replica nodes to primary
+ While using Redis with cluster mode enabled, asynchronous replication mechanisms are used to keep the read replicas synchronized with the primary. If cluster mode is disabled, the replication mechanism is done synchronously
+ If you have no replicas and a node fails, you experience no loss of data when using Redis with cluster mode enabled

<details close>
<summary>Answer</summary>
a,c
</details>

<br>

---

A website serves static content from an Amazon Simple Storage Service (Amazon S3) bucket and dynamic content from an application load balancer. The user base is spread across the world and latency should be minimized for a better user experience.

Which technology/service can help access the static and dynamic content while keeping the data latency low?

+ Use CloudFront's Lambda@Edge feature to server data from S3 buckets and load balancer programmatically on-the-fly
+ Configure CloudFront with multiple origins to serve both static and dynamic content at low latency to global users
+ Use Global Accelerator to transparently switch between S3 bucket and load balancer for different data needs
+ Use CloudFront's Origin Groups to group both static and dynamic requests into one request for further processing

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
CloudFront could serve both static and dynamic content.
</details>

<br>

---

You are storing your video files in a separate S3 bucket than your main static website in an S3 bucket. When accessing the video URLs directly the users can view the videos on the browser, but they can't play the videos while visiting the main website.

What is the root cause of this problem?

+ Enable CORS
+ Change the bucket policy
+ Amend the IAM policy
+ Disable Server-Side Encryption

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company developed an app-based service for citizens to book transportation rides in the local community. The platform is running on AWS EC2 instances and uses Amazon Relational Database Service (RDS) for storing transportation data. A new feature has been requested where receipts would be emailed to customers with PDF attachments retrieved from Amazon Simple Storage Service (S3).

Which of the following options will provide EC2 instances with the right permissions to upload files to Amazon S3 and generate S3 Signed URL?

+ CloudFormation
+ EC2 User Data
+ Run `aws configure` on the EC2 instance
+ Create an IAM role for EC2

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

Your company has been hired to build a resilient mobile voting app for an upcoming music award show that expects to have 5 to 20 million viewers. The mobile voting app will be marketed heavily months in advance so you are expected to handle millions of messages in the system. You are configuring Amazon Simple Queue Service (SQS) queues for your architecture that should receive messages from 20 KB to 200 KB.

Is it possible to send these messages to SQS?

+ Yes, the max message size is 512KB
+ Yes, the max message size is 256KB
+ No, the max message size is 128KB
+ No, the max message size is 64KB

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
1byte - 256KB
</details>

<br>

---

You are getting ready for an event to show off your Alexa skill written in JavaScript. As you are testing your voice activation commands you find that some intents are not invoking as they should and you are struggling to figure out what is happening. You included the following code `console.log(JSON.stringify(this.event))` in hopes of getting more details about the request to your Alexa skill.

You would like the logs stored in an Amazon Simple Storage Service (S3) bucket named `MyAlexaLog`. How do you achieve this?

+ Use CloudWatch integration feature with Kinesis
+ Use CloudWatch integration feature with S3
+ Use CloudWatch integration feature with Lambda
+ Use CloudWatch integration feature with Glue

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

You have a Java-based application running on EC2 instances loaded with AWS CodeDeploy agents. You are considering different options for deployment, one is the flexibility that allows for incremental deployment of your new application versions and replaces existing versions in the EC2 instances. The other option is a strategy in which an Auto Scaling group is used to perform a deployment.

Which of the following options will allow you to deploy in this manner? (Select two)

+ Cattle Deployment
+ Warm Standby Deployment
+ In-place Deployment
+ Blue/green Deployment
+ Pilot Light Deployment

<details close>
<summary>Answer</summary>
c,d
</details>

<br>

---

DevOps engineers are developing an order processing system where notifications are sent to a department whenever an order is placed for a product. The system also pushes identical notifications of the new order to a processing module that would allow EC2 instances to handle the fulfillment of the order. In the case of processing errors, the messages should be allowed to be re-processed at a later stage. The order processing system should be able to scale transparently without the need for any manual or programmatic provisioning of resources.

Which of the following solutions can be used to address this use-case?

+ SNS + Kinesis
+ SNS + SQS
+ SNS + Lambda
+ SQS + SES

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

You are planning to build a fleet of EBS-optimized EC2 instances to handle the load of your new application. Due to security compliance, your organization wants any secret strings used in the application to be encrypted to prevent exposing values as clear text.

The solution requires that decryption events be audited and API calls to be simple. How can this be achieved? (select two)

+ Encrypt first with KMS then store in SSM Parameter store
+ Store the secret as SecureString in SSM Parameter Store
+ Store the secret as PlainText in SSM Parameter Store
+ Audit using CloudTrail
+ Audit using SSM Audit Trail

<details close>
<summary>Answer</summary>
b,d
</details>

<br>

---

A .NET developer team works with many ASP.NET web applications that use EC2 instances to host them on IIS. The deployment process needs to be configured so that multiple versions of the application can run in AWS Elastic Beanstalk. One version would be used for development, testing, and another version for load testing.

Which of the following methods do you recommend?


+ Create an Application Load Balancer to route based on hostname so you can pass on parameters to the development Elastic Beanstalk environment. Create a file in .ebextensions/ to know how to handle the traffic coming from the ALB
+ You cannot have multiple development environments in Elastic Beanstalk, just one development and one production environment
+ Use only one Beanstalk environment and perform configuration changes using an Ansible script
+ Define a dev environment with a single instance and a 'load test' environment that has settings close to production environment

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

You work as a developer doing contract work for the government on AWS gov cloud. Your applications use Amazon Simple Queue Service (SQS) for its message queue service. Due to recent hacking attempts, security measures have become stricter and require you to store data in encrypted queues.

Which of the following steps can you take to meet your requirements without making changes to the existing code?

+ Use Secrets Manager
+ Use the SSL endpoint
+ Use Client side encryption
+ Enable SQS KMS encryption

<details close>
<summary>Answer</summary>
d
</details>

<br>


<details close>
<summary>Note</summary>
SQS KMS => transmite sensitive data in encrypted queues
SSL endpoint => SSL is for encrpyted during transit. 
</details>

<br>

---
You are designing a high-performance application that requires millions of connections. You have several EC2 instances running Apache2 web servers and the application will require capturing the user’s source IP address and source port without the use of X-Forwarded-For.

Which of the following options will meet your needs?

+ Application Load Balancer
+ Network Load Balancer
+ Elastic Load Balancer
+ Classic Load Balancer

<details close>
<summary>Answer</summary>
b
</details>

<br>

---
Your company leverages Amazon CloudFront to provide content via the internet to customers with low latency. Aside from latency, security is another concern and you are looking for help in enforcing end-to-end connections using HTTPS so that content is protected.

Which of the following options is available for HTTPS in AWS CloudFront?

+ Between clients and CloudFront only
+ Between clients and CloudFront as well as between CloudFront and backend
+ Between CloudFront and backend only
+ Neither between clients and CloudFront nor between CloudFront and backend

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company would like to migrate the existing application code from a GitHub repository to AWS CodeCommit.

As an AWS Certified Developer Associate, which of the following would you recommend for migrating the cloned repository to CodeCommit over HTTPS?

+ Use Git credentials generated from IAM 
+ Use IAM Multi-Factor authentication
+ Use authentication offered by GitHub secure tokens
+ Use IAM user secret access key and access key ID

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A development team is storing sensitive customer data in S3 that will require encryption at rest. The encryption keys must be rotated at least annually.

What is the easiest way to implement a solution for this requirement?

+ Encrypt the data before sending it to Amazon S3
+ Use AWS KMS with automatic key rotation
+ Import a custom key into AWS KMS and automate the key rotation on an annual basis by using a Lambda function
+ Use SSE-C with automatic key rotation on an annual basis


<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A firm maintains a highly available application that receives HTTPS traffic from mobile devices and web browsers. The main Developer would like to set up the Load Balancer routing to route traffic from web servers to smart.com/api and from mobile devices to smart.com/mobile. A developer advises that the previous recommendation is not needed and that requests should be sent to api.smart.com and mobile.smart.com instead.

Which of the following routing options were discussed in the given use-case? (select two)

+ Path based
+ Cookie value
+ Client IP
+ Web browser version
+ Host based

<details close>
<summary>Answer</summary>
a,e
</details>

<br>

---

You have a popular three-tier web application that is used by users throughout the globe receiving thousands of incoming requests daily. You have AWS Route 53 policies to automatically distribute weighted traffic to the API resources located at URL api.global.com.

What is an alternative way of distributing traffic to a web application?

+ S3
+ CloudFront
+ ELB
+ Auto Scaling

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

You have been hired at a company that needs an experienced developer to help with a continuous integration/continuous delivery (CI/CD) workflow on AWS. You configure the company’s workflow to run an AWS CodePipeline pipeline whenever the application’s source code changes in a repository hosted in AWS Code Commit and compiles source code with AWS Code Build. You are configuring ProjectArtifacts in your build stage.

Which of the following should you do?

+ Configure AWS CodeBuild to store output artifacts on EC2 servers
+ Give AWS CodeBuild permissions to upload the build output to your Amazon S3 bucket
+ Give AWS CodeCommit permissions to upload the build output to your Amazon S3 bucket
+ Contact AWS Support to allow AWS CodePipeline to manage build outputs

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

Your company manages MySQL databases on EC2 instances to have full control. Applications on other EC2 instances managed by an ASG make requests to these databases to get information that displays data on dashboards viewed on mobile phones, tablets, and web browsers.

Your manager would like to scale your Auto Scaling group based on the number of requests per minute. How can you achieve this?

+ You create a CloudWatch custom metric and build an alarm to scale your ASG
+ Attach an Elastic Load Balancer
+ Attach additional Elastic File Storage
+ You enable detailed monitoring and use that to scale your ASG

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

Your mobile application needs to perform API calls to DynamoDB. You do not want to store AWS secret and access keys onto the mobile devices and need all the calls to DynamoDB made with a different identity per mobile device.

Which of the following services allows you to achieve this?

+ Cognito Identity Pools
+ Cognito User Pools
+ Cognito Sync
+ IAM

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

You are revising options that would be best for monitoring a few EC2 instances you currently manage. Amazon CloudWatch has metrics available to monitor your EC2 instances for CPU load, I/O, and network I/O. Your budget does not allow for spending on monitoring so using the default monitoring available is your preferred choice.

With default monitoring, at what interval will these metrics be collected?

+ 1 minutes
+ 10 minutes
+ 2 minutes
+ 5 minutes

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

Your organization is looking into making a change to all virtual machines in the cloud. They would like to take advantage of running a bootstrap script for their Windows Server 2012 Base AMI virtual machines when they first boot.

Which of the following options will allow the organization to achieve this?

+ Custom AMI
+ Mount EFS network drives
+ EC2 Meta Data
+ EC2 User Data

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

Your company is in the process of building a DevOps culture and is moving all of its on-premise resources to the cloud using serverless architectures and automated deployments. You have created a CloudFormation template in YAML that uses an AWS Lambda function to pull HTML files from GitHub and place them into an Amazon Simple Storage Service (S3) bucket that you specify.

Which of the following AWS CLI commands can you use to upload AWS Lambda functions and AWS CloudFormation templates to AWS?

+ `cloudformation package` and `cloudformation deploy`
+ `cloudformation package` and `cloudformation upload`
+ `cloudformation zip` and `cloudformation upload`
+ `cloudformation zip` and `cloudformation deploy`

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
zip and upload do not exist
</details>

<br>

---

Your AWS CodeDeploy deployment to T2 instances succeed. The new application revision makes API calls to Amazon S3 however the application is not working as expected due to authorization exceptions and you were assigned to troubleshoot the issue.

Which of the following should you do?

+ Fix the IAM permissions for the CodeDeploy service role
+ Fix the IAM permissions for the EC2 instance role
+ Make the S3 bucket public
+ Enable CodeDeploy Proxy

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A financial services company with over 10,000 employees has hired you as the new Senior Developer. Initially caching was enabled to reduce the number of calls made to all API endpoints and improve the latency of requests to the company’s API Gateway.

For testing purposes, you would like to invalidate caching for the API clients to get the most recent responses. Which of the following should you do?

+ Using the request parameter ?cache-control-max-age=0
+ Use the Request parameter: ?bypass_cache=1
+ Using the Header Bypass-Cache=1
+ Using the Header Cache-Control: max-age=0


<details close>
<summary>Answer</summary>
d
</details>

<br>

---

As a Full-stack Web Developer, you are involved with every aspect of a company’s platform from development with PHP and JavaScript to the configuration of NoSQL databases with Amazon DynamoDB. You are not concerned about your response receiving stale data from your database and need to perform 16 eventually consistent reads per second of 12 KB in size each.

How many read capacity units (RCUs) do you need?

+ 12
+ 192
+ 24
+ 48

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

Your company stores confidential data on an Amazon Simple Storage Service (S3) bucket. New security compliance guidelines require that files be stored with server-side encryption. The encryption used must be Advanced Encryption Standard (AES-256) and the company does not want to manage S3 encryption keys.

Which of the following options should you use?
+ SSE-S3
+ SSE-C
+ Client Side Encryption
+ SSE-KMS

<details close>
<summary>Answer</summary>
a
</details>

<br>



