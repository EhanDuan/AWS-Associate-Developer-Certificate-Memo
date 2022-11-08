# Exam#5 Practice Set

**A media company wants to migrate a video editing service to Amazon EC2 while following security best practices. The videos are sourced and read from a non-public S3 bucket.**

**As a Developer Associate, which of the following solutions would you recommend for the given use-case?**
+ Set up an IAM user with read-only permissions for the S3 bucket. Configure AWS credentials for this user via AWS CLI on the EC2 instance

+ Set up an IAM user with read-only permissions for the S3 bucket. Configure the IAM user credentials in the user data of the EC2 instance

+ Set up an S3 service role with read-only permissions for the S3 bucket and attach the role to the EC2 instance profile

+ Set up an EC2 service role with read-only permissions for the S3 bucket and attach the role to the EC2 instance profile


<details close>
<summary>Answer</summary>
d
</details>

<br>

<details close>
<summary>Note</summary>
As an AWS security best practice, you should not create an IAM user and pass the user's credentials to the application or embed the credentials in the application. Instead, create an IAM role that you attach to the EC2 instance to give temporary security credentials to applications running on the instance. When an application uses these credentials in AWS, it can perform all of the operations that are allowed by the policies attached to the role.

So for the given use-case, you should create an IAM role with read-only permissions for the S3 bucket and apply it to the EC2 instance profile.
</details>



Source: https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html

---

A media analytics company has built a streaming application on Lambda using Serverless Application Model (SAM).

As a Developer Associate, which of the following would you identify as the correct order of execution to successfully deploy the application?

 + Develop the SAM template locally => upload the template to Lambda => deploy your application to the cloud
 + Develop the SAM template locally => upload the template to CodeCommit => deploy your application to CodeDeploy
 + Develop the SAM template locally => upload the template to S3 => deploy your application to the cloud
 + Develop the SAM template locally => deploy the template to S3 => use your application in the cloud


<details close>
<summary>Answer</summary>
c
</details>



Source: https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-deploying.html

---

An IT company leverages CodePipeline to automate its release pipelines. The development team wants to write a Lambda function that will send notifications for state changes within the pipeline.

As a Developer Associate, which steps would you suggest to associate the Lambda function with the event source?

+ Set up an Amazon CloudWatch alarm that monitors status changes in Code Pipeline and triggers the Lambda function
+ Set up an Amazon CloudWatch Events rule that uses CodePipeline as an event source with the target as the Lambda function
+ Use the Lambda console to configure a trigger that invokes the Lambda function with CodePipeline as the event source
+ Use the CodePipeline console to set up a trigger for the Lambda function

<details close>
<summary>Answer</summary>
b
</details>

---

A data analytics company ingests a large number of messages and stores them in an RDS database using Lambda. Because of the increased payload size, it is taking more than 15 minutes to process each message.

As a Developer Associate, which of the following options would you recommend to process each message in the MOST scalable way?

+ Provision EC2 instances in an Auto Scaling group to poll the messages from an SQS queue
+ Provision an EC2 instance to poll the messages from an SQS queue
+ Contact AWS Support to increase the Lambda timeout to 60 minutes
+ Use DynamoDB instead of RDS as database

<details close>
<summary>Answer</summary>
a
</details>

---

A development team has a mix of applications hosted on-premises as well as on EC2 instances. The on-premises application controls all applications deployed on the EC2 instances. In case of any errors, the team wants to leverage Amazon CloudWatch to monitor and troubleshoot the on-premises application.

As a Developer Associate, which of the following solutions would you suggest to address this use-case?

+ Upload log files from the on-premises server to an EC2 instance which further forwards the logs to CloudWatch
+ Configure CloudWatch Logs to directly read the logs from the on-premises server
+ Configure the CloudWatch agent on the on-premises server by using IAM user credentials with permissions for CloudWatch
+ Upload log files from the on-premises server to S3 and let CloudWatch process the files from S3


<details close>
<summary>Answer</summary>
c
</details>

<details close>
<summary>Note</summary>
The CloudWatch agent enables you to do the following:

Collect system-level metrics from on-premises servers. These can include servers in a hybrid environment as well as servers not managed by AWS.

Collect logs from Amazon EC2 instances and on-premises servers, running either Linux or Windows Server.

To enable the CloudWatch agent to send data from an on-premises server, you must specify the access key and secret key of the IAM user that you created earlier.


</details>

---

Your company has developers worldwide with access to the company's Amazon Simple Storage Service (S3) buckets. The objects in the buckets are encrypted at the server-side but need more flexibility with access control, auditing, rotation, and deletion of keys. You would also like to limit who can use the key.

Which encryption mechanism best fits your needs?


+ SSE-S3
+ SSE-C
+ Client Side Encrpytion
+ SSE-KMS


<details close>
<summary>Answer</summary>
d
</details>

---

You are running a public DNS service on an EC2 instance where the DNS name is pointing to the IP address of the instance. You wish to upgrade your DNS service but would like to do it without any downtime.

Which of the following options will help you accomplish this?


+ Use Route 53
+ Create a Load Balancer and an auto scaling group
+ Provide a static private IP
+ Elastic IP


<details close>
<summary>Answer</summary>
d
</details>

---

You are a cloud security engineer working for a popular cyber-forensics company that offers vulnerability scanning solutions to government contractors. The scanning solutions are integrated with AWS resources to monitor EC2 and S3 API calls which then display results to users on an analytical dashboard.

Which of the following AWS services makes this possible?

+ IAM
+ S3 Access Logs
+ VPC Flow Logs
+ CloudTrail


<details close>
<summary>Answer</summary>
d
</details>

---

Your company is shifting towards Elastic Container Service (ECS) to deploy applications. The process should be automated using the AWS CLI to create a service where at least ten instances of a task definition are kept running under the default cluster.

Which of the following commands should be executed?

+ `docker-compose create ecs-simple-service`
+ `aws ecr create-service --service-name ecs-simple-service --task-definition ecs-demo --desired-count 10`
+ `aws ecs create-service --service-name ecs-simple-service --task-definition ecs-demo --desired-count 10`
+ `aws ecs run-task --cluster default --task-definition ecs-demo`

<details close>
<summary>Answer</summary>
c
</details>

---

Your organization has a single Amazon Simple Storage Service (S3) bucket that contains folders labeled with customer names. Several administrators have IAM access to the S3 bucket and versioning is enabled to easily recover from unintended user actions.

Which of the following statements about versioning is NOT true based on this scenario?

+ Any file that was unversioned before enabling versioning will have the 'null' version
+ Overwriting a file increases its versions
+ Deleting a file is a recoverable operation
+ Versioning can be enabled only for a specific folder

<details close>
<summary>Answer</summary>
d
</details>

---

You have been collecting AWS X-Ray traces across multiple applications and you would now like to index your XRay traces to search and filter through them efficiently.

What should you use in your instrumentation?

+ Annotations
+ Sampling
+ Segments
+ Metadata

<details close>
<summary>Answer</summary>
a
</details>


---

You would like your Elastic Beanstalk environment to expose an HTTPS endpoint instead of an HTTP endpoint to get in-flight encryption between your clients and your web servers.

What must be done to set up HTTPS on Beanstalk?

+ Create a config file in the .ebextensions folder to configure the Load Balancer
+ Use a separate CloudFormation template to load the SSL certificate onto the Load Balancer
+ Open up the port 80 for the security group
+ Configure Health Checks


<details close>
<summary>Answer</summary>
a
</details>

<details close>
<summary>Note</summary>
The simplest way to use HTTPS with an Elastic Beanstalk environment is to assign a server certificate to your environment's load balancer. When you configure your load balancer to terminate HTTPS, the connection between the client and the load balancer is secure. Backend connections between the load balancer and EC2 instances use HTTP, so no additional configuration of the instances is required.
</details>

---

Your AWS account is now growing to 200 users and you would like to provide each of these users a personal space in the S3 bucket 'my_company_space' with the prefix `/home/<username>`, where they have read/write access.

How can you do this efficiently?

+ Create one customer-managed policy with policy variables and attach it to a group of all users
+ Create inline policies for each user as they are onboarded
+ Create one customer-managed policy per user and attach them to the relevant users
+ Create an S3 bucket policy and change it as users are added and removed


<details close>
<summary>Answer</summary>
a
</details>

---

You would like to deploy a Lambda function globally so that requests are filtered at the AWS edge locations.

Which Lambda deployment mode do you need?

+ Use a Lambda@Edge
+ Use a Global DynamoDB table as a Lambda source
+ Deploy Lambda in a Global VPC
+ Deploy Lambda in S3

<details close>
<summary>Answer</summary>
a
</details>

---

Your organization has set up a full CI/CD pipeline leveraging CodePipeline and the deployment is done on Elastic Beanstalk. This pipeline has worked for over a year now but you are approaching the limits of Elastic Beanstalk in terms of how many versions can be stored in the service.

How can you remove older versions that are not used by Elastic Beanstalk so that new versions can be created for your applications?

+ Setup an `.ebextensions` file
+ Define a Lambda function
+ Use a Lifecycle Policy
+ Use Worker Environments

<details close>
<summary>Answer</summary>
c
</details>

---

You are running a video website and provide users with S3 pre-signed URLs allowing your users to securely upload their video content onto your buckets. The average file size uploaded to your buckets is 500MB and you would like your users to efficiently send the content.

What would you recommend doing in the client SDK?

+ Do a multi-part upload
+ Upload as one part
+ Use SSE-S3 encryption
+ Zip the video file before sending

<details close>
<summary>Answer</summary>
a
</details>

---

You would like to run the X-Ray daemon for your Docker containers deployed using AWS Fargate.

What do you need to do to ensure the setup will work? (Select two)
+ Deploy the X-Ray daemon agent as a process on your EC2 instance
+ Deploy the X-Ray daemon agent as a daemon set on ECS
+ Provide the correct IAM task role to the X-Ray container
+ Deploy the X-Ray daemon agent as a sidecar container
+ Provide the correct IAM instance role to the EC2 instance


<details close>
<summary>Answer</summary>
b,c
</details>

---

Your Lambda function must use the Node.js drivers to connect to your RDS PostgreSQL database in your VPC.

How do you bundle your Lambda function to add the dependencies?

+ Zip the function as-is with a package.json file so that AWS Lambda can resolve the dependencies for you
+ Upload the code through the AWS console and upload the dependencies as a zip
+ Zip the function and the dependencies separately and upload them in AWS Lambda as two parts
+ Put the function and the dependencies in one folder and zip them together


<details close>
<summary>Answer</summary>
d
</details>

---

You would like to retrieve a subset of your dataset stored in S3 with the CSV format. You would like to retrieve a month of data and only 3 columns out of the 10.

You need to minimize compute and network costs for this, what should you use?

+ S3 Inventory
+ S3 Select
+ S3 Analytics
+ S3 Access Logs

<details close>
<summary>Answer</summary>
b
</details>

---

Your company wants to move away from manually managing Lambda in the AWS console and wants to upload and update them using AWS CloudFormation.

How do you declare an AWS Lambda function in CloudFormation? (Select two)

+ Upload all the code to CodeCommit and refer to the CodeCommit Repository in `AWS::Lambda::Function` block
+ Upload all the code as a zip to S3 and refer the object in `AWS::Lambda::Function` block
+ Upload all the code as a folder to S3 and refer the folder in `AWS::Lambda::Function` block
+ Write the AWS Lambda code inline in CloudFormation in the `AWS::Lambda::Function` block and reference the dependencies as a zip file stored in S3
+ Write the AWS Lambda code inline in CloudFormation in the `AWS::Lambda::Function block` as long as there are no third-party dependencies


<details close>
<summary>Answer</summary>
b,e
</details>

---

One of your Kinesis Stream is experiencing increased traffic due to a sale day. Therefore your Kinesis Administrator has split shards and thus you went from having 6 shards to having 10 shards in your Kinesis Stream. Your consuming application is running a KCL-based application on EC2 instances.

What is the maximum number of EC2 instances that can be deployed to process the shards?

+ 1
+ 6
+ 10
+ 20

<details close>
<summary>Answer</summary>
c
</details>

---

Your client wants to deploy a service on EC2 instances, and as EC2 instances are added into an ASG, each EC2 instance should be running 3 different Docker Containers simultaneously.

What Elastic Beanstalk platform should they choose?

+ Docker single-container platform
+ Custom platform
+ Third-party platform
+ Docker multi-container platform

<details close>
<summary>Answer</summary>
d
</details>

---

Which of the following CLI options will allow you to retrieve a subset of the attributes coming from a DynamoDB scan?

+ --filter-expression
+ --projection-expression
+ --page-size
+ --max-items

<details close>
<summary>Answer</summary>
b
</details>

---
You are implementing a banking application in which you need to update the Exchanges DynamoDB table and the AccountBalance DynamoDB table at the same time or not at all.

Which DynamoDB feature should you use?

+ DynamoDB Indexes
+ DynamoDB Transactions
+ DynamoDB TTL
+ DynamoDB Streams

<details close>
<summary>Answer</summary>
b
</details>

---

As part of your video processing application, you are looking to perform a set of repetitive and scheduled tasks asynchronously. Your application is deployed on Elastic Beanstalk.

Which Elastic Beanstalk environment should you set up for performing the repetitive tasks?

+ Setup a Worker environment and a `cron.yaml` file
+ Setup a Web Server environment and a `cron.yaml` file
+ Setup a Worker environment and a `.ebextensions` file
+ Setup a Web Server environment and a `.ebextensions` file

<details close>
<summary>Answer</summary>
a
</details>

---

An EC2 instance has an IAM instance role attached to it, providing it read and write access to the S3 bucket 'my_bucket'. You have tested the IAM instance role and both reads and writes are working. You then remove the IAM role from the EC2 instance and test both read and write again. Writes stopped working but reads are still working.

What is the likely cause of this behavior?

+ The EC2 instance is using cached temporary IAM credentials
+ Removing an instance role from an EC2 instance can take a few minutes before being active
+ When a read is done on a bucket, there's a grace period of 5 minutes to do the same read again
+ The S3 bucket policy authorizes reads

<details close>
<summary>Answer</summary>
d
</details>

---

Your company likes to operate multiple AWS accounts so that teams have their environments. Services deployed across these accounts interact with one another, and now there's a requirement to implement X-Ray traces across all your applications deployed on EC2 instances and AWS accounts.

As such, you would like to have a unified account to view all the traces. What should you in your X-Ray daemon set up to make this work? (Select two)

+ Create a role in the target unified account and allow roles in each sub-account to assume the role.
+ Configure the X-Ray daemon to use an IAM instance role
+ Create a user in the target unified account and generate access and secret keys
+ Configure the X-Ray daemon to use access and secret keys
+ Enable Cross Account collection in the X-Ray console


<details close>
<summary>Answer</summary>
a,b
</details>

---

You are deploying Lambda functions that operate on your S3 buckets to read files and extract key metadata. The Lambda functions are managed using SAM.

Which Policy should you insert in your serverless model template to give buckets read access?

+ SQSPollerPolicy
+ S3CrudPolicy
+ S3ReadPolicy
+ LambdaInvokePolicy


<details close>
<summary>Answer</summary>
c
</details>

---

You are running a web application where users can author blogs and share them with their followers. Most of the workflow is read based, but when a blog is updated, you would like to ensure that the latest data is served to the users (no stale data). The Developer has already suggested using ElastiCache to cope with the read load but has asked you to implement a caching strategy that complies with the requirements of the site.

Which strategy would you recommend?

+ Use a Lazy Loading strategy with TTL
+ Use a Write Through strategy
+ Use a Lazy Loading strategy without TTL
+ Use DAX

<details close>
<summary>Answer</summary>
b
</details>

---

You have created a DynamoDB table to support your application and provisioned RCU and WCU to it so that your application has been running for over a year now without any throttling issues. Your application now requires a second type of query over your table and as such, you have decided to create an LSI and a GSI on a new table to support that use case. One month after having implemented such indexes, it seems your table is experiencing throttling.

Upon looking at the table's metrics, it seems the RCU and WCU provisioned are still sufficient. What's happening?

+ The LSI is throttling so you need to provision more RCU and WCU to the LSI
+ Metrics are lagging in your CloudWatch dashboard and you should see the RCU and WCU peaking for the main table in a few minutes
+ Adding both an LSI and a GSI to a table is not recommended by AWS best practices as this is a known cause for creating throttles
+ The GSI is throttling so you need to provision more RCU and WCU to the GSI

<details close>
<summary>Answer</summary>
d
</details>

---

You need to load SSL certificates onto your Load Balancers and also have EC2 instances dynamically retrieve them when needed for service to service two-way TLS communication.

What service should you use to centrally manage and automatically renew these SSL certificates?

+ ACM
+ S3
+ KMS
+ IAM

<details close>
<summary>Answer</summary>
a
</details>

---
Your Lambda function processes files for your customers and as part of that process, it creates a lot of intermediary files it needs to store on its disk and then discard.

What is the best way to store temporary files for your Lambda functions that will be discarded when the function stops running?

+ Use the local directory /opt
+ Create a tmp/ directory in the source zip file and use it
+ Use an S3 bucket
+ Use the local directory /tmp

<details close>
<summary>Answer</summary>
d
</details>

---

You are using AWS SQS FIFO queues to get the ordering of messages on a per `user_id` basis.

As a developer, which message parameter should you set the value of `user_id` to guarantee the ordering?

+ MessageGroupId
+ MessageDeduplicationId 
+ MessageOrderId
+ MessageHash

<details close>
<summary>Answer</summary>
a
</details>

---


You are using AWS SQS FIFO queues to get the ordering of messages on a per `user_id` basis. On top of this, you would like to make sure that duplicate messages should not be sent to SQS as this would cause application failure.

As a developer, which message parameter should you set for deduplicating messages?

+ ReceiveRequestAttemptId
+ MessageGroupId
+ MessageDeduplicationId
+ ContentBasedDeduplication

<details close>
<summary>Answer</summary>
c
</details>

---

You would like to have a one-stop dashboard for all the CI/CD needs of one of your projects. You don't need heavy control of the individual configuration of each component in your CI/CD, but need to be able to get a holistic view of your projects.

Which service do you recommend?

+ CodeBuild
+ CodeDeploy
+ CodeStar
+ CodePipeline

<details close>
<summary>Answer</summary>
c
</details>

---

Your client has tasked you with finding a service that would enable you to get cross-account tracing and visualization.

Which service do you recommend?
+ AWS X-Ray
+ VPC FLow Logs
+ CloudWatch Events
+ CloudTrail

<details close>
<summary>Answer</summary>
a
</details>

---

You are looking to invoke an AWS Lambda function every hour (similar to a cron job) in a serverless way.

Which event source should you use for your AWS Lambda function?

+ Amazon S3
+ CloudWatch Events
+ SQS
+ Kinesis

<details close>
<summary>Answer</summary>
b
</details>

---
You are storing bids information on your betting application and you would like to automatically expire DynamoDB table data after one week.

What should you use?
+ Use DynamoDB Streams
+ Use DAX
+ Use TTL
+ Use a Lambda function

<details close>
<summary>Answer</summary>
c
</details>

---

You would like your Elastic Beanstalk environment to expose an HTTPS endpoint and an HTTP endpoint. The HTTPS endpoint should be used to get in-flight encryption between your clients and your web servers, while the HTTP endpoint should only be used to redirect traffic to HTTPS and support URLs starting with http://.

What must be done to configure this setup? (Select three)

+ Open up port 80 & port 443
+ Configure your EC2 instances to redirect HTTPS traffic to HTTP
+ Configure your EC2 instances to redirect HTTP traffic to HTTPS
+ Only open up port 443
+ Only open up port 80
+ Assign an SSL certificate to the Load Balancer

<details close>
<summary>Answer</summary>
a,c,f
</details>

---

You are creating a web application in which users can follow each other. Some users will be more popular than others and thus their data will be requested very often. Currently, the user data sits in RDS and it has been recommended by your Developer to use ElastiCache as a caching layer to improve the read performance. The whole dataset of users cannot sit in ElastiCache without incurring tremendous costs and therefore you would like to cache only the most often requested users profiles there. As your website is high traffic, it is accepted to have stale data for users for a while, as long as the stale data is less than a minute old.

What caching strategy do you recommend implementing?

+ Use a Lazy Loading strategy with TTL
+ Use a Lazy Loading strategy without TTL
+ Use a Write Through strategy with TTL
+ Use a Write Through strategy without TTL

<details close>
<summary>Answer</summary>
a
</details>

---

Which environment variable can be used by AWS X-Ray SDK to ensure that the daemon is correctly discovered on ECS?

+ AWS_XRAY_TRACING_NAME
+ AWS_XRAY_CONTEXT_MISSING
+ AWS_XRAY_DAEMON_ADDRESS
+ AWS_XRAY_DEBUG_MODE

<details close>
<summary>Answer</summary>
c
</details>

---

Applications running on EC2 instances process messages from an SQS queue but sometimes they experience errors due to messages not being processed.

To isolate the messages, which option will help with further debugging?

+ Increase the VisibilityTimeout
+ Use DeleteMessage
+ Reduce the VisibilityTimeout
+ Implement a Dead Letter Queue

<details close>
<summary>Answer</summary>
d
</details>

---

A developer created an online shopping application that runs on EC2 instances behind load balancers. The same web application version is hosted on several EC2 instances and the instances run in an Auto Scaling group. The application uses STS to request credentials but after an hour your application stops working.

What is the most likely cause of this issue?

+ The IAM service is experiencing downtime once an hour
+ Your IAM policy is wrong
+ A lambda function revokes your access every hour
+ Your application needs to renew the credentials after 1 hour when they expire


<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
AWS Security Token Service (AWS STS) is a web service that enables you to request temporary, limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that you authenticate (federated users). By default, AWS Security Token Service (STS) is available as a global service, and all AWS STS requests go to a single endpoint at https://sts.amazonaws.com.

Credentials that are created by using account credentials can range from 900 seconds (15 minutes) up to a maximum of 3,600 seconds (1 hour), with a default of 1 hour. Hence you need to renew the credentials post expiry.
</details>

---

Your team lead has finished creating a CodeBuild project in the management console and a build spec has been defined for the project. After the build is run, CodeBuild fails to pull a Docker image into the build environment.

What is the most likely cause?

+ The Docker image is too big
+ The Docker image is missing some tags
+ CodeBuild cannot work with custom Docker images
+ Missing IAM permissions for the CodeBuild Service

<details close>
<summary>Answer</summary>
d
</details>

---

You've just deployed an AWS Lambda function. The lambda function will be invoked via the API Gateway. The API Gateway will need to control access to it.

Which of the following mechanisms is not supported for API Gateway?

+ IAM permissions with sigv4
+ STS
+ Lambda Authorizer
+ Cognito User Pools

<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
The AWS Security Token Service (STS) is a web service that enables you to request temporary, limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that you authenticate (federated users). However, is not supported at the time with API Gateway.
</details>

---

Your development team has created a popular mobile app written for Android. The team is looking for a technology that can send messages to mobile devices using a mobile app.

Mobile app users will register and be given permissions to access AWS resources. Which technology would you recommend for subscribing users to messages?

+ SES
+ SQS
+ Kinesis
+ SNS

<details close>
<summary>Answer</summary>
d
</details>

---

You are working for a small organization that does not have a database administrator and the organization needs to install a database on the cloud quickly to support an accounting application used by thousands of users. The application will act as a backend and will perform (CRUD) operations such as create, read, update and delete as well as inner joins.

Which database is best suited for this scenario?

+ Redshift
+ DynamoDB
+ RDS
+ ElastiCache

<details close>
<summary>Answer</summary>
c
</details>

---

You are a developer working on AWS Lambda functions that are triggered by Amazon API Gateway and would like to perform testing on a low volume of traffic for new API versions.

Which of the following features will accomplish this task?

+ Custom Authorizers
+ Stage Variables
+ Mapping Templates
+ Canary Deployment

<details close>
<summary>Answer</summary>
d
</details>

<details close>
<summary>Note</summary>
In a canary release deployment, total API traffic is separated at random into a production release and a canary release with a preconfigured ratio. Typically, the canary release receives a small percentage of API traffic and the production release takes up the rest. The updated API features are only visible to API traffic through the canary. You can adjust the canary traffic percentage to optimize test coverage or performance.
</details>

---

When your company first created an AWS account, you began with a single sign-in principal called a root user account that had complete access to all AWS services and resources.

What should you do to adhere to best practices for using the root user account?


+ It should be accessible by no one, throw away the passwords after creating the account
+ It should be accessible by 3 to 6 members of the IT team
+ It should be accessible using the access key id and secret access key
+ It should be accessible by one admin only after enabling Multi-factor authentication

<details close>
<summary>Answer</summary>
d
</details>

---

Your company is new to cloud computing and would like to host a static HTML5 website on the cloud and be able to access it via domain www.mycompany.com. You have created a bucket in Amazon Simple Storage Service (S3), enabled website hosting, and set the index.html as the default page. Finally, you create an Alias record in Amazon Route 53 that points to the S3 website endpoint of your S3 bucket.

When you test the domain www.mycompany.com you get the following error: 'HTTP response code 403 (Access Denied)'. What can you do to resolve this error?


+ Enable CORS
+ Create an IAM role
+ Create a bucket policy
+ Enable Ecrpytion

<details close>
<summary>Answer</summary>
c
</details>

---

You were assigned to a project that requires the use of the AWS CLI to build a project with AWS CodeBuild. Your project's root directory includes the buildspec.yml file to run build commands and would like your build artifacts to be automatically encrypted at the end.

How should you configure CodeBuild to accomplish this?

+ Specify a KMS key to use
+ Use an AWS Lambda Hook
+ Use the AWS Encryption SDK
+ Use In Flight encryption (SSL)

<details close>
<summary>Answer</summary>
a
</details>

---

You are responsible for an application that runs on multiple Amazon EC2 instances. In front of the instances is an Internet-facing load balancer that takes requests from clients over the internet and distributes them to the EC2 instances. A health check is configured to ping the index.html page found in the root directory for the health status. When accessing the website via the internet visitors of the website receive timeout errors.

What should be checked first to resolve the issue?

+ Security Groups
+ IAM Roles
+ The application is down
+ The ALB is warming up

<details close>
<summary>Answer</summary>
a
</details>

---

A security company is requiring all developers to perform server-side encryption with customer-provided encryption keys when performing operations in AWS S3. Developers should write software with C# using the AWS SDK and implement the requirement in the PUT, GET, Head, and Copy operations.

Which of the following encryption methods meets this requirement?

+ Client-Side Encryption
+ SSE-KMS
+ SSE-C
+ SSE-S3


<details close>
<summary>Answer</summary>
c
</details>

---

A company's e-commerce application becomes slow when traffic spikes. The application has a three-tier architecture (web, application and database tier) that uses synchronous transactions. The development team at the company has identified certain bottlenecks in the application tier and it is looking for a long term solution to improve the application's performance.

As a developer associate, which of the following solutions would you suggest to meet the required application response times while accounting for any traffic spikes?

+ Leverage horizontal scaling for the web and application tiers by using Auto Scaling groups and Application Load Balancer
+ Leverage SQS with asynchronous AWS Lambda calls to decouple the application and data tiers
+ Leverage horizontal scaling for the application's persistence layer by adding Oracle RAC on AWS
+ Leverage vertical scaling for the application instance by provisioning a larger Amazon EC2 instance size


<details close>
<summary>Answer</summary>
a
</details>

---

An e-commerce company has multiple EC2 instances operating in a private subnet which is part of a custom VPC. These instances are running an image processing application that needs to access images stored on S3. Once each image is processed, the status of the corresponding record needs to be marked as completed in a DynamoDB table.

How would you go about providing private access to these AWS resources which are not part of this custom VPC?


+ Create a gateway endpoint for S3 and add it as a target in the route table of the custom VPC. Create an interface endpoint for DynamoDB and then connect to the DynamoDB service using the private IP address
+ Create a separate gateway endpoint for S3 and DynamoDB each. Add two new target entries for these two gateway endpoints in the route table of the custom VPC
+ Create a gateway endpoint for DynamoDB and add it as a target in the route table of the custom VPC. Create an API endpoint for S3 and then connect to the S3 service using the private IP address
+ Create a separate interface endpoint for S3 and DynamoDB each. Then connect to these services using the private IP address


<details close>
<summary>Answer</summary>
b
</details>

<details close>
<summary>Note</summary>
Endpoints are virtual devices. They are horizontally scaled, redundant, and highly available VPC components. They allow communication between instances in your VPC and services without imposing availability risks or bandwidth constraints on your network traffic.

A VPC endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by AWS PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network.

There are two types of VPC endpoints: interface endpoints and gateway endpoints. An interface endpoint is an elastic network interface with a private IP address from the IP address range of your subnet that serves as an entry point for traffic destined to a supported service.

A gateway endpoint is a gateway that you specify as a target for a route in your route table for traffic destined to a supported AWS service. The following AWS services are supported:

Amazon S3

DynamoDB
</details>

---

A company ingests real-time data into its on-premises data center and subsequently a daily data feed is compressed into a single file and uploaded on Amazon S3 for backup. The typical compressed file size is around 2 GB.

Which of the following is the fastest way to upload the daily compressed file into S3?

+ Upload the compressed file in a single operation
+ Upload the compressed file using multipart upload
+ FTP the compressed file into an EC2 instance that runs in the same region as the S3 bucket. Then transfer the file from the EC2 instance into the S3 bucket
+ Upload the compressed file using multipart upload with S3 transfer acceleration

<details close>
<summary>Answer</summary>
d
</details>

---

A developer has created a new Application Load Balancer but has not registered any targets with the target groups.

Which of the following errors would be generated by the Load Balancer?

+ HTTP 503: Service unavailable
+ HTTP 500: Internal server error
+ HTTP 500: Internal server error
+ HTTP 504: Gateway timeout


<details close>
<summary>Answer</summary>
a
</details>

---

A company has recently launched a new gaming application that the users are adopting rapidly. The company uses RDS MySQL as the database. The development team wants an urgent solution to this issue where the rapidly increasing workload might exceed the available database storage.

As a developer associate, which of the following solutions would you recommend so that it requires minimum development effort to address this requirement?


+ Enable storage auto-scaling for RDS MySQL
+ Migrate RDS MySQL database to Aurora which offers storage auto-scaling
+ Migrate RDS MySQL database to DynamoDB which automatically allocates storage space when required
+ Create read replica for RDS MySQL

<details close>
<summary>Answer</summary>
a
</details>

---

A financial services company has developed a REST API which is deployed in an Auto Scaling Group behind an Application Load Balancer. The API stores the data payload in DynamoDB and the static content is served through S3. Upon analyzing the usage pattern, it's found that 80% of the read requests are shared across all users.

As a Developer Associate, how can you improve the application performance while optimizing the cost with the least development effort?

+ Enable DynamoDB Accelerator (DAX) for DynamoDB and CloudFront for S3
+ Enable ElastiCache Redis for DynamoDB and CloudFront for S3
+ Enable DAX for DynamoDB and ElastiCache Memcached for S3
+ Enable ElastiCache Redis for DynamoDB and ElastiCache Memcached for S3


<details close>
<summary>Answer</summary>
a
</details>

---

The development team at an e-commerce company is preparing for the upcoming Thanksgiving sale. The product manager wants the development team to implement appropriate caching strategy on Amazon ElastiCache to withstand traffic spikes on the website during the sale. A key requirement is to facilitate consistent updates to the product prices and product description, so that the cache never goes out of sync with the backend.

As a Developer Associate, which of the following solutions would you recommend for the given use-case?


+ Use a caching strategy to update the cache and the backend at the same time
+ Use a caching strategy to write to the backend first and wait for the cache to expire via TTL
+ Use a caching strategy to write to the cache directly and sync the backend at a later time
+ Use a caching strategy to write to the backend first and then invalidate the cache


<details close>
<summary>Answer</summary>
d
</details>

---

You are working with a t2.small instance bastion host that has the AWS CLI installed to help manage all the AWS services installed on it. You would like to know the security group and the instance id of the current instance.

Which of the following will help you fetch the needed information?

+ Create an IAM role and attach it to your EC2 instance that helps you perform a 'describe' API call
+ Query the user data at http://169.254.169.254/latest/user-data
+ Query the metadata at http://169.254.169.254/latest/meta-data
+ Query the user data at http://254.169.254.169/latest/meta-data



<details close>
<summary>Answer</summary>
c
</details>

---

A popular mobile app retrieves data from an AWS DynamoDB table that was provisioned with read-capacity units (RCU’s) that are evenly shared across four partitions. One of those partitions is receiving more traffic than the other partitions, causing hot partition issues.

What technology will allow you to reduce the read traffic on your AWS DynamoDB table with minimal effort?

+ More partitions
+ DynamoDB Streams
+ ElastiCache
+ DynamoDB DAX

<details close>
<summary>Answer</summary>
d
</details>

---

An IT company uses AWS CloudFormation templates to provision their AWS infrastructure for Amazon EC2, Amazon VPC, and Amazon S3 resources. Using cross-stack referencing, a developer creates a stack called `NetworkStack` which will export the `subnetId` that can be used when creating EC2 instances in another stack.

To use the exported value in another stack, which of the following functions must be used?

+ `!Ref`
+ `!ImportValue`
+ `!GetAtt`
+ `!Sub`

<details close>
<summary>Answer</summary>
b
</details>