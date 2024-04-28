This repository contains my project submission for the Focus coding challenge, and it's structured into four main parts:

1) **my-app**: 
This module is a web application that allows users to enter text and upload a text file. Once the text file is uploaded, the application interacts with AWS S3 to store the file and then calls an API Gateway that triggers the my-lambda function.

2) **my-lambda**: 
Here lies the AWS Lambda function responsible for adding new records to the DynamoDB table. The data recorded includes the ID, input text, and a URL to the text file stored in the input S3 bucket.

3) **event-processor-lambda**: 
This Lambda function is activated by a DynamoDB stream whenever a new record is inserted. It automates the process of spinning up an EC2 instance, sending it commands to execute, and subsequently shutting it down after the tasks are completed.

4) **my-cdk**: 
This directory holds the cloud infrastructure code, which utilizes the AWS Cloud Development Kit (CDK). It's used to set up and manage the necessary cloud resources. You can initialize and deploy the CDK stack by running `npx cdk bootstrap` followed by `npx cdk deploy`.

Additionally, there's a `script.py` file. This script is crucial for processing; it downloads the record from S3, appends the provided text to it, and this action is performed by the EC2 instance which is orchestrated through the AWS Systems Manager (SSM) within the Lambda function.

**Testing Process:**
To test the system, you should install Node.js on your computer, then run `npm install` within the module directories to install all the necessary dependencies.

**References:**
The following resources provide additional information and reference material:
1) AWS SDK for JavaScript documentation to help with the AWS SDK functionalities.
2) AWS Identity and Access Management (IAM) documentation for understanding policy elements and actions.
3) AWS EC2 documentation for the 'runInstances' method, useful for creating EC2 instances programmatically.
4) The HTML input file element documentation to understand how file inputs are handled in web forms. 

The above summarization organizes your repository content and instructions on how to operate and test your submission. It’s designed to meet the specific tasks set by the coding challenge while incorporating best practices and adhering to AWS documentation.
