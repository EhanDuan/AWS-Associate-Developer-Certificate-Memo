# Development with AWS Services Practice Set (Selections from top to bottom as a,b,c,d)

## Q1. The development team wants AWS Account A's Lambda function to AWS Account B's a DynamoDB table. Which of the following solutions would you recommend ?
+ Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account
+ Add a resource policy to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A
+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the role in Account B to allow the execution role of Lambda to assume this role. Update the Lambda function code to add the AssumeRole API call
+ Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssumeRole API call

Answer: c

Note:
+ Execution Role: The primary role in account A that gives Lambda function perimissions to do its work
+ Assume Role: A role in account B that Lambda function in account A assumes to gain access to cross-account resources

Source: https://aws.amazon.com/premiumsupport/knowledge-center/lambda-function-assume-iam-role/

