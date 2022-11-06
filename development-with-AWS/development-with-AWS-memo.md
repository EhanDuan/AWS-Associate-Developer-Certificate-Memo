# Development with AWS Services Practice Set (Selections from top to bottom as a,b,c,d)

**Q1. The team wants AWS Account A's Lambda function to AWS Account B's DynamoDB table. Which of the following solutions would you recommend?**
+ Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account

+ Add a resource policy to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A

+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the role in Account B to allow the execution role of Lambda to assume this role. Update the Lambda function code to add the AssumeRole API call

+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssumeRole API call


<details close>
<summary>Answer</summary>
c
</details>

<br>

Note
+ Execution Role: The primary role in account A that gives Lambda function perimissions to do its work
+ Assume Role: A role in account B that Lambda function in account A assumes to gain access to cross-account resources

Source: https://aws.amazon.com/premiumsupport/knowledge-center/lambda-function-assume-iam-role/

---

**Q2. The team wants to run a serverless data store service on two docker containers that share resources. Which of the following ECS configurations can be used to facilitate this use-case?**
+ Put the two containers into a single task definition using a Fargate Launch Type
+ Put the two containers into two separate task definitions using a Fargate Launch Type
+ Put the two containers into two separate task definitions using a Fargate Launch Type
+ Put the two containers into a single task definition using an EC2 Launch Type

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note: Single task will share the resources.
<br>
Source: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/application_architecture.html


**Q3. The team uses CloudFormation to manage its AWS infrastructure. They has a network stack containing a VPC with subnets and a web application stack with EC2 instances and an RDS instance. The team wants to reference the VPC created in the network stack into its web application stack. Which of the following solutions would you recommend for the given use-case?**
+ Create a cross-stack reference and use the Outputs output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
+ Create a cross-stack reference and use the Outputs output field to flag the value of VPC from the network stack. Then use Ref intrinsic function to reference the value of VPC into the web application stack
+ Create a cross-stack reference and use the Export output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
+ Create a cross-stack reference and use the Export output field to flag the value of VPC from the network stack. Then use Ref intrinsic function to reference the value of VPC into the web application stack

<details close>
<summary>Answer</summary>
c
</details>
<br>
Note: Key words: export and import.

Source: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/walkthrough-crossstackref.html

**Q4. An application has its EC2 server fleet running behind an Application Load Balancer and the traffic is fronted by a CloudFront distribution. The team wants to decouple the user authentication process for the application so that the application servers can just focus on the business logic. Which of the following solutions would you recommend to address this use-case with minimal development effort?**

+ Use Cognito Authentication via Cognito User Pools for your Application Load Balancer
+ Use Cognito Authentication via Cognito Identity Pools for your Application Load Balancer
+ Use Cognito Authentication via Cognito User Pools for your CloudFront distribution
+ Use Cognito Authentication via Cognito Identity Pools for your CloudFront distribution

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note:
+ Cognito User Pools is for users. Identity pools is for developers
+ Cognito cannot directly used with CloudFront

Source: 
+ https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-authenticate-users.html
+ https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html
+ https://aws.amazon.com/blogs/networking-and-content-delivery/authorizationedge-using-cookies-protect-your-amazon-cloudfront-content-from-being-downloaded-by-unauthenticated-users/

**Q5. A video encoding application running on an EC2 instance takes about 20 seconds on average to process each raw footage file. The application picks the new job messages from an SQS queue. The development team needs to account for the use-case when the video encoding process takes longer than usual so that the same raw footage is not processed by multiple consumers. Which of the following solutions would you recommend to address this use-case?**
+ Use ChangeMessageVisibility action to extend a message's visibility timeout
+ Use DelaySeconds action to delay a message's visibility timeout
+ Use WaitTimeSeconds action to short poll and extend a message's visibility timeout
+ Use WaitTimeSeconds action to long poll and extend a message's visibility timeout

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note:
+ Avoid multiple consumers => extend visibility timeout

Source: 
+ https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html
+ https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_ChangeMessageVisibility.html

**Q6. The development team at an IT company has configured an Application Load Balancer (ALB) with a Lambda function A as the target but the Lambda function A is not able to process any request from the ALB. Upon investigation, the team finds that there is another Lambda function B in the AWS account that is exceeding the concurrency limits. How can the development team address this issue?**

+ Set up provisioned concurrency for the Lambda function B so that it throttles if it goes above a certain concurrency limit
+ Set up reserved concurrency for the Lambda function B so that it throttles if it goes above a certain concurrency limit
+ Use an API Gateway instead of an Application Load Balancer (ALB) for Lambda function A
+ Use a Cloudfront Distribution instead of an Application Load Balancer (ALB) for Lambda function A

<details close>
<summary>Answer</summary>
b
</details>
<br>

Note:
+ reversed: I have my own quota, others cannot grab mine. I would also not influence others.

Source: 
+ https://docs.aws.amazon.com/lambda/latest/dg/configuration-concurrency.html#configuration-concurrency-reserved
+ https://aws.amazon.com/blogs/networking-and-content-delivery/lambda-functions-as-targets-for-application-load-balancers/

---

**Q7. A company has a fleet of EC2 based web servers running into very high CPU utilization issues. The team has determined that serving secure traffic via HTTPS is a major contributor to the high CPU load. Which of the following steps can take the high CPU load off the web servers? (Select two)**
+ Create an HTTP listener on the Application Load Balancer with SSL termination
+ Configure an SSL/TLS certificate on an Application Load Balancer via AWS Certificate Manager (ACM)
+ Create an HTTPS listener on the Application Load Balancer with SSL termination
+ Create an HTTPS listener on the Application Load Balancer with SSL pass-through
+ Create an HTTP listener on the Application Load Balancer with SSL pass-through

<details close>
<summary>Answer</summary>
b,c
</details>
<br>

Note:
+ pass-through: traffic still hit the fleet
+ termination: HTTPS will stop here

Source:
+ https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html
+ https://aws.amazon.com/premiumsupport/knowledge-center/associate-acm-certificate-alb-nlb/

---
**Q8. An IT company has a HealthCare application with data security requirements such that the encryption key must be stored in a custom application running on-premises. The company wants to offload the data storage as well as the encryption process to Amazon S3 but continue to use the existing encryption keys.
Which of the following S3 encryption options allows the company to leverage Amazon S3 for storing data with given constraints?**

+ Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3)
+ Server-Side Encryption with Customer Master Keys (CMKs) Stored in AWS Key Management Service (SSE-KMS)
+ Server-Side Encryption with Customer-Provided Keys (SSE-C)
+ Client-Side Encryption with data encryption is done on the client-side before sending it to Amazon S3

<details close>
<summary>Answer</summary>
c
</details>
<br>

Note:
+ SSE-S3: use AES-256 to encrypt data. It is AWS-managed keys.
+ CMKs + SSE-KMS: Customer master keys. Provides an audit trail that shows when CMK was used and by whom.
+ SSE-C: customer provide keys. You managed keys and AWS managed encrpytion.

Source: https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html

---

**Q9. A data analytics company wants to use clickstream data for Machine Learning tasks, develop algorithms, and create visualizations and dashboards to support the business stakeholders. Each of these business units works independently and would need real-time access to this clickstream data for their applications.**

**As a Developer Associate, which of the following AWS services would you recommend such that it provides a highly available and fault-tolerant solution to capture the clickstream events from the source and then provide a simultaneous feed of the data stream to the consumer applications?**

+ AWS Kinesis Data Streams
+ AWS Kinesis Data Firehose
+ AWS Kinesis Data Analytics
+ Amazon SQS

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note: 
+ Kinesis Data Streams: scalable and durable real-time data streaming service
+ Kinesis Data Firehose: load streaming data into data stores and analytics tools
+ Kinesis Data Analytics: analyze streaming data in real-time

Source:
+ https://aws.amazon.com/kinesis/data-streams/faqs/
+ https://aws.amazon.com/kinesis/data-firehose/faqs/
+ https://aws.amazon.com/kinesis/data-analytics/faqs/

---



**You're a developer for 'Movie Gallery', a company that just migrated to the cloud. A database must be created using NoSQL technology to hold movies that are listed for public viewing. You are taking an important step in designing the database with DynamoDB and need to choose the appropriate partition key.**

**Which of the following unique attributes satisfies this requirement?**

+ lead_actor_name
+ producer_name
+ movie_id
+ movie_language

<details close>
<summary>Answer</summary>
c
</details>
<br>

---

**A company wants to automate the creation of ECS clusters using CloudFormation. The process has worked for a while, but after creating task definitions and assigning roles, the development team discovers that the tasks for containers are not using the permissions assigned to them.**

**Which ECS config must be set in /etc/ecs/ecs.config to allow ECS tasks to use IAM roles?**

+ `ECS_AVAILABLE_LOGGING_DRIVERS`
+ `ECS_ENGINE_AUTH_DATA`
+ `ECS_ENABLE_TASK_IAM_ROLE`
+ `ECS_CLUSTER`

<details close>
<summary>Answer</summary>
c
</details>
<br>

<p hidden>6-11</p>

---

**As an AWS Certified Developer Associate, you are writing a CloudFormation template in YAML. The template consists of an EC2 instance creation and one RDS resource. Once your resources are created you would like to output the connection endpoint for the RDS database.**

**Which intrinsic function returns the value needed?**

+ <code>!Sub</code>
+ <code>!ref</code>
+ `!GetAtt`
+ `!FindInMap`

<details close>
<summary>Answer</summary>
c
</details>
<br>

<p hidden>6-12</p>

---

**You are a developer working at a cloud company that embraces serverless. You have performed your initial deployment and would like to work towards adding API Gateway stages and associate them with existing deployments. Your stages will include prod, test, and dev and will need to match a Lambda function variant that can be updated over time.**

**Which of the following features must you add to achieve this? (select two)**

+ Lambda X-Ray integration
+ Stage Variables
+ Lambda Versions
+ Lambda Aliases
+ Mapping Templates

<details close>
<summary>Answer</summary>
b,d
</details>
<br>

<p hidden>6-13</p>

---

<p hidden>6-14</p>

**A company has AWS Lambda functions where each is invoked by other AWS services such as Amazon Kinesis Data Firehose, Amazon API Gateway, Amazon Simple Storage Service, or Amazon CloudWatch Events. What these Lambda functions have in common is that they process heavy workloads such as big data analysis, large file processing, and statistical computations**

**What should you do to improve the performance of your AWS Lambda functions without changing your code?**

+ Change the instance type for your Lambda function
+ Increase the RAM assigned to your Lambda function
+ Change your Lambda function runtime to use Golang
+ Increase the Lambda function timeout

<details close>
<summary>Answer</summary>
b
</details>
<br>

Note: Heavy workloads => RAM

Source: https://docs.aws.amazon.com/lambda/latest/dg/configuration-console.html

---
<p hidden>6-15</p>

**A cyber forensics application, running behind an ALB, wants to analyze patterns for the client IPs.**

**Which of the following headers can be used for this requirement?**


+ X-Forwarded-Proto
+ X-Forwarded-Port
+ X-Forwarded-IP
+ X-Forwarded-For

<details close>
<summary>Answer</summary>
d
</details>
<br>

---
<p hidden>6-16</p>

**A new recruit is trying to understand the nuances of EC2 Auto Scaling. As an AWS Certified Developer Associate, you have been asked to mentor the new recruit.**

**Can you identify and explain the correct statements about Auto Scaling to the new recruit? (Select two).**
+ EC2 Auto Scaling groups are regional constructs. They span across Availability Zones and AWS regions
+ Amazon EC2 Auto Scaling cannot add a volume to an existing instance if the existing volume is approaching capacity
+ Every time you create an Auto Scaling group from an existing instance, it creates a new AMI (Amazon Machine Image)
+ Amazon EC2 Auto Scaling works with both Application Load Balancers and Network Load Balancers
+ You cannot use Amazon EC2 Auto Scaling for health checks (to replace unhealthy instances) if you are not using Elastic Load Balancing (ELB)


<details close>
<summary>Answer</summary>
b,d
</details>
<br>

---
<p hidden>6-17</p>

**A company that specializes in cloud communications platform as a service allows software developers to programmatically use their services to send and receive text messages. The initial platform did not have a scalable architecture as all components were hosted on one server and should be redesigned for high availability and scalability.**

**Which of the following options can be used to implement the new architecture? (select two)**

+ ALB + ECS
+ EBS + RDS
+ SES + S3
+ CloudWatch + CloudFront
+ API Gateway + Lambda

<details close>
<summary>Answer</summary>
a,e
</details>
<br>

---
<p hidden>6-18</p>

**As an AWS Certified Developer Associate, you have been hired to consult with a company that uses the NoSQL database for mobile applications. The developers are using DynamoDB to perform operations such as GetItem but are limited in knowledge. They would like to be more efficient with retrieving some attributes rather than all.**

**Which of the following recommendations would you provide?**

+ Use a `FilterExpression`
+ Specify a `ProjectionExpression`
+ Use the `--query` parameter
+ Use a `scan`

<details close>
<summary>Answer</summary>
b
</details>
<br>

---
<p hidden>6-19</p>


**A developer at a university is encrypting a large XML payload transferred over the network using AWS KMS and wants to test the application before going to production.**

**What is the maximum data size supported by AWS KMS?**

+ 16KB
+ 1MB
+ 10MB
+ 4KB

<details close>
<summary>Answer</summary>
d
</details>
<br>

Note: You can encrypt up to 4 kilobytes (4096 bytes) of arbitrary data such as an RSA key, a database password, or other sensitive information.

---
<p hidden>6-20</p>

**As a Developer, you are working on a mobile application that utilizes Amazon Simple Queue Service (SQS) for sending messages to downstream systems for further processing. One of the requirements is that the messages should be stored in the queue for a period of 12 days.**

**How will you configure this requirement?**

+ Enable Long Polling for the SQS queue
+ The maximum retention period of SQS messages is 7 days, therefore retention period of 12 days is not possible
+ Change the queue message retention setting
+ Use a FIFO SQS queue

<details close>
<summary>Answer</summary>
c
</details>
<br>

Note: Default SQS retention : 4 days. Available Range: 60s - 14 days.

---
<p hidden>6-21</p>

**A company uses microservices-based infrastructure to process the API calls from clients, perform request filtering and cache requests using the AWS API Gateway. Users report receiving 501 error code and you have been contacted to find out what is failing.**

**Which service will you choose to help you troubleshoot?**

+ Use CloudTrail service
+ Use API Gateway service
+ Use CloudWatch service
+ Use X-Ray service

<details close>
<summary>Answer</summary>
d
</details>
<br>

Note: Microservices debug => X-Ray

---
<p hidden>6-22</p>

**A Company uses a large set of EBS volumes for their fleet of Amazon EC2 instances. As an AWS Certified Developer Associate, your help has been requested to understand the security features of the EBS volumes. The company does not want to build or maintain their own encryption key management infrastructure.**

**Can you help them understand what works for Amazon EBS encryption? (Select two)**

+ Encryption by default is a Region-specific setting. If you enable it for a Region, you cannot disable it for individual volumes or snapshots in that Region
+ You can encrypt an existing unencrypted volume or snapshot by using AWS Key Management Service (KMS) AWS SDKs
+ A snapshot of an encrypted volume can be encrypted or unencrypted
+ A volume restored from an encrypted snapshot, or a copy of an encrypted snapshot is always encrypted
+ Encryption by default is an AZ specific setting. If you enable it for an AZ, you cannot disable it for individual volumes or snapshots in that AZ


<details close>
<summary>Answer</summary>
a, d
</details>
<br>

Source:
+ https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
+ https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html#encrypt-unencrypted

---

<p hidden>6-23</p>

**A multi-national company runs its technology operations on AWS Cloud. As part of their storage solution, they use a large number of EBS volumes, with AWS Config and CloudTrail activated. A manager has tried to find the user name that created an EBS volume by searching CloudTrail events logs but wasn't successful.**

**As a Developer Associate, which of the following would you recommend as the correct solution?**

+ AWS CloudTrail event logs for 'ManageVolume' aren't available for EBS volumes created during an Amazon EC2 launch
+ Amazon EBS CloudWatch metrics are disabled
+ AWS CloudTrail event logs for 'CreateVolume' aren't available for EBS volumes created during an Amazon EC2 launch
+ EBS volume status checks are disabled

<details close>
<summary>Answer</summary>
c
</details>
<br>

---

<p hidden>6-24</p>

**An AWS CodePipeline was configured to be triggered by Amazon CloudWatch Events. Recently the pipeline failed and upon investigation, the Team Lead noticed that the source was changed from AWS CodeCommit to Amazon Simple Storage Service (S3). The Team Lead has requested you to find the user who had made the changes.**

**Which service will help you solve this?**

+ Amazon CloudWatch
+ Amazon Inspector
+ AWS X-Ray
+ AWS CloudTrail

<details close>
<summary>Answer</summary>
d
</details>
<br>

---

<p hidden>6-25</p>

**You are a system administrator whose company recently moved its production application to AWS and migrated data from MySQL to AWS DynamoDB. You are adding new tables to AWS DynamoDB and need to allow your application to query your data by the primary key and an alternate sort key. This option must be added when first creating tables otherwise changes cannot be made afterward.**

**Which of the following actions should you take?**
+ Create a GSI
+ Call Scan
+ Create a LSI
+ Migrate away from DynamoDB

<details close>
<summary>Answer</summary>
C
</details>
<br>

Note: You cannot add a LSI to an existing table, which aligns with the peoroblem requirement.

---

<p hidden>6-26</p>

**An organization with high data volume workloads have successfully moved to DynamoDB after having many issues with traditional database systems. However, a few months into production, DynamoDB tables are consistently recording high latency.**

**As a Developer Associate, which of the following would you suggest to reduce the latency? (Select two)**

+ Increase the request timeout settings, so the client gets enough time to complete the requests, thereby reducing retries on the system
+ Consider using Global tables if your application is accessed by globally distributed users
+ Reduce connection pooling, which keeps the connections alive even when user requests are not present, thereby, blocking the services
+ Use eventually consistent reads in place of strongly consistent reads whenever possible
+ Use DynamoDB Accelerator (DAX) for businesses with heavy write-only workloads



<details close>
<summary>Answer</summary>
b,d
</details>
<br>

Note:
+ DAX: heavy read workload
+ DynamoDB has global tables (soulds like CDN-version DB)

Source:
+ https://aws.amazon.com/premiumsupport/knowledge-center/dynamodb-high-latency/

---

<p hidden>6-27</p>


**A multi-national company maintains separate AWS accounts for different verticals in their organization. The project manager of a team wants to migrate the Elastic Beanstalk environment from Team A's AWS account into Team B's AWS account. As a Developer, you have been roped in to help him in this process.**

**Which of the following will you suggest?**
 
+ Create a saved configuration in Team A's account and configure it to Export. Now, log into Team B's account and choose the Import option. Here, you need to specify the name of the saved configuration and allow the system to create the new application. This takes a little time based on the Regions the two accounts belong to
+ It is not possible to migrate Elastic Beanstalk environment from one AWS account to the other
+ Create an export configuration from the Elastic Beanstalk console from Team A's account. This configuration has to be shared with the IAM Role of Team B's account. The import option of Team B's account will show the saved configuration, that can be used to create a new Beanstalk application
+ Create a saved configuration in Team A's account and download it to your local machine. Make the account-specific parameter changes and upload to the S3 bucket in Team B's account. From Elastic Beanstalk console, create an application from 'Saved Configurations'


<details close>
<summary>Answer</summary>
d
</details>
<br>

Source:
+ https://aws.amazon.com/premiumsupport/knowledge-center/elastic-beanstalk-migration-accounts/

+ https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environment-configuration-savedconfig.html

---

<p hidden>6-28</p>

Your team-mate has configured an Amazon S3 event notification for an S3 bucket that holds sensitive audit data of a firm. As the Team Lead, you are receiving the SNS notifications for every event in this bucket. After validating the event data, you realized that few events are missing.

What could be the reason for this behavior and how to avoid this in the future?

+ If two writes are made to a single non-versioned object at the same time, it is possible that only a single event notification will be sent
+ Someone could have created a new notification configuration and that has overridden your existing configuration
+ Versioning is enabled on the S3 bucket and event notifications are getting fired for only one version
+ Your notification action is writing to the same bucket that triggers the notification


<details close>
<summary>Answer</summary>
a
</details>
<br>

Source:
+ https://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html

---

<p hidden>6-29</p>

A startup manages its Cloud resources with Elastic Beanstalk. The environment consists of few Amazon EC2 instances, an Auto Scaling Group (ASG), and an Elastic Load Balancer. Even after the Load Balancer marked an EC2 instance as unhealthy, the ASG has not replaced it with a healthy instance.

As a Developer, suggest the necessary configurations to automate the replacement of unhealthy instance.

+ Health check parameters were configured for checking the instance health alone. The instance failed because of application failure which was not configured as a parameter for health check status
+ The health check type of your instance's Auto Scaling group, must be changed from EC2 to ELB by using a configuration file
+ Auto Scaling group doesn't automatically replace the unhealthy instances marked by the load balancer. They have to be manually replaced from AWS Console
+ The ping path field of the Load Balancer is configured incorrectly

<details close>
<summary>Answer</summary>
b
</details>
<br>

Source:
https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-healthchecks.html

---

<p hidden>6-30</p>

An e-commerce company uses Amazon SQS queues to decouple their application architecture. The development team has observed message processing failures for an edge case scenario when a user places an order for a particular product ID, but the product ID is deleted, thereby causing the application code to fail.

As a Developer Associate, which of the following solutions would you recommend to address such message failures?

+ Use a temporary queue to handle message processing failures
+ Use a dead-letter queue to handle message processing failures
+ Use short polling to handle message processing failures
+ Use long polling to handle message processing failures

<details close>
<summary>Answer</summary>
b
</details>
<br>

Note: SQS error message => dead-letter queue

---
<p hidden>6-31</p>

You manage a group of developers that are experienced with the AWS SDK for Java. You have given them a requirement to build a state machine workflow where each state executes an AWS Lambda function written in Java. Data payloads of 1KB in size will be passed between states and should allow for two retry attempts if the state fails.

Which of the following options will assist your developers with this requirement?

+ AWS Step Functions
+ CloudWatch Rules
+ Amazon Simple Workflow Service
+ AWS ECS

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note: state machine workflow => Step Function

Source: https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html

---
<p hidden>6-32</p>

An analytics company is using Kinesis Data Streams (KDS) to process automobile health-status data from the taxis managed by a taxi ride-hailing service. Multiple consumer applications are using the incoming data streams and the engineers have noticed a performance lag for the data delivery speed between producers and consumers of the data streams.

As a Developer Associate, which of the following options would you suggest for improving the performance for the given use-case?

+ Swap out Kinesis Data Streams with SQS Standard queues
+ Swap out Kinesis Data Streams with SQS FIFO queues
+ Use Enhanced Fanout feature of Kinesis Data Streams
+ Swap out Kinesis Data Streams with Kinesis Data Firehose

<details close>
<summary>Answer</summary>
c
</details>
<br>

Note:
Amazon Kinesis Data Streams (KDS) is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources such as website clickstreams, database event streams, financial transactions, social media feeds, IT logs, and location-tracking events.

By default, the 2MB/second/shard output is shared between all of the applications consuming data from the stream. You should use enhanced fan-out if you have multiple consumers retrieving data from a stream in parallel. With enhanced fan-out developers can register stream consumers to use enhanced fan-out and receive their own 2MB/second pipe of read throughput per shard, and this throughput automatically scales with the number of shards in a stream.


Source: 
https://aws.amazon.com/blogs/aws/kds-enhanced-fanout/

---

<p hidden>6-33</p>

A company has configured an Auto Scaling group with health checks. The configuration is set to the desired capacity value of 3 and maximum capacity value of 3. The EC2 instances of your Auto Scaling group are configured to scale when CPU utilization is at 60 percent and is now running at 80 percent utilization.

Which of the following will take place?

+ System will trigger CloudWatch alarms to AWS support
+ The desired capacity will go up to 4 and the maximum capacity will stay at 3
+ The desired capacity will go up to 4 and the maximum capacity will also go up to 4
+ System will keep running as is


<details close>
<summary>Answer</summary>
d
</details>
<br>

Source:
https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html

---

<p hidden>6-34</p>

Your application sends messages to an Amazon Simple Queue Service (SQS) queue frequently, which are then polled by another application that specifies which message to retrieve.

Which of the following options describe the maximum number of messages that can be retrieved at one time?

+ 100
+ 5
+ 20
+ 10

<details close>
<summary>Answer</summary>
d
</details>
<br>

---

<p hidden>6-35</p>

You're a developer maintaining a web application written in .NET. The application makes references to public objects in a public S3 accessible bucket using a public URL. While doing a code review your colleague advises that the approach is not a best practice because some of the objects contain private data. After the administrator makes the S3 bucket private you can no longer access the S3 objects but you would like to create an application that will enable people to access some objects as needed with a time policy constraint.

Which of the following options will give access to the objects?

+ Using bucket policy
+ Using pre-signed URL
+ Using Routing Policy
+ Using IAM policy

<details close>
<summary>Answer</summary>
b
</details>
<br>

Note: 
All objects by default are private, with object owner having permission to access the objects. However, the object owner can optionally share objects with others by creating a pre-signed URL, using their own security credentials, to grant time-limited permission to download the objects.

Source: 
https://docs.aws.amazon.com/AmazonS3/latest/dev/ShareObjectPreSignedURL.html

---
<p hidden>6-36</p>

As a site reliability engineer, you work on building and running large-scale, distributed, fault-tolerant systems in the cloud using automation. You have just replaced the company's Jenkins based CI/CD platform with AWS CodeBuild and would like to programmatically define your build steps.

Which of the following options should you choose?

+ Define an `appspec.yml`  file in the root directory
+ Define an `buildspec.yml`  file in the root directory
+ Define an `buildspec.yml` file in the codebuild/ directory
+ Define an `appspec.yml` file in the codebuild/ director


<details close>
<summary>Answer</summary>
b
</details>
<br>

Note:
A `buildspec` is a collection of build commands and related settings, in YAML format, that CodeBuild uses to run a build.
If you include a `buildspec` as part of the source code, by default, the buildspec file must be named `buildspec.yml` and placed in the root of your source directory.

Source: https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html

---
<p hidden>6-37</p>
You are a software engineer working for an IT company and are asked to contribute to a growing internal application that includes dashboards for data visualization. You are provisioning your AWS DynamoDB table and need to perform 10 strongly consistent reads per second of 4 KB in size each.

How many Read Capacity Units (RCUs) are needed?

+ 10
+ 40
+ 20
+ 5

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note: strongly consistent read: ceiling(4 / 4) * 10 = 10;

---

<p hidden>6-38</p>

A development team has inherited a web application running in the us-east-1 region with three availability zones (us-east-1a, us-east1-b, and us-east-1c) whose incoming web traffic is routed by a load balancer. When one of the EC2 instances hosting the web application crashes, the team realizes that the load balancer continues to route traffic to that instance causing intermittent issues.

Which of the following should the development team do to minimize this problem?

+ Enable Health Checks
+ Enable Stickiness
+ Enable Multi-AZ deployments
+ Enable SSL

<details close>
<summary>Answer</summary>
a
</details>
<br>


---

<p hidden>6-39</p>

You are working for a technology startup building web and mobile applications. You would like to pull Docker images from the ECR repository called demo so you can start running local tests against the latest application version.

Which of the following commands must you run to pull existing Docker images from ECR? (Select two)

+ `docker pull 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`
+ `$(aws ecr get-login --no-include-email)`
+ `docker login -u $AWS_ACCESS_KEY_ID -p $AWS_SECRET_ACCESS_KEY`
+ `aws docker push 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`
+ `docker build -t 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`

<details close>
<summary>Answer</summary>
a,b
</details>
<br>

Source:
https://docs.aws.amazon.com/cli/latest/reference/ecr/get-login.html

---

<p hidden>6-40</p>

A video streaming application uses Amazon CloudFront for its data distribution. The development team has decided to use CloudFront with origin failover for high availability.

Which of the following options are correct while configuring CloudFront with Origin Groups? (Select two)

+ CloudFront routes all incoming requests to the primary origin, even when a previous request failed over to the secondary origin
+ When there’s a cache hit, CloudFront routes the request to the primary origin in the origin group
+ To set up origin failover, you must have a distribution with at least three origins
+ In the Origin Group of your distribution, all the origins are defined as primary for automatic failover in case an origin fails
+ CloudFront fails over to the secondary origin only when the HTTP method of the viewer request is GET, HEAD or OPTIONS


<details close>
<summary>Answer</summary>
a,e
</details>
<br>

Note:
+ cache hit: found in cache, no need to origin.
+ cache miss: not found in cache, find in primary orgin
+ Failover: most case, traffic goes to primary. CloudFront fails over to the secondary origin only when the HTTP method of the viewer request is GET, HEAD, or OPTIONS. 

Source: 
https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/high_availability_origin_failover.html

---

<p hidden>6-41</p>

An investment firm wants to continuously generate time-series analytics of the stocks being purchased by its customers. The firm wants to build a live leaderboard with near-real-time analytics for these in-demand stocks.

Which of the following represents a fully managed solution with the least cost to address this use-case?

+ Use Kinesis Data Streams to ingest data and Kinesis Data Analytics to generate leaderboard scores and time-series analytics
+ Use Kinesis Data Streams to ingest data and Amazon Kinesis Client Library to the application logic to generate leaderboard scores and time-series analytics
+ Use Kinesis Firehose to ingest data and Kinesis Data Analytics to generate leaderboard scores and time-series analytics
+ Use Kinesis Firehose to ingest data and Amazon Athena to generate leaderboard scores and time-series analytics

<details close>
<summary>Answer</summary>
c
</details>
<br>

Source:

+ https://docs.aws.amazon.com/firehose/latest/dev/data-analysis.html
+ https://aws.amazon.com/kinesis/data-analytics/faqs/
+ https://aws.amazon.com/kinesis/data-firehose/pricing/
+ https://aws.amazon.com/kinesis/data-streams/pricing/


---

<p hidden>6-42</p>

A development team is configuring Kinesis Data Streams for ingesting real-time data from various appliances. The team has declared a shard capacity of one to test the configuration.

What happens if the capacity limits of an Amazon Kinesis data stream are exceeded while the data producer adds data to the data stream?

+ The put data calls will be rejected with a `ProvisionedThroughputExceeded` exception
+ The put data calls will be rejected with a `AccessDeniedException` exception once the limit is reached 
+ Data is lost unless the partition key of the data records is changed in order to write data to a different shard in the stream
+ Contact AWS support to request an increase in the number of shards

<details close>
<summary>Answer</summary>
a
</details>
<br>

Source: https://aws.amazon.com/kinesis/data-streams/faqs/

---

<p hidden>6-43</p>

A development team has been using Amazon S3 service as an object store. With Amazon S3 turning strongly consistent, the team wants to understand the impact of this change on its data storage practices.

As a developer associate, can you identify the key characteristics of the strongly consistent data model followed by S3? (Select two)

+ If you delete a bucket and immediately list all buckets, the deleted bucket might still appear in the list
+ A process replaces an existing object and immediately tries to read it. Amazon S3 might return the old data
+ A process deletes an existing object and immediately tries to read it. Amazon S3 can return data as the object deletion has not yet propagated completely
+ A process deletes an existing object and immediately lists keys within its bucket. The object could still be visible for few more minutes till the change propagates
+ A process deletes an existing object and immediately tries to read it. Amazon S3 will not return any data as the object has been deleted


<details close>
<summary>Answer</summary>
a, e
</details>
<br>

Note: 
+ Bucket: eventual consistency
+ Object: strong consistency

Source:
https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html#ConsistencyModel

---
<p hidden>6-44</p>

A developer is configuring the redirect actions for an Application Load Balancer. The developer stumbled upon the following snippet of code.

Which of the following is an example of a query string condition that the developer can use on AWS CLI?

+ `[
  {
      "Field": "query-string",
      "PathPatternConfig": {
          "Values": ["/img/*"]
      }
  }
]`

+ `[
  {
      "Field": "query-string",
      "StringHeaderConfig": {
          "Values": ["*.example.com"]
      }
  }
]`

+ `[
  {
      "Field": "query-string",
      "QueryStringConfig": {
          "Values": [
            {
                "Key": "version",
                "Value": "v1"
            },
            {
                "Value": "*example*"
            }
          ]
      }
  }
]
`

+ `[
  {
      "Type": "redirect",
      "RedirectConfig": {
          "Protocol": "HTTPS",
          "Port": "443",
          "Host": "#{host}",
          "Path": "/#{path}",
          "Query": "#{query}",
          "StatusCode": "HTTP_301"
      }
  }
]
`

<details close>
<summary>Answer</summary>
c
</details>
<br>

Source:

https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html#query-string-conditions

---

<p hidden>6-45</p>

A developer has just completed configuring the Application Load Balancer for the EC2 instances. Just as he started testing his configuration, he realized that he has missed assigning target groups to his ALB.

Which error code should he expect in his debug logs?

+ HTTP 500
+ HTTP 503
+ HTTP 504
+ HTTP 403

<details close>
<summary>Answer</summary>
c
</details>
<br>

Note:
+ 500: Internal Service Error
+ 503: Service Unavailable Error
+ 504: Gateway Timeout Error
+ 403: Forbidden Error

Source: 
https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-troubleshooting.html

---

<p hidden>6-46</p>

A developer in your company has configured a build using AWS CodeBuild. The build fails and the developer needs to quickly troubleshoot the issue to see which commands or settings located in the BuildSpec file are causing an issue.

Which approach will help them accomplish this?

+ Freeze the CodeBuild during its next execution
+ SSH into the CodeBuild Docker container
+ Run AWS CodeBuild locally using CodeBuild Agent
+ Enable detailed monitoring

<details close>
<summary>Answer</summary>
c
</details>
<br>

Note:

AWS CodeBuild is a fully managed build service. There are no servers to provision and scale, or software to install, configure, and operate.

With the Local Build support for AWS CodeBuild, you just specify the location of your source code, choose your build settings, and CodeBuild runs build scripts for compiling, testing, and packaging your code. You can use the AWS CodeBuild agent to test and debug builds on a local machine.

Source: 
+ https://docs.aws.amazon.com/codebuild/latest/userguide/use-codebuild-agent.html
+ https://docs.aws.amazon.com/codebuild/latest/userguide/troubleshooting.html
+ https://aws.amazon.com/blogs/devops/announcing-local-build-support-for-aws-codebuild/

---

<p hidden>6-47</p>

A developer while working on Amazon EC2 instances, realized that an instance was not needed and had shut it down. But another instance of the same type automatically got launched in the account.

Which of the following options can attribute the given sequence of actions?

+ The user did not have the right permissions to shutdown the instance. User needs root permissions to terminate an instance
+ Instance might be part of Auto Scaling Group and hence re-launched similar instance
+ The instance could have been a part of Application Load Balancer and hence was automatically started
+ The instance could have been a part of Network Load Balancer and hence was automatically started

<details close>
<summary>Answer</summary>
b
</details>
<br>

---

<p hidden>6-48</p>

As a Developer Associate, you are responsible for the data management of the AWS Kinesis streams at your company. The security team has mandated stricter security requirements by leveraging mechanisms available with the Kinesis Data Streams service that won't require code changes on your end.

Which of the following features meet the given requirements? (Select two)

+ Envelope Encryption
+ SSE-C encryption
+ Encryption in flight with HTTPS endpoint
+ Client-Side Encryption
+ KMS encryption for data at rest

<details close>
<summary>Answer</summary>
c,e
</details>
<br>

Source:
https://docs.aws.amazon.com/streams/latest/dev/what-is-sse.html

---

<p hidden>6-49</p>

Your organization has developers that merge code changes regularly to an AWS CodeCommit repository. Your pipeline has AWS CodeCommit as the source and you would like to configure a rule that reacts to changes in CodeCommit.

Which of the following options do you choose for this type of integration?

+ Use CloudTrail Event rules with Amazon Simple Email Service (SES)
+ Use Lambda function with Amazon Simple Notification Service (SNS)
+ Use Lambda Event Rules
+ Use CloudWatch Event Rules


<details close>
<summary>Answer</summary>
d
</details>
<br>

Note: 
Amazon CloudWatch Events is a web service that monitors your AWS resources and the applications you run on AWS. You can use Amazon CloudWatch Events to detect and react to changes in the state of a pipeline, stage, or action. Then, based on rules you create, CloudWatch Events invokes one or more target actions when a pipeline, stage, or action enters the state you specify in a rule. Examples of Amazon CloudWatch Events rules and targets:

A rule that sends a notification when the instance state changes, where an EC2 instance is the event source, and Amazon SNS is the event target.

A rule that sends a notification when the build phase changes, where a CodeBuild configuration is the event source, and Amazon SNS is the event target.

A rule that detects pipeline changes and invokes an AWS Lambda function.

Source: 
https://docs.aws.amazon.com/codepipeline/latest/userguide/detect-state-changes-cloudwatch-events.html

---

<p hidden>6-50</p>

An e-commerce application writes log files into Amazon S3. The application also reads these log files in parallel on a near real-time basis. The development team wants to address any data discrepancies that might arise when the application overwrites an existing log file and then tries to read that specific log file.

Which of the following options BEST describes the capabilities of Amazon S3 relevant to this scenario?

+ A process replaces an existing object and immediately tries to read it. Until the change is fully propagated, Amazon S3 might return the previous data
+ A process replaces an existing object and immediately tries to read it. Until the change is fully propagated, Amazon S3 does not return any data
+ A process replaces an existing object and immediately tries to read it. Until the change is fully propagated, Amazon S3 might return the new data
+ A process replaces an existing object and immediately tries to read it. Amazon S3 always returns the latest version of the object

<details close>
<summary>Answer</summary>
d
</details>
<br>

---

<p hidden>6-51</p>

As a site reliability engineer, you are responsible for improving the company’s deployment by scaling and automating applications. As new application versions are ready for production you ensure that the application gets deployed to different sets of EC2 instances at different times allowing for a smooth transition.

Using AWS CodeDeploy, which of the following options will allow you to do this?

+ CodeDeploy Hooks
+ CodeDeploy Agent
+ CodeDeploy Deployment Groups
+ Define multiple CodeDeploy Applications

<details close>
<summary>Answer</summary>
c
</details>
<br>

Note: 
You can specify one or more deployment groups for a CodeDeploy application. The deployment group contains settings and configurations used during the deployment. Most deployment group settings depend on the compute platform used by your application. Some settings, such as rollbacks, triggers, and alarms can be configured for deployment groups for any compute platform.

In an EC2/On-Premises deployment, a deployment group is a set of individual instances targeted for deployment. A deployment group contains individually tagged instances, Amazon EC2 instances in Amazon EC2 Auto Scaling groups, or both.

Source:
https://docs.aws.amazon.com/codedeploy/latest/userguide/deployment-groups.html

---

<p hidden>6-52</p>

Your company has a load balancer in a VPC configured to be internet facing. The public DNS name assigned to the load balancer is `myDns-1234567890.us-east-1.elb.amazonaws.com`. When your client applications first load they capture the load balancer DNS name and then resolve the IP address for the load balancer so that they can directly reference the underlying IP.

It is observed that the client applications work well but unexpectedly stop working after a while. What is the reason for this?

+ The load balancer is highly available and its public IP may change. The DNS name is constant
+ Your security groups are not stable
+ You need to enable stickiness
+ You need to disable multi-AZ deployments

<details close>
<summary>Answer</summary>
a
</details>
<br>

Note:
When your load balancer is created, it receives a public DNS name that clients can use to send requests. The DNS servers resolve the DNS name of your load balancer to the public IP addresses of the load balancer nodes for your load balancer. Never resolve the IP of a load balancer as it can change with time. You should always use the DNS name.

Source:
https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-internet-facing-load-balancers.html

---

<p hidden>6-53</p>

A developer is creating a RESTful API service using an Amazon API Gateway with AWS Lambda integration. The service must support different API versions for testing purposes.

As a Developer Associate, which of the following would you suggest as the best way to accomplish this?

+ Use an X-Version header to identify which version is being called and pass that header to the Lambda function
+ Use an API Gateway Lambda authorizer to route API clients to the correct API version 
+ Set up an API Gateway resource policy to identify the API versions and provide context to the Lambda function
+ Deploy the API versions as unique stages with unique endpoints and use stage variables to provide the context to identify the API versions

<details close>
<summary>Answer</summary>
d
</details>
<br>

Note:

Stage variables are name-value pairs that you can define as configuration attributes associated with a deployment stage of a REST API. They act like environment variables and can be used in your API setup and mapping templates.

With deployment stages in API Gateway, you can manage multiple release stages for each API, such as alpha, beta, and production. Using stage variables you can configure an API deployment stage to interact with different backend endpoints.


Source: 
https://docs.aws.amazon.com/apigateway/latest/developerguide/stage-variables.html

https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-resource-policies.html

https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html

---

<p hidden>6-54</p>

A company wants to implement authentication for its new RESTful API service that uses Amazon API Gateway. To authenticate the calls, each request must include HTTP headers with a client ID and user ID. These credentials must be compared to the authentication data in a DynamoDB table.

As an AWS Certified Developer Associate, which of the following would you recommend for implementing this authentication in API Gateway?

+ Develop an AWS Lambda authorizer that references the authentication data in the DynamoDB table
+ Set up an API Gateway Model that requires the credentials, then grant API Gateway access to the authentication table in DynamoDB
+ Update the API Gateway integration requests to require the credentials, then grant API Gateway access to the authentication table in DynamoDB
+ Authorize using Amazon Cognito that will reference the authentication table of DynamoDB

<details close>
<summary>Answer</summary>
a
</details>
<br>


Note:
A Lambda authorizer is an API Gateway feature that uses a Lambda function to control access to your API.

---
<p hidden>6-55</p>

A development team has created AWS CloudFormation templates that are reusable by taking advantage of input parameters to name resources based on client names.

You would like to save your templates on the cloud, which storage option should you choose?

+ EFS
+ EBS
+ S3
+ ECR


<details close>
<summary>Answer</summary>
c
</details>
<br>

Note: EFS is not an option for CloudFormation templates file.

---
<p hidden>6-56</p>

Your e-commerce company needs to improve its software delivery process and is moving away from the waterfall methodology. You decided that every application should be built using the best CI/CD practices and every application should be packaged and deployed as a Docker container. The Docker images should be stored in ECR and pushed with AWS CodePipeline and AWS CodeBuild.

When you attempt to do this, the last step fails with an authorization issue. What is the most likely issue?

+ CodeBuild cannot talk to ECR because of security group issues
+ The ECR repository is stale, you must delete and re-create it
+ The IAM permissions are wrong for the CodeBuild service
+ The ECS instances are misconfigured and must contain additional data in /etc/ecs/ecs.config


<details close>
<summary>Answer</summary>
c
</details>
<br>

---
<p hidden>6-57</p>

You are a DynamoDB developer for an aerospace company that requires you to write 6 objects per second of 4.5KB in size each.

What write capacity unit is needed for your project?

+ 46
+ 24
+ 15
+ 30

<details close>
<summary>Answer</summary>
d
</details>
<br>

<details close>
<summary>Note</summary>
ceiling(4.5/1) * 6 = 30
</details>
<br>

---
<p hidden>6-58</p>

Your web application front end consists of 5 EC2 instances behind an Application Load Balancer. You have configured your web application to capture the IP address of the client making requests. When viewing the data captured you notice that every IP address being captured is the same, which also happens to be the IP address of the Application Load Balancer.

What should you do to identify the true IP address of the client?

+ Look into the X-Forwarded-Proto header in the backend
+ Modify the front-end of the website so that the users send their IP in the requests
+ Look into the X-Forwarded-For header in the backend
+ Look into the client's cookie

<details close>
<summary>Answer</summary>
c
</details>
<br>

---

<p hidden>6-59</p>

Your team has just signed up an year-long contract with a client maintaining a three-tier web application, that needs to be moved to AWS Cloud. The application has steady traffic throughout the day and needs to be on a reliable system with no down-time or access issues. The solution needs to be cost-optimal for this startup.

Which of the following options should you choose?

+ Amazon EC2 Spot Instances
+ Amazon EC2 On Demand Instances
+ Amazon EC2 Reserved Instances
+ On-premise EC2 instance

<details close>
<summary>Answer</summary>
c
</details>
<br>


<details close>
<summary>Note</summary>
One year long & steady traffic => reversed instances
</details>
<br>

---
<p hidden>6-60</p>

A development team has noticed that one of the EC2 instances has been wrongly configured with the 'DeleteOnTermination' attribute set to True for its root EBS volume.

As a developer associate, can you suggest a way to disable this flag while the instance is still running?

+ Set the `DeleteOnTermination` attribute to False using the command line 
+ Update the attribute using AWS management console. Select the EC2 instance and then uncheck the Delete On Termination check box for the root EBS volume
+ Set the `DisableApiTermination` attribute of the instance using the API
+ The attribute cannot be updated when the instance is running. Stop the instance from Amazon EC2 console and then update the flag

<details close>
<summary>Answer</summary>
c
</details>
<br>


<details close>
<summary>Note</summary>
If the instance is already running, you can set DeleteOnTermination to False using the command line.
</details>
<br>

---

<p hidden>6-61</p>

The development team at a health-care company is planning to migrate to AWS Cloud from the on-premises data center. The team is evaluating Amazon RDS as the database tier for its flagship application.

Which of the following would you identify as correct for RDS Multi-AZ? (Select two)

+ To enhance read scalability, a Multi-AZ standby instance can be used to serve read requests
+ RDS applies OS updates by performing maintenance on the standby, then promoting the standby to primary and finally performing maintenance on the old primary, which becomes the new standby
+ Amazon RDS automatically initiates a failover to the standby, in case primary database fails for any reason
+ For automated backups, I/O activity is suspended on your primary DB since backups are not taken from standby DB
+ Updates to your DB Instance are asynchronously replicated across the Availability Zone to the standby in order to keep both in sync

<details close>
<summary>Answer</summary>
b,c
</details>
<br>

<details close>
<summary>Note</summary>
Running a DB instance as a Multi-AZ deployment can further reduce the impact of a maintenance event because Amazon RDS applies operating system updates by following these steps:

Perform maintenance on the standby.

Promote the standby to primary.

Perform maintenance on the old primary, which becomes the new standby.

When you modify the database engine for your DB instance in a Multi-AZ deployment, then Amazon RDS upgrades both the primary and secondary DB instances at the same time. In this case, the database engine for the entire Multi-AZ deployment is shut down during the upgrade.

---

 You also benefit from enhanced database availability when running your DB instance as a Multi-AZ deployment. If an Availability Zone failure or DB instance failure occurs, your availability impact is limited to the time automatic failover takes to complete.

</details>
<br>

---

<p hidden>6-62</p>

A company stores confidential data on an Amazon Simple Storage Service (S3) bucket. New regulatory guidelines require that files be stored with server-side encryption. The encryption used must be Advanced Encryption Standard (AES-256) and the company does not want to manage S3 encryption keys.

Which of the following options should you use?

+ SSE-S3
+ SSE-C
+ Client-Side Encryption
+ SSE-KMS

<details close>
<summary>Answer</summary>
a
</details>
<br>

<details close>
<summary>Note</summary>
Client-Side Encryption: You have to manage it.
</details>
<br>


---

<p hidden>6-63</p>

A company is looking at storing their less frequently accessed files on AWS that can be concurrently accessed by hundreds of EC2 instances. The company needs the most cost-effective file storage service that provides immediate access to data whenever needed.

Which of the following options represents the best solution for the given requirements?

+ Amazon Elastic File System (EFS) Standard–IA storage class
+ Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class
+ Amazon Elastic File System (EFS) Standard storage class
+ Amazon Elastic Block Store (EBS)

<details close>
<summary>Answer</summary>
a
</details>
<br>

<details close>
<summary>Note</summary>
Amazon EFS is a file storage service for use with Amazon compute (EC2, containers, serverless) and on-premises servers. Amazon EFS provides a file system interface, file system access semantics (such as strong consistency and file locking), and concurrently accessible storage for up to thousands of Amazon EC2 instances.

The Standard–IA storage class reduces storage costs for files that are not accessed every day. It does this without sacrificing the high availability, high durability, elasticity, and POSIX file system access that Amazon EFS provides. AWS recommends Standard-IA storage if you need your full dataset to be readily accessible and want to automatically save on storage costs for files that are less frequently accessed.
</details>
<br>

---

<p hidden>6-64</p>

A development team has configured an Elastic Load Balancer for host-based routing. The idea is to support multiple subdomains and different top-level domains.

The rule *.sample.com matches which of the following?

+ sample.com
+ sample.test.com
+ SAMPLE.COM
+ test.sample.com


<details close>
<summary>Answer</summary>
d
</details>
<br>


























