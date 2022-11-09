# Exam#2 Practice Set
The development team at a HealthCare company has deployed EC2 instances in AWS Account A. These instances need to access patient data with Personally Identifiable Information (PII) on multiple S3 buckets in another AWS Account B.

As a Developer Associate, which of the following solutions would you recommend for the given use-case?

+ Copy the underlying AMI for the EC2 instances from Account A into Account B. Launch EC2 instances in Account B using this AMI and then access the PII data on Amazon S3 in Account B
+ Add a bucket policy to all the Amazon S3 buckets in Account B to allow access from EC2 instances in Account A
+ Create an IAM role (instance profile) in Account A and set Account B as a trusted entity. Attach this role to the EC2 instances in Account A and add an inline policy to this role to access S3 data from Account B
+ Create an IAM role with S3 access in Account B and set Account A as a trusted entity. Create another role (instance profile) in Account A and attach it to the EC2 instances in Account A and add an inline policy to this role to assume the role from Account B

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

The app development team at a social gaming mobile app wants to simplify the user sign up process for the app. The team is looking for a fully managed scalable solution for user management in anticipation of the rapid growth that the app foresees.

As a Developer Associate, which of the following solutions would you suggest so that it requires the LEAST amount of development effort?

+ Create a custom solution using EC2 and DynamoDB to facilitate sign up and user management for the mobile app
+ Create a custom solution using Lambda and DynamoDB to facilitate sign up and user management for the mobile app
+ Use Cognito Identity pools to facilitate sign up and user management for the mobile app
+ Use Cognito User pools to facilitate sign up and user management for the mobile app

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

The development team at a retail company is gearing up for the upcoming Thanksgiving sale and wants to make sure that the application's serverless backend running via Lambda functions does not hit latency bottlenecks as a result of the traffic spike.

As a Developer Associate, which of the following solutions would you recommend to address this use-case?


+ Configure Application Auto Scaling to manage Lambda reserved concurrency on a schedule
+ Add an Application Load Balancer in front of the Lambda functions
+ No need to make any special provisions as Lambda is automatically scalable because of its serverless nature
+ Configure Application Auto Scaling to manage Lambda provisioned concurrency on a schedule

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

The development team at an analytics company is using SQS queues for decoupling the various components of application architecture. As the consumers need additional time to process SQS messages, the development team wants to postpone the delivery of new messages to the queue for a few seconds.

As a Developer Associate, which of the following solutions would you recommend to the development team?
+ Use FIFO queues to postpone the delivery of new messages to the queue for a few seconds
+ Use dead-letter queues to postpone the delivery of new messages to the queue for a few seconds
+ Use visibility timeout to postpone the delivery of new messages to the queue for a few seconds
+ Use delay queues to postpone the delivery of new messages to the queue for a few seconds

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

Other than the `Resources` section, which of the following sections in a Serverless Application Model (SAM) Template is mandatory?
+ Parameters
+ Mappings
+ Globals
+ Transform

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A data analytics company is processing real-time Internet-of-Things (IoT) data via Kinesis Producer Library (KPL) and sending the data to a Kinesis Data Streams driven application. The application has halted data processing because of a ProvisionedThroughputExceeded exception.

Which of the following actions would help in addressing this issue? (Select two)
+ Configure the data producer to retry with an exponential backoff
+ Increase the number of shards within your data streams to provide enough capacity
+ Use Amazon Kinesis Agent instead of Kinesis Producer Library (KPL) for sending data to Kinesis Data Streams
+ Use Amazon SQS instead of Kinesis Data Streams
+ Use Kinesis enhanced fan-out for Kinesis Data Streams

<details close>
<summary>Answer</summary>
a,b
</details>

<br>

---

The development team at an e-commerce company completed the last deployment for their application at a reduced capacity because of the deployment policy. The application took a performance hit because of the traffic spike due to an on-going sale.

Which of the following represents the BEST deployment option for the upcoming application version such that it maintains at least the FULL capacity of the application and MINIMAL impact of failed deployment?

+ Deploy the new application version using 'All at once' deployment policy
+ Deploy the new application version using 'Rolling' deployment policy
+ Deploy the new application version using 'Immutable' deployment policy
+ Deploy the new application version using 'Rolling with additional batch' deployment policy

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A social gaming application supports the transfer of gift vouchers between users. When a user hits a certain milestone on the leaderboard, they earn a gift voucher that can be redeemed or transferred to another user. The development team wants to ensure that this transfer is captured in the database such that the records for both users are either written successfully with the new gift vouchers or the status quo is maintained.

Which of the following solutions represent the best-fit options to meet the requirements for the given use-case? (Select two)

+ Perform DynamoDB read and write operations with ConsistentRead parameter set to true
+ Complete both operations on Amazon RedShift in a single transaction block
+ Use the Amazon Athena transactional read and write APIs on the table items as a single, all-or-nothing operation
+ Use the DynamoDB transactional read and write APIs on the table items as a single, all-or-nothing operation
+ Complete both operations on RDS MySQL in a single transaction block

<details close>
<summary>Answer</summary>
d,e
</details>

<br>

---

The technology team at an investment bank uses DynamoDB to facilitate high-frequency trading where multiple trades can try and update an item at the same time.

Which of the following actions would make sure that only the last updated value of any item is used in the application

+ Use ConsistentRead = true while doing GetItem operation for any item
+ Use ConsistentRead = true while doing UpdateItem operation for any item
+ Use ConsistentRead = true while doing PutItem operation for any item
+ Use ConsistentRead = false while doing PutItem operation for any item

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

The development team at a multi-national retail company wants to support trusted third-party authenticated users from the supplier organizations to create and update records in specific DynamoDB tables in the company's AWS account.

As a Developer Associate, which of the following solutions would you suggest for the given use-case?

+ Create a new IAM user in the company's AWS account for each of the third-party authenticated users from the supplier organizations. The users can then use the IAM user credentials to access DynamoDB
+ Create a new IAM group in the company's AWS account for each of the third-party authenticated users from the supplier organizations. The users can then use the IAM group credentials to access DynamoDB
+ Use Cognito Identity pools to enable trusted third-party authenticated users to access DynamoDB
+ Use Cognito User pools to enable trusted third-party authenticated users to access DynamoDB

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A developer wants to package the code and dependencies for the application-specific Lambda functions as container images to be hosted on Amazon Elastic Container Registry (ECR).

Which of the following options are correct for the given requirement? (Select two)

+ Lambda supports both Windows and Linux-based container images
+ To deploy a container image to Lambda, the container image must implement the Lambda Runtime API
+ You can test the containers locally using the Lambda Runtime API
+ You can deploy Lambda function as a container image, with a maximum size of 15 GB
+ You must create the Lambda function from the same account as the container registry in Amazon ECR

<details close>
<summary>Answer</summary>
b,e
</details>

<br>

---

A development team is building a game where players can buy items with virtual coins. For every virtual coin bought by a user, both the players table as well as the items table in DynamodDB need to be updated simultaneously using an all-or-nothing operation.

As a developer associate, how will you implement this functionality?

+ Use `BatchWriteItem`  API to update multiple tables simultaneously
+ Capture the transactions in the players table using DynamoDB streams and then sync with the items table
+ Use `TransactWriteItems`  API of DynamoDB Transactions
+ Capture the transactions in the items table using DynamoDB streams and then sync with the players table

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A CRM application is hosted on Amazon EC2 instances with the database tier using DynamoDB. The customers have raised privacy and security concerns regarding sending and receiving data across the public internet.

As a developer associate, which of the following would you suggest as an optimal solution for providing communication between EC2 instances and DynamoDB without using the public internet?
+ The firm can use a virtual private network (VPN) to route all DynamoDB network traffic through their own corporate network infrastructure
+ Configure VPC endpoints for DynamoDB that will provide required internal access without using public internet
+ Create a NAT Gateway to provide the necessary communication channel between EC2 instances and DynamoDB
+ Create an Internet Gateway to provide the necessary communication channel between EC2 instances and DynamoDB

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company uses Amazon Simple Email Service (SES) to cost-effectively send susbscription emails to the customers. Intermittently, the SES service throws the error: `Throttling – Maximum sending rate exceeded`.

As a developer associate, which of the following would you recommend to fix this issue?

+ Configure Timeout mechanism for each request made to the SES service
+ Use Exponential Backoff technique to introduce delay in time before attempting to execute the operation again
+ Raise a service request with Amazon to increase the throttling limit for the SES API
+ Implement retry mechanism for all 4xx errors to avoid throttling error

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

Signing AWS API requests helps AWS identify an authentic user from a potential threat.

As a developer associate, which of the following would you identify as the use-case where you need to sign the API requests?

+ When you send HTTP requests to an AWS service
+ When you send anonymous requests to Amazon Simple Storage Service (Amazon S3)
+ When you use the AWS Command Line Interface (AWS CLI) to run commands on an AWS resource
+ When you use one of the AWS SDKs to make requests to AWS resources/services

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
When you send anonymous requests to Amazon Simple Storage Service (Amazon S3) - Anonymous requests made to Amazon S3 resources need not be signed. Some API operations in AWS Security Token Service (AWS STS) are exempt from signing too.
</details>

<br>

---

A pharmaceutical company uses Amazon EC2 instances for application hosting and Amazon CloudFront for content delivery. A new research paper with critical findings has to be shared with a research team that is spread across the world.

Which of the following represents the most optimal solution to address this requirement without compromising the security of the content?

+ Use CloudFront signed cookies feature to control access to the file
+ Configure AWS Web Application Firewall (WAF) to monitor and control the HTTP and HTTPS requests that are forwarded to CloudFront
+ Use CloudFront signed URL feature to control access to the file
+ Using CloudFront's Field-Level Encryption to help protect sensitive data


<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A developer is defining the signers that can create signed URLs for their Amazon CloudFront distributions.

Which of the following statements should the developer consider while defining the signers? (Select two)

+ When you create a signer, the public key is with CloudFront and private key is used to sign a portion of URL
+ When you use the root user to manage CloudFront key pairs, you can only have up to two active CloudFront key pairs per AWS account
+ You can also use AWS Identity and Access Management (IAM) permissions policies to restrict what the root user can do with CloudFront key pairs
+ CloudFront key pairs can be created with any account that has administrative permissions and full access to CloudFront resources
+ Both the signers (trusted key groups and CloudFront key pairs) can be managed using the CloudFront APIs

<details close>
<summary>Answer</summary>
a,b
</details>

<br>

---

An e-commerce company uses AWS CloudFormation to implement Infrastructure as Code for the entire organization. Maintaining resources as stacks with CloudFormation has greatly reduced the management effort needed to manage and maintain the resources. However, a few teams have been complaining of failing stack updates owing to out-of-band fixes running on the stack resources.

Which of the following is the best solution that can help in keeping the CloudFormation stack and its resources in sync with each other?

+ Use CloudFormation in Elastic Beanstalk environment to reduce direct changes to CloudFormation resources
+ Use Tag feature of CloudFormation to monitor the changes happening on specific resources
+ Use Drift Detection feature of CloudFormation
+ Use Change Sets feature of CloudFormation

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company wants to automate its order fulfillment and inventory tracking workflow. Starting from order creation to updating inventory to shipment, the entire process has to be tracked, managed and updated automatically.

Which of the following would you recommend as the most optimal solution for this requirement?
+ Use Amazon Simple Queue Service (Amazon SQS) queue to pass information from order management to inventory tracking workflow
+ Configure Amazon EventBridge to track the flow of work from order management to inventory tracking systems
+ Use Amazon SNS to develop event-driven applications that can share information
+ Use AWS Step Functions to coordinate and manage the components of order management and inventory tracking workflow

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

While defining a business workflow as state machine on AWS Step Functions, a developer has configured several states.

Which of the following would you identify as the state that represents a single unit of work performed by a state machine?

```json
"HelloWorld": {
  "Type": "Task",
  "Resource": "arn:aws:lambda:us-east-1:123456789012:function:HelloFunction",
  "Next": "AfterHelloWorldState",
  "Comment": "Run the HelloWorld Lambda function"
}
```

```json
"wait_until" : {
  "Type": "Wait",
  "Timestamp": "2016-03-14T01:59:00Z",
  "Next": "NextState"
}

```

```json
"No-op": {
  "Type": "Task",
  "Result": {
    "x-datum": 0.381018,
    "y-datum": 622.2269926397355
  },
  "ResultPath": "$.coords",
  "Next": "End"
}
```

```json
"FailState": {
  "Type": "Fail",
  "Cause": "Invalid response.",
  "Error": "ErrorA"
}
```

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

An Auto Scaling group has a maximum capacity of 3, a current capacity of 2, and a scaling policy that adds 3 instances.

When executing this scaling policy, what is the expected outcome?

+ Amazon EC2 Auto Scaling adds 3 instances to the group
+ Amazon EC2 Auto Scaling adds 3 instances to the group and scales down 2 of those instances eventually
+ Amazon EC2 Auto Scaling adds only 1 instance to the group
+ Amazon EC2 Auto Scaling does not add any instances to the group, but suggests changing the scaling policy to add one instance


<details close>
<summary>Answer</summary>
c
</details>

<br>

---

You are a developer handling a deployment service that automates application deployments to Amazon EC2 instances. Most of the deployments consist of code, but sometimes web and configuration files. One of your deployments failed and was rolled back by AWS CodeDeploy to the last known good application revision.

During rollback which of the following instances did AWS CodeDeploy deploy first to?

+ To the non-failed instances
+ To the failed instances
+ To the failed instances
+ You cannot rollback a CodeDeploy deployment

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
To the failed instances: AWS CodeDeploy rolls back deployments by redeploying a previously deployed revision of an application as a new deployment on the failed instances.
</details>

<br>

---

As an AWS certified developer associate, you are working on an AWS CloudFormation template that will create resources for a company's cloud infrastructure. Your template is composed of three stacks which are Stack-A, Stack-B, and Stack-C. Stack-A will provision a VPC, a security group, and subnets for public web applications that will be referenced in Stack-B and Stack-C.

After running the stacks you decide to delete them, in which order should you do it?

+ Stack B, then Stack C, then Stack A
+ Stack A, then Stack B, then Stack C
+ Stack A, Stack C then Stack B
+ Stack C then Stack A then Stack B

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

Your company has embraced cloud-native microservices architectures. New applications must be dockerized and stored in a registry service offered by AWS. The architecture should support dynamic port mapping and support multiple tasks from a single service on the same container instance. All services should run on the same EC2 instance.

Which of the following options offers the best-fit solution for the given use-case?

+ Application Load Balancer + ECS
+ Classic Load Balancer + Beanstalk
+ Application Load Balancer + Beanstalk
+ Classic Load Balancer + ECS

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A team lead has asked you to create an AWS CloudFormation template that creates EC2 instances and RDS databases. The template should be reusable by allowing the user to input a parameter value for an Amazon EC2 AMI ID.

Which of the following intrinsic function should you choose to reference the parameter?

+ `!Param`
+ `!GetAtt`
+ `!Ref`
+ `!Join`

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A Developer is configuring Amazon EC2 Auto Scaling group to scale dynamically.

Which metric below is NOT part of Target Tracking Scaling Policy?
+ ASGAverageCPUUtilization
+ ApproximateNumberOfMessagesVisible
+ ASGAverageNetworkOut
+ ALBRequestCountPerTarget

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

You are a developer working on a web application written in Java and would like to use AWS Elastic Beanstalk for deployment because it would handle deployment, capacity provisioning, load balancing, auto-scaling, and application health monitoring. In the past, you connected to your provisioned instances through SSH to issue configuration commands. Now, you would like a configuration mechanism that automatically applies settings for you.

Which of the following options would help do this?

+ Use SSM parameter store as an input to your Elastic Beanstalk Configurations
+ Deploy a CloudFormation wrapper
+ Include config files in `.ebextensions/` at the root of your source code
+ Use an AWS Lambda hook

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
SSM is not suppported for Elastic Beanstalk
</details>

<br>

---

A development team has configured their Amazon EC2 instances for Auto Scaling. A Developer during routine checks has realized that only basic monitoring is active, as opposed to detailed monitoring.

Which of the following represents the best root-cause behind the issue?

+ AWS Management Console might have been used to create the launch configuration
+ AWS CLI was used to create the launch configuration
+ SDK was used to create the launch configuration
+ The default configuration for Auto Scaling was not set

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A new recruit is trying to configure what an Amazon EC2 should do when it interrupts a Spot Instance.

Which of the below CANNOT be configured as an interruption behavior?
+ Stop the Spot Instance
+ Hibernate the Spot Instance
+ Terminate the Spot Instance
+ Reboot the Spot Instance

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

You are an administrator for a video-on-demand web application where content creators upload videos directly into S3. Recent support requests from customers state that uploading video files near 500GB size causes the website to break. After doing some investigation you find the following error: 'Your proposed upload exceeds the maximum allowed size'.

What must you do to solve this error?

+ Your IAM permissions are incorrect
+ The maximum file size is 5 GB
+ You need to use multi-part upload for large files
+ You need to place a service limit request increase with AWS

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A media publishing company is using Amazon EC2 instances for running their business-critical applications. Their IT team is looking at reserving capacity apart from savings plans for the critical instances.

As a Developer Associate, which of the following reserved instance types you would select to provide capacity reservations?

+ Regional Reserved Instances
+ Both Regional Reserved Instances and Zonal Reserved Instances
+ Neither Regional Reserved Instances nor Zonal Reserved Instances
+ Zonal Reserved Instances

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
Regional Reserved Instances do not hace capacity reservation
</details>

<br>

---

Recently in your organization, the AWS X-Ray SDK was bundled into each Lambda function to record outgoing calls for tracing purposes. When your team leader goes to the X-Ray service in the AWS Management Console to get an overview of the information collected, they discover that no data is available.

What is the most likely reason for this issue?

+ X-Ray only works with AWS Lambda aliases
+ Enable X-Ray sampling
+ Fix the IAM Role
+ Change the security group rules

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

You are a development team lead setting permissions for other IAM users with limited permissions. On the AWS Management Console, you created a dev group where new developers will be added, and on your workstation, you configured a developer profile. You would like to test that this user cannot terminate instances.

Which of the following options would you execute?
+ Using the CLI, create a dummy EC2 and delete it using another CLI call
+ Use the AWS CLI --test option
+ Retrieve the policy using the EC2 metadata service and use the IAM policy simulator
+ Use the AWS CLI --dry-run option

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A business has purchased one m4.xlarge Reserved Instance but it has used three m4.xlarge instances concurrently for an hour.

As a Developer, explain how the instances are charged?

+ One instance is charged at one hour of Reserved Instance usage and the other two instances are charged at two hours of On-Demand usage
+ All instances are charged at one hour of Reserved Instance usage
+ All instances are charged at one hour of On-Demand Instance usage
+ One instance is charged at one hour of On-Demand usage and the other two instances are charged at two hours of Reserved Instance usage

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A business has their test environment built on Amazon EC2 configured on General purpose SSD volume.

At which gp2 volume size will their test environment hit the max IOPS?

+ 10.6 TiB
+ 5.3 TiB
+ 16 TiB
+ 2.7 TiB

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
The performance of gp2 volumes is tied to volume size, which determines the baseline performance level of the volume and how quickly it accumulates I/O credits; larger volumes have higher baseline performance levels and accumulate I/O credits faster.

5.3 TiB - General Purpose SSD (gp2) volumes offer cost-effective storage that is ideal for a broad range of workloads. These volumes deliver single-digit millisecond latencies and the ability to burst to 3,000 IOPS for extended periods of time. Between a minimum of 100 IOPS (at 33.33 GiB and below) and a maximum of 16,000 IOPS (at 5,334 GiB and above), baseline performance scales linearly at 3 IOPS per GiB of volume size.
</details>

<br>

---

A pharmaceutical company runs their database workloads on Provisioned IOPS SSD (io1) volumes.

As a Developer Associate, which of the following options would you identify as an INVALID configuration for io1 EBS volume types?
+ 200 GiB size volume with 2000 IOPS
+ 200 GiB size volume with 10000 IOPS
+ 200 GiB size volume with 15000 IOPS
+ 200 GiB size volume with 5000 IOPS

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

An Accounting firm extensively uses Amazon EBS volumes for persistent storage of application data of Amazon EC2 instances. The volumes are encrypted to protect the critical data of the clients. As part of managing the security credentials, the project manager has come across a policy snippet that looks like the following:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Allow for use of this Key",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::111122223333:role/UserRole"
            },
            "Action": [
                "kms:GenerateDataKeyWithoutPlaintext",
                "kms:Decrypt"
            ],
            "Resource": "*"
        },
        {
            "Sid": "Allow for EC2 Use",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::111122223333:role/UserRole"
            },
            "Action": [
                "kms:CreateGrant",
                "kms:ListGrants",
                "kms:RevokeGrant"
            ],
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                "kms:ViaService": "ec2.us-west-2.amazonaws.com"
            }
        }
    ]
}
```

+ The first statement provides the security group the ability to generate a data key and decrypt that data key from the CMK when necessary
+ The second statement in this policy provides the security group (mentioned in first statement of the policy), the ability to create, list, and revoke grants for Amazon EC2
+ The first statement provides a specified IAM principal the ability to generate a data key and decrypt that data key from the CMK when necessary
+ The second statement in the policy mentions that all the resources stated in the first statement can take the specified role which will provide the ability to create, list, and revoke grants for Amazon EC2

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

The Development team at a media company is working on securing their databases.

Which of the following AWS database engines can be configured with IAM Database Authentication? (Select two)
+ RDS Oracle
+ Aurora
+ RDS MySQL
+ RDS PostGreSQL
+ RDS Sequel Server

<details close>
<summary>Answer</summary>
c,d
</details>

<br>

---

A developer in your company was just promoted to Team Lead and will be in charge of code deployment on EC2 instances via AWS CodeCommit and AWS CodeDeploy. Per the new requirements, the deployment process should be able to change permissions for deployed files as well as verify the deployment success.

Which of the following actions should the new Developer take?

+ Define an `appspec.yml`  file in the codebuild/ directory
+ Define a `buildspec.yml` file in the root directory
+ Define a `buildspec.yml` file in the codebuild/ directory
+ Define an `appspec.yml` file in the root directory

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A university has created a student portal that is accessible through a smartphone app and web application. The smartphone app is available in both Android and IOS and the web application works on most major browsers. Students will be able to do group study online and create forum questions. All changes made via smartphone devices should be available even when offline and should synchronize with other devices.

Which of the following AWS services will meet these requirements?

+ BeanStalk
+ Cognito Identity Pools
+ Cognito Sync
+ Cognito User Pools

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
Amazon Cognito Sync is an AWS service and client library that enables cross-device syncing of application-related user data. You can use it to synchronize user profile data across mobile devices and the web without requiring your own backend. The client libraries cache data locally so your app can read and write data regardless of device connectivity status. When the device is online, you can synchronize data, and if you set up push sync, notify other devices immediately that an update is available.

Incorrect options:
</details>

<br>

---

As an AWS Certified Developer Associate, you have been hired to work with the development team at a company to create a REST API using the serverless architecture.

Which of the following solutions will you choose to move the company to the serverless architecture paradigm?


+ API Gateway exposing Lambda Functionality
+ Fargate with Lambda at the front
+ Public-facing Application Load Balancer with ECS on Amazon EC2
+ Route 53 with EC2 as backend

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A developer needs to automate software package deployment to both Amazon EC2 instances and virtual servers running on-premises, as part of continuous integration and delivery that the business has adopted.

Which AWS service should he use to accomplish this task?

+ AWS CodePipeline
+ AWS CodeBuild
+ AWS Elastic Beanstalk
+ AWS CodeDeploy

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A company needs a version control system for their fast development lifecycle with incremental changes, version control, and support to existing Git tools.

Which AWS service will meet these requirements?
+ AWS CodePipeline
+ Amazon Versioned S3 Bucket
+ AWS CodeCommit
+ AWS CodeBuild

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

As a senior architect, you are responsible for the development, support, maintenance, and implementation of all database applications written using NoSQL technology. A new project demands a throughput requirement of 10 strongly consistent reads per second of 6KB in size each.

How many read capacity units will you need when configuring your DynamoDB table?

+ 10 
+ 60
+ 30
+ 20

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

As a Senior Developer, you are tasked with creating several API Gateway powered APIs along with your team of developers. The developers are working on the API in the development environment, but they find the changes made to the APIs are not reflected when the API is called.

As a Developer Associate, which of the following solutions would you recommend for this use-case?
+ Developers need IAM permissions on API execution component of API Gateway
+ Enable Lambda authorizer to access API
+ Use Stage Variables for development state of API
+ Redeploy the API to an existing stage or to a new stage

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A developer working with EC2 Windows instance has installed Kinesis Agent for Windows to stream JSON-formatted log files to Amazon Simple Storage Service (S3) via Amazon Kinesis Data Firehose. The developer wants to understand the sink type capabilities of Kinesis Firehose.

Which of the following sink types is NOT supported by Kinesis Firehose.

+ Amazon Elasticsearch Service (Amazon ES) with optionally backing up data to Amazon S3
+ Amazon Simple Storage Service (Amazon S3) as a direct Firehose destination
+ Amazon Redshift with Amazon S3
+ Amazon ElastiCache with Amazon S3 as backup

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
Amazon ElastiCache with Amazon S3 as backup - Amazon ElastiCache is a fully managed in-memory data store, compatible with Redis or Memcached. ElastiCache is NOT a supported destination for Amazon Kinesis Data Firehose.

</details>

<br>

---

A startup has been experimenting with DynamoDB in its new test environment. The development team has discovered that some of the write operations have been overwriting existing items that have the specified primary key. This has messed up their data, leading to data discrepancies.

Which DynamoDB write option should be selected to prevent this kind of overwriting?

+ Batch writes
+ Conditional writes
+ Atomic Counters
+ Use Scan operation

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A development team is working on an AWS Lambda function that accesses DynamoDB. The Lambda function must do an upsert, that is, it must retrieve an item and update some of its attributes or create the item if it does not exist.

Which of the following represents the solution with MINIMUM IAM permissions that can be used for the Lambda function to achieve this functionality?

+ dynamodb:AddItem, dynamodb:GetItem
+ dynamodb:UpdateItem, dynamodb:GetItem
+ dynamodb:GetRecords, dynamodb:PutItem, dynamodb:UpdateTable
+ dynamodb:UpdateItem, dynamodb:GetItem, dynamodb:PutItem

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company is using a Border Gateway Protocol (BGP) based AWS VPN connection to connect from its on-premises data center to Amazon EC2 instances in the company’s account. The development team can access an EC2 instance in subnet A but is unable to access an EC2 instance in subnet B in the same VPC.

Which logs can be used to verify whether the traffic is reaching subnet B?

+ VPN logs
+ Subnet logs
+ VPC Flow Logs
+ BGP logs

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

Your team lead has asked you to learn AWS CloudFormation to create a collection of related AWS resources and provision them in an orderly fashion. You decide to provide AWS-specific parameter types to catch invalid values.

When specifying parameters which of the following is not a valid Parameter type?

+ String
+ DependentParameter
+ CommaDelimitedList
+ AWS::EC2::KeyPair::KeyName

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company runs its flagship application on a fleet of Amazon EC2 instances. After misplacing a couple of private keys from the SSH key pairs, they have decided to re-use their SSH key pairs for the different instances across AWS Regions.

As a Developer Associate, which of the following would you recommend to address this use-case?
+ It is not possible to reuse SSH key pairs across AWS Regions
+ Store the public and private SSH key pair in AWS Trusted Advisor and access it across AWS Regions
+ Generate a public SSH key from a private SSH key. Then, import the key into each of your AWS Regions
+ Encrypt the private SSH key and store it in the S3 bucket to be accessed from any AWS Region


<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
Here is the correct way of reusing SSH keys in your AWS Regions:

Generate a public SSH key (.pub) file from the private SSH key (.pem) file.

Set the AWS Region you wish to import to.

Import the public SSH key into the new Region.
</details>

<br>

---

While troubleshooting, a developer realized that the Amazon EC2 instance is unable to connect to the Internet using the Internet Gateway.

Which conditions should be met for Internet connectivity to be established? (Select two)
+ The instance's subnet is not associated with any route table
+ The network ACLs associated with the subnet must have rules to allow inbound and outbound traffic
+ The instance's subnet is associated with multiple route tables with conflicting configurations
+ The route table in the instance’s subnet should have a route to an Internet Gateway
+ The subnet has been configured to be Public and has no access to the internet

<details close>
<summary>Answer</summary>
b,d
</details>

<br>

---

You have launched several AWS Lambda functions written in Java. A new requirement was given that over 1MB of data should be passed to the functions and should be encrypted and decrypted at runtime.

Which of the following methods is suitable to address the given use-case?

+ Use KMS direct encryption and store as file
+ Use Envelope Encryption and reference the data as file within the code
+ Use Envelope Encryption and store as environment variable
+ Use KMS Encryption and store as environment variable

<details close>
<summary>Answer</summary>
b
</details>

<br>

<details close>
<summary>Note</summary>
While AWS KMS does support sending data up to 4 KB to be encrypted directly, envelope encryption can offer significant performance benefits. When you encrypt data directly with AWS KMS it must be transferred over the network. Envelope encryption reduces the network load since only the request and delivery of the much smaller data key go over the network. The data key is used locally in your application or encrypting AWS service, avoiding the need to send the entire block of data to AWS KMS and suffer network latency.

AWS Lambda environment variables can have a maximum size of 4 KB. Additionally, the direct 'Encrypt' API of KMS also has an upper limit of 4 KB for the data payload. To encrypt 1 MB, you need to use the Encryption SDK and pack the encrypted file with the lambda function.
</details>

<br>

---

You have created a continuous delivery service model with automated steps using AWS CodePipeline. Your pipeline uses your code, maintained in a CodeCommit repository, AWS CodeBuild, and AWS Elastic Beanstalk to automatically deploy your code every time there is a code change. However, the deployment to Elastic Beanstalk is taking a very long time due to resolving dependencies on all of your 100 target EC2 instances.

Which of the following actions should you take to improve performance with limited code changes?

+ Store the dependencies in S3, to be used while deploying to Beanstalk
+ Bundle the dependencies in the source code in CodeCommit
+ Bundle the dependencies in the source code during the build stage of CodeBuild
+ Create a custom platform for Elastic Beanstalk

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A developer is looking at establishing access control for an API that connects to a Lambda function downstream.

Which of the following represents a mechanism that CANNOT be used for authenticating with the API Gateway?

+ Standard AWS IAM roles and policies
+ AWS Security Token Service (STS)
+ Lambda Authorizer
+ Cognito User Pools

<details close>
<summary>Answer</summary>
b
</details>

<br>


<details close>
<summary>Note</summary>
AWS Security Token Service (AWS STS) is a web service that enables you to request temporary, limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that you authenticate (federated users). However, it is not supported by API Gateway.
</details>

<br>

---

A company uses AWS CodeDeploy to deploy applications from GitHub to EC2 instances running Amazon Linux. The deployment process uses a file called appspec.yml for specifying deployment hooks. A final lifecycle event should be specified to verify the deployment success.

Which of the following hook events should be used to verify the success of the deployment?
+ ValidateService
+ AfterInstall
+ ApplicationStart
+ AllowTraffic

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company has created an Amazon S3 bucket that holds customer data. The team lead has just enabled access logging to this bucket. The bucket size has grown substantially after starting access logging. Since no new files have been added to the bucket, the perplexed team lead is looking for an answer.

Which of the following reasons explains this behavior?

+ Erroneous Bucket policies for batch uploads can sometimes be responsible for the exponential growth of S3 Bucket size
+ A DDoS attack on your S3 bucket can potentially blow up the size of data in the bucket if the bucket security is compromised during the attack
+ Object Encryption has been enabled and each object is stored twice as part of this configuration
+ S3 access logging is pointing to the same bucket and is responsible for the substantial growth of bucket size

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A diagnostic lab stores its data on DynamoDB. The lab wants to backup a particular DynamoDB table data on Amazon S3, so it can download the S3 backup locally for some operational use.

Which of the following options is NOT feasible?

+ Use AWS Data Pipeline to export your table to an S3 bucket in the account of your choice and download locally
+ Use Hive with Amazon EMR to export your data to an S3 bucket and download locally
+ Use AWS Glue to copy your table to Amazon S3 and download locally
+ Use the DynamoDB on-demand backup capability to write to Amazon S3 and download locally

<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
DynamoDB has two built-in backup methods (On-demand, Point-in-time recovery) that write to Amazon S3, but you will not have access to the S3 buckets that are used for these backups.
</details>

<br>

---

An application running on EC2 instances processes messages from an SQS queue. However, sometimes the messages are not processed and they end up in errors. These messages need to be isolated for further processing and troubleshooting.

Which of the following options will help achieve this?

+ Increase the VisibilityTimeout
+ Use DeleteMessage
+ Reduce the VisibilityTimeout
+ Implement a Dead-Letter Queue

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

As a Team Lead, you are expected to generate a report of the code builds for every week to report internally and to the client. This report consists of the number of code builds performed for a week, the percentage success and failure, and overall time spent on these builds by the team members. You also need to retrieve the CodeBuild logs for failed builds and analyze them in Athena.

Which of the following options will help achieve this?

+ Use CloudWatch Events
+ Use AWS Lambda integration
+ Enable S3 and CloudWatch Logs integration
+ Use AWS CloudTrail and deliver logs to S3

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

After a code review, a developer has been asked to make his publicly accessible S3 buckets private, and enable access to objects with a time-bound constraint.

Which of the following options will address the given use-case?

+ Use Bucket policy to block the unintended access
+ Share pre-signed URLs with resources that need access
+ Use Routing policies to re-route unintended access
+ It is not possible to implement time constraints on Amazon S3 Bucket access

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A developer with access to the AWS Management Console terminated an instance in the us-east-1a availability zone. The attached EBS volume remained and is now available for attachment to other instances. Your colleague launches a new Linux EC2 instance in the us-east-1e availability zone and is attempting to attach the EBS volume. Your colleague informs you that it is not possible and need your help.

Which of the following explanations would you provide to them?
+ The required IAM permissions are missing
+ EBS volumes are region locked
+ EBS volumes are AZ locked
+ The EBS volume is encrypted

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
When you create an EBS volume, it is automatically replicated within its Availability Zone to prevent data loss due to the failure of any single hardware component. You can attach an EBS volume to an EC2 instance in the same Availability Zone.
</details>

<br>

---

As a Developer, you are given a document written in YAML that represents the architecture of a serverless application. The first line of the document contains `Transform: 'AWS::Serverless-2016-10-31'`.

What does the `Transform` section in the document represent?

+ It represents a Lambda function definition
+ It represents an intrinsic function
+ Presence of `Transform` section indicates it is a Serverless Application Model (SAM) template
+ Presence of `Transform` section indicates it is a CloudFormation Parameter

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

You create an Auto Scaling group to work with an Application Load Balancer. The scaling group is configured with a minimum size value of 5, a maximum value of 20, and the desired capacity value of 10. One of the 10 EC2 instances has been reported as unhealthy.

Which of the following actions will take place?

+ The ASG will terminate the EC2 Instance
+ The ASG will detach the EC2 instance from the group, and leave it running
+ The ASG will keep the instance running and re-start the application
+ The ASG will format the root EBS drive on the EC2 instance and run the User Data again

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
To maintain the same number of instances, Amazon EC2 Auto Scaling performs a periodic health check on running instances within an Auto Scaling group. When it finds that an instance is unhealthy, it terminates that instance and launches a new one. Amazon EC2 Auto Scaling creates a new scaling activity for terminating the unhealthy instance and then terminates it. Later, another scaling activity launches a new instance to replace the terminated instance.
</details>

<br>

---

A company has a cloud system in AWS with components that send and receive messages using SQS queues. While reviewing the system you see that it processes a lot of information and would like to be aware of any limits of the system.

Which of the following represents the maximum number of messages that can be stored in an SQS queue?


+ no limit
+ 10000
+ 100000
+ 1000000

<details close>
<summary>Answer</summary>
a
</details>

<br>

<details close>
<summary>Note</summary>
"no limit": There are no message limits for storing in SQS, but 'in-flight messages' do have limits. Make sure to delete messages after you have processed them. There can be a maximum of approximately 120,000 inflight messages (received from a queue by a consumer, but not yet deleted from the queue).
</details>

<br>









