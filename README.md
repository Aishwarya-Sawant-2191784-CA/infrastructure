Assignment3 ReadMe (steps performed):
Download and install: https://awscli.amazonaws.com/AWSCLIV2.msi

Create IAM Accounts in dev and demo aws member accounts
Download and save the csv files after creation of accounts

Give AdministratorAccess Permission: 
https://console.aws.amazon.com/iam/home#/policies/arn%3Aaws%3Aiam%3A%3Aaws%3Apolicy%2FAdministratorAccess


Create dev profile for your dev AWS account and demo profile for your production AWS account. Do not set up a default profile.
aws configure --profile=dev
aws configure --profile=demo

Get the required key and ID from previously downloaded csv files
set region name: us-east-1
leave output format empty

Follow everything in "Create & Setup GitHub Repository for AWS Infrastructure"
-- No status checks needed


CloudFormation:
Documentation: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html

VPC Template:
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-vpc.html
=================
final command:
aws --profile=dev cloudformation create-stack --stack-name online-vpc --template-body file://csye6225-infra.yml
=================
Create an VPC with CIDR e.g.10.0.0.0/16 when parameters are asked
Similarly for subnet when parameters asked please enter the subnet range.
The template includes the creation of route tables and routes pointing to target Internet gateway and any IP.


Useful resources for this assignment:
------------------------
https://stackoverflow.com/questions/48142799/error-in-creating-multiple-subnets-in-aws-vpc
https://aws.amazon.com/premiumsupport/knowledge-center/create-attach-igw-vpc/

