# SAML JavaScript Serverless Sample App
This repository contains sample code and [SAM templates](http://docs.aws.amazon.com/lambda/latest/dg/deploying-lambda-apps.html) for performing SAML AuthN/AuthZ flows to access AWS services from a user-facing application. The sample applications are written in JavaScript with minimal UI or extras in order to act as a tutorial for getting credentials and calling API Gateway endpoints protected by AWS_IAM. This can be extended for use against other AWS Service through IAM roles and other client application such as Native apps.

Detailed readme files are in each sub directory. A walk through tutorial is in a 2-part blog series located [here](https://aws.amazon.com/blogs/compute/saml-for-your-serverless-javascript-application-part-i/).


## Scenario 1
This is the "client-side" flow where SAML assertions are returned to the client via API Gateway. JavaScript in the browser passes the assertion to Amazon Cognito Identity and recieves AWS credentials back for signing requests to access other AWS Services.

![lambdasamlone_4.png](/Scenario1/lambdasamlone_4.png?raw=true)


## Scenario 2
This is the "backend" flow where a custom AWS Lambda function will use an XML parser to find out what Active Directory group the user belongs to and make an appropriate call for credentials on behalf of the user. It then shows how to generate and sign JWT tokens with KMS and use API Gateway custom authorizers so the client application can retrieve credentials to use with different AWS Services.

![lambdasamltwo_1.png](/Scenario2/lambdasamltwo_1.png?raw=true)