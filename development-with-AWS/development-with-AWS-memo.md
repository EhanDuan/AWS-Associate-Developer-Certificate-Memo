# Development with AWS Services Practice Set (Selections from top to bottom as a,b,c,d)

### Q1. The team wants AWS Account A's Lambda function to AWS Account B's DynamoDB table. Which of the following solutions would you recommend ?
+ Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account
+ Add a resource policy to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A
+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the role in Account B to allow the execution role of Lambda to assume this role. Update the Lambda function code to add the AssumeRole API call
+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssumeRole API call

Answer: c

Note
+ Execution Role: The primary role in account A that gives Lambda function perimissions to do its work
+ Assume Role: A role in account B that Lambda function in account A assumes to gain access to cross-account resources

Source: https://aws.amazon.com/premiumsupport/knowledge-center/lambda-function-assume-iam-role/

### Q2. The team wants to run a serverless data store service on two docker containers that share resources. Which of the following ECS configurations can be used to facilitate this use-case?
+ Put the two containers into a single task definition using a Fargate Launch Type
+ Put the two containers into two separate task definitions using a Fargate Launch Type
+ Put the two containers into two separate task definitions using a Fargate Launch Type
+ Put the two containers into a single task definition using an EC2 Launch Type

Answer: a

Note: Single task will share the resources.

Source: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/application_architecture.html


### Q3. The team uses CloudFormation to manage its AWS infrastructure. They has a network stack containing a VPC with subnets and a web application stack with EC2 instances and an RDS instance. The team wants to reference the VPC created in the network stack into its web application stack. Which of the following solutions would you recommend for the given use-case?
+ Create a cross-stack reference and use the Outputs output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
+ Create a cross-stack reference and use the Outputs output field to flag the value of VPC from the network stack. Then use Ref intrinsic function to reference the value of VPC into the web application stack
+ Create a cross-stack reference and use the Export output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
+ Create a cross-stack reference and use the Export output field to flag the value of VPC from the network stack. Then use Ref intrinsic function to reference the value of VPC into the web application stack

Answer: c

Note: Key words: export and import.

Source: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/walkthrough-crossstackref.html

### Q3. An application has its EC2 server fleet running behind an Application Load Balancer and the traffic is fronted by a CloudFront distribution. The team wants to decouple the user authentication process for the application so that the application servers can just focus on the business logic. Which of the following solutions would you recommend to address this use-case with minimal development effort?

+ Use Cognito Authentication via Cognito User Pools for your Application Load Balancer
+ Use Cognito Authentication via Cognito Identity Pools for your Application Load Balancer
+ Use Cognito Authentication via Cognito User Pools for your CloudFront distribution
+ Use Cognito Authentication via Cognito Identity Pools for your CloudFront distribution

Answer: a

Note:
+ Cognito User Pools is for users. Identity pools is for developers
+ Cognito cannot directly used with CloudFront

Source: 
+ https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-authenticate-users.html
+ https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html
+ https://aws.amazon.com/blogs/networking-and-content-delivery/authorizationedge-using-cookies-protect-your-amazon-cloudfront-content-from-being-downloaded-by-unauthenticated-users/

### Q4. A video encoding application running on an EC2 instance takes about 20 seconds on average to process each raw footage file. The application picks the new job messages from an SQS queue. The development team needs to account for the use-case when the video encoding process takes longer than usual so that the same raw footage is not processed by multiple consumers. Which of the following solutions would you recommend to address this use-case?
+ Use ChangeMessageVisibility action to extend a message's visibility timeout
+ Use DelaySeconds action to delay a message's visibility timeout
+ Use WaitTimeSeconds action to short poll and extend a message's visibility timeout
+ Use WaitTimeSeconds action to long poll and extend a message's visibility timeout

Answer: a

Note:
+ Avoid multiple consumers => extend visibility timeout

Source: 
+ https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html
+ https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_ChangeMessageVisibility.html

### Q5. The development team at an IT company has configured an Application Load Balancer (ALB) with a Lambda function A as the target but the Lambda function A is not able to process any request from the ALB. Upon investigation, the team finds that there is another Lambda function B in the AWS account that is exceeding the concurrency limits.How can the development team address this issue?





