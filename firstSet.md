# Exam#1 Practice Set

Amazon Simple Queue Service (SQS) has a set of APIs for various actions supported by the service.

As a developer associate, which of the following would you identify as correct regarding the `CreateQueue` API? (Select two)

+ The dead-letter queue of a FIFO queue must also be a FIFO queue. Whereas, the dead-letter queue of a standard queue can be a standard queue or a FIFO queue
+ The length of time, in seconds, for which the delivery of all messages in the queue is delayed is configured using `MessageRetentionPeriod`  attribute
+ You can't change the queue type after you create it
+ The visibility timeout value for the queue is in seconds, which defaults to 30 seconds
+ Queue tags are case insensitive. A new tag with a key identical to that of an existing tag overwrites the existing tag

<details close>
<summary>Answer</summary>
c,d
</details>

<br>

---

A developer is configuring a bucket policy that denies upload object permission to any requests that do not include the `x-amz-server-side-encryption` header requesting server-side encryption with SSE-KMS for an Amazon S3 bucket - `examplebucket`.

Which of the following policies is the right fit for the given requirement?

```json
{
   "Version":"2012-10-17",
   "Id":"PutObjectPolicy",
   "Statement":[{
         "Sid":"DenyUnEncryptedObjectUploads",
         "Effect":"Deny",
         "Principal":"*",
         "Action":"s3:PutObject",
         "Resource":"arn:aws:s3:::examplebucket/*",
         "Condition":{
            "StringNotEquals":{
               "s3:x-amz-server-side-encryption":"aws:kms"
            }
         }
      }
   ]
}
```

```json
{
   "Version":"2012-10-17",
   "Id":"PutObjectPolicy",
   "Statement":[{
         "Sid":"DenyUnEncryptedObjectUploads",
         "Effect":"Deny",
         "Principal":"*",
         "Action":"s3:PutObject",
         "Resource":"arn:aws:s3:::examplebucket/*",
         "Condition":{
            "StringEquals":{
               "s3:x-amz-server-side-encryption":"aws:kms"
            }
         }
      }
   ]
}
```

```json
{
   "Version":"2012-10-17",
   "Id":"PutObjectPolicy",
   "Statement":[{
         "Sid":"DenyUnEncryptedObjectUploads",
         "Effect":"Deny",
         "Principal":"*",
         "Action":"s3:GetObject",
         "Resource":"arn:aws:s3:::examplebucket/*",
         "Condition":{
            "StringNotEquals":{
               "s3:x-amz-server-side-encryption":"aws:AES256"
            }
         }
      }
   ]
}
```

```json
{
   "Version":"2012-10-17",
   "Id":"PutObjectPolicy",
   "Statement":[{
         "Sid":"DenyUnEncryptedObjectUploads",
         "Effect":"Deny",
         "Principal":"*",
         "Action":"s3:PutObject",
         "Resource":"arn:aws:s3:::examplebucket/*",
         "Condition":{
            "StringNotEquals":{
               "s3:x-amz-server-side-encryption":"false"
            }
         }
      }
   ]
}
```

<details close>
<summary>Answer</summary>
a
</details>

<br>

---


ECS Fargate container tasks are usually spread across Availability Zones (AZs) and the underlying workloads need persistent cross-AZ shared access to the data volumes configured for the container tasks.

Which of the following solutions is the best choice for these workloads?

+ Docker Volumes
+ Bind mounts
+ AWS Gateway Storage volumes
+ Amazon EFS volumes

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A development team has configured inbound traffic for the relevant ports in both the Security Group of the EC2 instance as well as the Network Access Control List (NACL) of the subnet for the EC2 instance. The team is, however, unable to connect to the service running on the Amazon EC2 instance.

As a developer associate, which of the following will you recommend to fix this issue?

+ Network ACLs are stateful, so allowing inbound traffic to the necessary ports enables the connection. Security Groups are stateless, so you must allow both inbound and outbound traffic
+ IAM Role defined in the Security Group is different from the IAM Role that is given access in the Network ACLs
+ Security Groups are stateful, so allowing inbound traffic to the necessary ports enables the connection. Network ACLs are stateless, so you must allow both inbound and outbound traffic
+ Rules associated with Network ACLs should never be modified from the command line. An attempt to modify rules from the command line blocks the rule and results in an erratic behavior

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A developer is testing Amazon Simple Queue Service (SQS) queues in a development environment. The queue along with all its contents has to be deleted after testing.

Which SQS API should be used for this requirement?

+ PurgeQueue
+ DeleteQueue
+ RemoveQueue
+ RemovePermission

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A company has built its technology stack on AWS serverless architecture for managing all its business functions. To expedite development for a new business requirement, the company is looking at using pre-built serverless applications.

Which AWS service represents the easiest solution to address this use-case?

+ AWS Marketplace
+ AWS AppSync
+ AWS Service Catalog
+ AWS Serverless Application Repository (SAR)

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A development team wants to build an application using serverless architecture. The team plans to use AWS Lambda functions extensively to achieve this goal. The developers of the team work on different programming languages like Python, .NET and Javascript. The team wants to model the cloud infrastructure using any of these programming languages.

Which AWS service/tool should the team use for the given use-case?

+ AWS CloudFormation
+ AWS Cloud Development Kit (CDK)
+ AWS Serverless Application Model (SAM)
+ AWS CodeDeploy

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

As a developer, you are working on creating an application using AWS Cloud Development Kit (CDK).

Which of the following represents the correct order of steps to be followed for creating an app using AWS CDK?

+ Create the app from a template provided by AWS CDK -> Add code to the app to create resources within stacks -> Build the app (optional) -> Synthesize one or more stacks in the app -> Deploy stack(s) to your AWS account
+ Create the app from a template provided by AWS CloudFormation -> Add code to the app to create resources within stacks -> Build the app (optional) -> Synthesize one or more stacks in the app -> Deploy stack(s) to your AWS account
+ Create the app from a template provided by AWS CDK -> Add code to the app to create resources within stacks -> Synthesize one or more stacks in the app -> Deploy stack(s) to your AWS account -> Build the app
+ Create the app from a template provided by AWS CloudFormation -> Add code to the app to create resources within stacks -> Synthesize one or more stacks in the app -> Deploy stack(s) to your AWS account -> Build the app

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

After a test deployment in ElasticBeanstalk environment, a developer noticed that all accumulated Amazon EC2 burst balances were lost.

Which of the following options can lead to this behavior?

+ The deployment was run as a Rolling deployment, resulting in the resetting of EC2 burst balances
+ The deployment was run as a All-at-once deployment, flushing all the accumulated EC2 burst balances
+ The deployment was either run with immutable updates or in traffic splitting mode
+ When a canary deployment fails, it resets the EC2 burst balances to zero

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

When running a Rolling deployment in Elastic Beanstalk environment, only two batches completed the deployment successfully, while rest of the batches failed to deploy the updated version. Following this, the development team terminated the instances from the failed deployment.

What will be the status of these failed instances post termination?

+ Elastic Beanstalk will not replace the failed instances
+ Elastic Beanstalk will replace the failed instances with instances running the application version from the oldest successful deployment
+ Elastic Beanstalk will replace the failed instances after the application version to be installed is manually chosen from AWS Console
+ Elastic Beanstalk will replace the failed instances with instances running the application version from the most recent successful deployment

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A Developer at a company is working on a CloudFormation template to set up resources. Resources will be defined using code and provisioned based on certain conditions.

Which section of a CloudFormation template does not allow for conditions?

+ Outputs
+ Resources
+ Conditions
+ Parameters

<details close>
<summary>Answer</summary>
d
</details>

<br>

---

A firm runs its technology operations on a fleet of Amazon EC2 instances. The firm needs a certain software to be available on the instances to support their daily workflows. The developer team has been told to use the user data feature of EC2 instances.

Which of the following are true about the user data EC2 configuration? ( Select two)

+ By default, user data is executed every time an EC2 instance is re-started
+ When an instance is running, you can update user data by using root user credentials
+ By default, scripts entered as user data are executed with root user privileges
+ By default, user data runs only during the boot cycle when you first launch an instance
+ By default, scripts entered as user data do not have root user privileges for executing

<details close>
<summary>Answer</summary>
c,d
</details>

<br>

---

A development team at a social media company uses AWS Lambda for its serverless stack on AWS Cloud. For a new deployment, the Team Lead wants to send only a certain portion of the traffic to the new Lambda version. In case the deployment goes wrong, the solution should also support the ability to roll back to a previous version of the Lambda function, with MIMINUM downtime for the application.

As a Developer Associate, which of the following options would you recommend to address this use-case?

+ Set up the application to use an alias that points to the current version. Deploy the new version of the code and configure alias to send all users to this new version. If the deployment goes wrong, reset the alias to point to the current version
+ Set up the application to directly deploy the new Lambda version. If the deployment goes wrong, reset the application back to the current version using the version number in the ARN
+ Set up the application to use an alias that points to the current version. Deploy the new version of the code and configure the alias to send 10% of the users to this new version. If the deployment goes wrong, reset the alias to point all traffic to the current version
+ Set up the application to have multiple alias of the Lambda function. Deploy the new version of the code. Configure a new alias that points to the current alias of the Lambda function for handling 10% of the traffic. If the deployment goes wrong, reset the new alias to point all traffic to the most recent working alias of the Lambda function

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

Which of the following best describes how KMS Encryption works?

+ KMS stores the CMK, and receives data from the clients, which it encrypts and sends back
+ KMS receives CMK from the client at every Encrypt call, and encrypts the data with that
+ KMS sends the CMK to the client, which performs the encryption and then deletes the CMK
+ KMS generates a new CMK for each Encrypt call and encrypts the data with it

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company uses Elastic Beanstalk to manage its IT infrastructure on AWS Cloud and it would like to deploy the new application version to the EC2 instances. When the deployment is executed, some instances should serve requests with the old application version, while other instances should serve requests using the new application version until the deployment is completed.

Which deployment meets this requirement without incurring additional costs?

+ Immutable
+ Rolling
+ All at once
+ Rolling with additional batches

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A financial services company is undergoing a compliance audit by the regulator. The company has hundreds of IAM users that make API calls but specifically it needs to be determined who is making KMS API calls.

Which of the following services should the audit team use?

+ CloudTrail
+ CloudWatch Metrics
+ X-Ray
+ Config

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

A company has hired you as an AWS Certified Developer Associate to help with redesigning a real-time data processor. The company wants to build custom applications that process and analyze the streaming data for its specialized needs.

Which solution will you recommend to address this use-case?

+ Use SQS to process the data streams as well as decouple the producers and consumers for the real-time data processor
+ Use SNS to process the data streams as well as decouple the producers and consumers for the real-time data processor
+ Use Kinesis Data Streams to process the data streams as well as decouple the producers and consumers for the real-time data processor
+ Use Kinesis Data Firehose to process the data streams as well as decouple the producers and consumers for the real-time data processor

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A SaaS company runs a HealthCare web application that is used worldwide by users. There have been requests by mobile developers to expose public APIs for the application-specific functionality. You decide to make the APIs available to mobile developers as product offerings.

Which of the following options will allow you to do that?
+ Use CloudFront Usage Plans
+ Use AWS Billing Usage Plans
+ Use API Gateway Usage Plans
+ Use AWS Lambda Custom Authorizers

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A company is looking at optimizing their Amazon EC2 instance costs. Few instances are sure to run for a few years, but the instance type might change based on business requirements.

Which EC2 instance purchasing option should they opt to meet the reduced cost criteria?

+ Elastic Reserved instances
+ Standard Reserved instances
+ Convertible Reserved instances
+ Scheduled Reserved instances

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

Your global organization has an IT infrastructure that is deployed using CloudFormation on AWS Cloud. One employee, in us-east-1 Region, has created a stack 'Application1' and made an exported output with the name 'ELBDNSName'. Another employee has created a stack for a different application 'Application2' in us-east-2 Region and also exported an output with the name 'ELBDNSName'. The first employee wanted to deploy the CloudFormation stack 'Application1' in us-east-2, but it got an error. What is the cause of the error?

+ Output Values in CloudFormation must have unique names across all Regions
+ Exported Output Values in CloudFormation must have unique names across all Regions
+ Exported Output Values in CloudFormation must have unique names within a single Region
+ Output Values in CloudFormation must have unique names within a single Region

<details close>
<summary>Answer</summary>
c
</details>

<br>

---

A cybersecurity firm wants to run their applications on single-tenant hardware to meet security guidelines.

Which of the following is the MOST cost-effective way of isolating their Amazon EC2 instances to a single tenant?

+ Dedicated Instances
+ Spot Instances
+ Dedicated Hosts
+ On-Demand Instances

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

You're a developer doing contract work for the media sector. Since you work alone, you opt for technologies that require little maintenance, which allows you to focus more on your coding. You have chosen AWS Elastic Beanstalk to assist with the deployment of your applications. While reading online documentation you find that Elastic Beanstalk relies on another AWS service to provision your resources.

Which of the following represents this AWS service?

+ CodeCommit
+ CloudFormation
+ CodeDeploy
+ Systems Manager

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

You have created a Java application that uses RDS for its main data storage and ElastiCache for user session storage. The application needs to be deployed using Elastic Beanstalk and every new deployment should allow the application servers to reuse the RDS database. On the other hand, user session data stored in ElastiCache can be re-created for every deployment.

Which of the following configurations will allow you to achieve this? (Select two)

+ ElastiCache bundled with the application source code
+ ElastiCache defined in `.ebextensions/`
+ RDS database defined in `.ebextensions/`
+ ElastiCache database defined externally and referenced through environment variables
+ RDS database defined externally and referenced through environment variables


<details close>
<summary>Answer</summary>
b,e
</details>

<br>

---

Your company has stored all application secrets in SSM Parameter Store. The audit team has requested to get a report to better understand when and who has issued API calls against SSM Parameter Store.

Which of the following options can be used to produce your report?

+ Use AWS CloudTrail to get a record of actions taken by a user
+ Use SSM Parameter Store List feature to get a record of actions taken by a user
+ Use SSM Parameter Store Access Logs in CloudWatch Logs to get a record of actions taken by a user
+ Use SSM Parameter Store Access Logs in S3 to get a record of actions taken by a user

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

You are running workloads on AWS and have embedded RDS database connection strings within each web server hosting your applications. After failing a security audit, you are looking at a different approach to store your secrets securely and automatically rotate the database credentials.

Which AWS service can you use to address this use-case?

+ SSM Parameter Store
+ Secrets Manager
+ Systems Manager
+ KMS

<details close>
<summary>Answer</summary>
b
</details>

<br>

---

A developer at a company is trying to create a digital signature for SSH'ing into the Amazon EC2 instances.

Which of the following entities can be used to facilitate this use-case?

+ Multi-Factor Authentication (MFA)
+ Access keys
+ Key pairs
+ Root user credentials

<details close>
<summary>Answer</summary>
c
</details>

<br>

<details close>
<summary>Note</summary>
Key pairs consist of a public key and a private key. You use the private key to create a digital signature, and then AWS uses the corresponding public key to validate the signature. Key pairs are used only for Amazon EC2 and Amazon CloudFront. AWS does not provide key pairs for your account; you must create them. You can create Amazon EC2 key pairs from the Amazon EC2 console, CLI, or API. Key pairs make a robust combination for accessing an instance securely, a better option than using passwords.
</details>

<br>

---

An IT company is configuring Auto Scaling for its Amazon EC2 instances spread across different AZs and Regions.

Which of the following scenarios are NOT correct about EC2 Auto Scaling? (Select two)
+ An Auto Scaling group can contain EC2 instances in one or more Availability Zones within the same Region
+ Auto Scaling groups that span across multiple Regions need to be enabled for all the Regions specified
+ Amazon EC2 Auto Scaling attempts to distribute instances evenly between the Availability Zones that are enabled for your Auto Scaling group
+ For Auto Scaling groups in a VPC, the EC2 instances are launched in subnets
+ An Auto Scaling group can contain EC2 instances in only one Availability Zone of a Region

<details close>
<summary>Answer</summary>
b,e
</details>

<br>

---

You have created an Elastic Load Balancer that has marked all the EC2 instances in the target group as unhealthy. Surprisingly, when you enter the IP address of the EC2 instances in your web browser, you can access your website.

What could be the reason your instances are being marked as unhealthy? (Select two)

+ The security group of the EC2 instance does not allow for traffic from the security group of the Application Load Balancer
+ The route for the health check is misconfigured
+ The EBS volumes have been improperly mounted
+ Your web-app has a runtime that is not supported by the Application Load Balancer
+ You need to attach Elastic IP to the EC2 instances

<details close>
<summary>Answer</summary>
a,b
</details>

<br>

---
An organization has hosted its EC2 instances in two AZs. AZ1 has two instances and AZ2 has 8 instances. The Elastic Load Balancer managing the instances in the two AZs has cross-zone load balancing enabled in its configuration.

What percentage traffic will each of the instances in AZ1 receive?
+ 10
+ 25
+ 20
+ 15

<details close>
<summary>Answer</summary>
a
</details>

<br>

---

The development team at an IT company would like to provision their own Docker images that can be used as input sources for CodeBuild. These images will contain cached dependencies as well as special tooling for builds that are proprietary to the company.

Which of the following services can be used to store and deploy these Docker images?

+ S3
+ ECR
+ ECS
+ EBS

<details close>
<summary>Answer</summary>
b
</details>

---

The development team at an IT company wants to make changes to a current application written in Node.js and deployed on a Linux server. The team lead would like to decouple the application into microservices, package the application to a Docker container which is then run on the AWS infrastructure.

Which AWS service is best suited for this change?


+ ECS
+ Step Functions
+ Lambda
+ ECR

<details close>
<summary>Answer</summary>
a
</details>

---

A developer has been asked to create a web application to be deployed on EC2 instances. The developer just wants to focus on writing application code without worrying about server provisioning, configuration and deployment.

As a Developer Associate, which AWS service would you recommend for the given use-case?

+ CloudFormation
+ CodeDeploy
+ Elastic Beanstalk
+ Serverless Application Model

<details close>
<summary>Answer</summary>
c
</details>

---

An application is hosted by a 3rd party and exposed at yourapp.3rdparty.com. You would like to have your users access your application using www.mydomain.com, which you own and manage under Route 53.

What Route 53 record should you create?

+ Create an A record
+ Create a CNAME record
+ Create a PTR record
+ Create an Alias Record


<details close>
<summary>Answer</summary>
b
</details>

---

A startup with newly created AWS account is testing different EC2 instances. They have used Burstable performance instance - T2.micro - for 35 seconds and stopped the instance.

At the end of the month, what is the instance usage duration that the company is charged for?

+ 35 seconds
+ 0 seconds
+ 60 seconds
+ 30 seconds

<details close>
<summary>Answer</summary>
b
</details>

---


You are a developer working on AWS Lambda functions that are invoked via REST API's using Amazon API Gateway. Currently, when a GET request is invoked by the consumer, the entire data-set returned by the Lambda function is visible. Your team lead asked you to format the data response.

Which feature of the API Gateway can be used to solve this issue?

+ Deploy an interceptor shell script
+ Use API Gateway Mapping Templates
+ Use an API Gateway stage variable
+ Use a Lambda custom interceptor

<details close>
<summary>Answer</summary>
b
</details>

---


You are creating a Cloud Formation template to deploy your CMS application running on an EC2 instance within your AWS account. Since the application will be deployed across multiple regions, you need to create a map of all the possible values for the base AMI.

How will you invoke the `!FindInMap` function to fulfill this use case?
+ `!FindInMap [ MapName, TopLevelKey, SecondLevelKey ]`
+ `!FindInMap [ MapName, TopLevelKey ]`
+ `!FindInMap [ MapName ]`
+ `!FindInMap [ MapName, TopLevelKey, SecondLevelKey, ThirdLevelKey ]`


<details close>
<summary>Answer</summary>
a
</details>

---

A media company has created a video streaming application and it would like their Brazilian users to be served by the company's Brazilian servers. Other users around the globe should not be able to access the servers through DNS queries.

Which Route 53 routing policy meets this requirement?

+ Latency
+ Geolocation
+ Failover
+ Weighted

<details close>
<summary>Answer</summary>
b
</details>

---

A multi-national company has multiple business units with each unit having its own AWS account. The development team at the company would like to debug and trace data across accounts and visualize it in a centralized account.

As a Developer Associate, which of the following solutions would you suggest for the given use-case?
+ CloudTrail
+ VPC Flow Logs
+ CloudWatch Events
+ X-Ray

<details close>
<summary>Answer</summary>
d
</details>

---

The manager at an IT company wants to set up member access to user-specific folders in an Amazon S3 bucket - `bucket-a`. So, user x can only access files in his folder - `bucket-a/user/user-x/` and user y can only access files in her folder - `bucket-a/user/user-y/` and so on.

As a Developer Associate, which of the following IAM constructs would you recommend so that the policy snippet can be made generic for all team members and the manager does not need to create separate IAM policy for each team member?
+ IAM policy principal
+ IAM policy variables
+ IAM policy condition
+ IAM policy resource

<details close>
<summary>Answer</summary>
b
</details>

---

The development team at a company creates serverless solutions using AWS Lambda. Functions are invoked by clients via AWS API Gateway which anyone can access. The team lead would like to control access using a 3rd party authorization mechanism.

As a Developer Associate, which of the following options would you recommend for the given use-case?

+ IAM permissions with sigv4
+ Lambda Authorizer
+ Cognito User Pools
+ API Gateway User Pools

<details close>
<summary>Answer</summary>
b
</details>

---

A multi-national company has just moved to AWS Cloud and it has configured forecast-based AWS Budgets alerts for cost management. However, no alerts have been received even though the account and the budgets have been created almost three weeks ago.

What could be the issue with the AWS Budgets configuration?
+ Budget forecast has been created from an account that does not have enough privileges
+ Amazon CloudWatch could be down and hence alerts are not being sent
+ Account has to be part of AWS Organizations to receive AWS Budgets alerts
+ AWS requires approximately 5 weeks of usage data to generate budget forecasts

<details close>
<summary>Answer</summary>
d
</details>

---


You have deployed a Java application to an EC2 instance where it uses the X-Ray SDK. When testing from your personal computer, the application sends data to X-Ray but when the application runs from within EC2, the application fails to send data to X-Ray.

Which of the following does NOT help with debugging the issue?

+ EC2 X-Ray Daemon
+ X-Ray sampling
+ EC2 Instance Role
+ CloudTrail

<details close>
<summary>Answer</summary>
b
</details>

---

An E-commerce business, has its applications built on a fleet of Amazon EC2 instances, spread across various Regions and AZs. The technical team has suggested using Elastic Load Balancers for better architectural design.

What characteristics of an Elastic Load Balancer make it a winning choice? (Select two)

+ Separate public traffic from private traffic
+ Build a highly available system
+ The Load Balancer communicates with the underlying EC2 instances using their public IPs
+ Improve vertical scalability of the system
+ Deploy EC2 instances across multiple AWS Regions

<details close>
<summary>Answer</summary>
a,b
</details>

---

You're a developer working on a large scale order processing application. After developing the features, you commit your code to AWS CodeCommit and begin building the project with AWS CodeBuild before it gets deployed to the server. The build is taking too long and the error points to an issue resolving dependencies from a third-party. You would like to prevent a build running this long in the future for similar underlying reasons.

Which of the following options represents the best solution to address this use-case?

+ Enable CodeBuild timeouts
+ Use AWS Lambda
+ Use AWS CloudWatch Events
+ Use VPC Flow Logs

<details close>
<summary>Answer</summary>
a
</details>

---

An e-commerce company has developed an API that is hosted on Amazon ECS. Variable traffic spikes on the application are causing order processing to take too long. The application processes orders using Amazon SQS queues. The `ApproximateNumberOfMessagesVisible` metric spikes at very high values throughout the day which triggers the CloudWatch alarm. Other ECS metrics for the API containers are well within limits.

As a Developer Associate, which of the following will you recommend for improving performance while keeping costs low?

+ Use backlog per instance metric with target tracking scaling policy
+ Use Docker swarm
+ Use ECS service scheduler
+ Use ECS step scaling policy

<details close>
<summary>Answer</summary>
a
</details>

---

A development team wants to deploy an AWS Lambda function that requires significant CPU utilization.

As a Developer Associate, which of the following would you suggest for reducing the average runtime of the function?

+ Deploy the function into multiple AWS Regions
+ Deploy the function with its CPU allocation set to the maximum amount
+ Deploy the function using Lambda layers
+ Deploy the function with its memory allocation set to the maximum amount

<details close>
<summary>Answer</summary>
d
</details>

---

The development team has just configured and attached the IAM policy needed to access AWS Billing and Cost Management for all users under the Finance department. But, the users are unable to see AWS Billing and Cost Management service in the AWS console.

What could be the reason for this issue?

+ The users might have another policy that restricts them from accessing the Billing information
+ You need to activate IAM user access to the Billing and Cost Management console for all the users who need access
+ Only root user has access to AWS Billing and Cost Management console
+ IAM user should be created under AWS Billing and Cost Management and not under AWS account to have access to Billing console

<details close>
<summary>Answer</summary>
b
</details>

---

In addition to regular sign-in credentials, AWS supports Multi-Factor Authentication (MFA) for accounts with privileged access.

Which of the following MFA mechanisms is NOT for root user authentication?

+ SMS text message-based MFA
+ Hardware MFA device
+ U2F security key
+ Virtual MFA devices

<details close>
<summary>Answer</summary>
a
</details>

---

Which of the following security credentials can only be created by the AWS Account root user?
+ CloudFront Key Pairs
+ EC2 Instance Key Pairs
+ IAM User Access Keys
+ IAM User passwords

<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
IAM users can't create CloudFront key pairs. You must log in using root credentials to create key pairs.
</details>

---

Your company has configured AWS Organizations to manage multiple AWS accounts. Within each AWS account, there are many CloudFormation scripts running. Your manager has requested that each script output the account number of the account the script was executed in.

Which Pseudo parameter will you use to get this information?

+ AWS::StackName
+ AWS::NoValue
+ AWS::Region
+ AWS::AccountId

<details close>
<summary>Answer</summary>
d
</details>

---

CodeCommit is a managed version control service that hosts private Git repositories in the AWS cloud.

Which of the following credential types is NOT supported by IAM for CodeCommit?
+ Git credentials
+ IAM username and password
+ SSH Keys
+ AWS Access Keys

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
IAM username and password credentials cannot be used to access CodeCommit.
</details>

---

You are a developer for a web application written in .NET which uses the AWS SDK. You need to implement an authentication mechanism that returns a JWT (JSON Web Token).

Which AWS service will help you with token handling and management?
+ Cognito Sync
+ API Gateway
+ Cognito Identity Pools
+ Cognito User Pools

<details close>
<summary>Answer</summary>
d
</details>

---

To enable HTTPS connections for his web application deployed on the AWS Cloud, a developer is in the process of creating server certificate.

Which AWS entities can be used to deploy SSL/TLS server certificates? (Select two)
+ AWS Secrets Manager
+ AWS Certificate Manager
+ AWS Systems Manager
+ IAM
+ AWS CloudFormation

<details close>
<summary>Answer</summary>
b,d
</details>

<details close>
<summary>Note</summary>
IAM is used as a certificate manager only when you must support HTTPS connections in a Region that is not supported by ACM
</details>

---

A development team lead is responsible for managing access for her IAM principals. At the start of the cycle, she has granted excess privileges to users to keep them motivated for trying new things. She now wants to ensure that the team has only the minimum permissions required to finish their work.

Which of the following will help her identify unused IAM roles and remove them without disrupting any service?

+ AWS Trusted Advisor
+ IAM Access Analyzer
+ Access Advisor feature on IAM console
+ Amazon Inspector

<details close>
<summary>Answer</summary>
c
</details>

---

You are a developer in a manufacturing company that has several servers on-site. The company decides to move new development to the cloud using serverless technology. You decide to use the AWS Serverless Application Model (AWS SAM) and work with an AWS SAM template file to represent your serverless architecture.

Which of the following is NOT a valid serverless resource type?

+ AWS::Serverless::UserPool
+ AWS::Serverless::Function
+ AWS::Serverless::Api
+ AWS::Serverless::SimpleTable

<details close>
<summary>Answer</summary>
a
</details>

---

A Developer has been entrusted with the job of securing certain S3 buckets that are shared by a large team of users. Last time, a bucket policy was changed, the bucket was erroneously available for everyone, outside the organization too.

Which feature/service will help the developer identify similar security issues with minimum effort?

+ Access Advisor feature on IAM console
+ S3 Object Lock
+ S3 Analytics
+ IAM Access Analyzer

<details close>
<summary>Answer</summary>
d
</details>

---

A developer has been asked to create an application that can be deployed across a fleet of EC2 instances. The configuration must allow for full control over the deployment steps using the blue-green deployment.

Which service will help you achieve that?

+ CodeBuild
+ CodeDeploy
+ Elastic Beanstalk
+ CodePipeline
<details close>
<summary>Answer</summary>
b
</details>

---

A development team lead is configuring policies for his team at an IT company.

Which of the following policy types only limit permissions but cannot grant permissions (Select two)?
+ AWS Organizations Service Control Policy (SCP)
+ Permissions boundary
+ Access control list (ACL)
+ Resource-based policy
+ Identity-based policy

<details close>
<summary>Answer</summary>
a,b
</details>

---

The Technical Lead of your team has reviewed a CloudFormation YAML template written by a new recruit and specified that an invalid section has been added to the template.

Which of the following represents an invalid section of the CloudFormation template?
+ 'Conditions' section of the template
+ 'Resources' section of the template
+ 'Parameters' section of the template
+ 'Dependencies' section of the template

<details close>
<summary>Answer</summary>
d
</details>

---

As an AWS Certified Developer Associate, you been asked to create an AWS Elastic Beanstalk environment to handle deployment for an application that has high traffic and high availability needs. You need to deploy the new version using Beanstalk while making sure that performance and availability are not affected.

Which of the following is the MOST optimal way to do this while keeping the solution cost-effective?

+ Deploy using 'Immutable' deployment policy
+ Deploy using 'Rolling with additional batch' deployment policy
+ Deploy using 'All at once' deployment policy
+ Deploy using 'Rolling' deployment policy

<details close>
<summary>Answer</summary>
b
</details>

---

As an AWS Certified Developer Associate, you have configured the AWS CLI on your workstation. Your default region is us-east-1 and your IAM user has permissions to operate commands on services such as EC2, S3 and RDS in any region. You would like to execute a command to stop an EC2 instance in the us-east-2 region.

What of the following is the MOST optimal solution to address this use-case?

+ You should create a new IAM user just for that other region
+ You need to override the default region by using aws configure
+ Use the --region parameter
+ Use boto3 dependency injection

<details close>
<summary>Answer</summary>
c
</details>

---

As an AWS Certified Developer Associate, you are given a document written in YAML that represents the architecture of a serverless application. The first line of the document contains `Transform: 'AWS::Serverless-2016-10-31'`.

What does the `Transform` section in the document represent?
+ It represents a Lambda function definition
+ It represents an intrinsic function
+ Presence of `Transform`  section indicates it is a Serverless Application Model (SAM) template
+ Presence of `Transform`  section indicates it is a CloudFormation Parameter

<details close>
<summary>Answer</summary>
c
</details>

---

You have chosen AWS Elastic Beanstalk to upload your application code and allow it to handle details such as provisioning resources and monitoring.

When creating configuration files for AWS Elastic Beanstalk which naming convention should you follow?

+ `.ebextensions_<mysettings>.config`
+ `.ebextensions/<mysettings>.config`
+ `.config/<mysettings>.ebextensions`
+ `.config_<mysettings>.ebextensions`

<details close>
<summary>Answer</summary>
b
</details>

---

As part of his development work, an AWS Certified Developer Associate is creating policies and attaching them to IAM identities. After creating necessary Identity-based policies, he is now creating Resource-based policies.

Which is the only resource-based policy that the IAM service supports?

+ AWS Organizations Service Control Policies (SCP)
+ Trust policy
+ Access control list (ACL)
+ Permissions boundary

<details close>
<summary>Answer</summary>
b
</details>











