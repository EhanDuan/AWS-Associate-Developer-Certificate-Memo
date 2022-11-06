# Development with AWS Services Practice Set (Selections from top to bottom as a,b,c,d)

**Q1. The team wants AWS Account A's Lambda function to AWS Account B's DynamoDB table. Which of the following solutions would you recommend?**
+ Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account

+ Add a resource policy to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A

+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the role in Account B to allow the execution role of Lambda to assume this role. Update the Lambda function code to add the AssumeRole API call

+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssumeRole API call


<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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


<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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

<details open>
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


<details open>
<summary>Answer</summary>
a, d
</details>
<br>

Source:
+ https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html

+ https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html#encrypt-unencrypted


