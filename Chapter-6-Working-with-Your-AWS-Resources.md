# Working with Your AWS Resources

## The AWS Management Console
- The AWS Management Console also known as the AWS Console or the AWS Web Console, is a web interface you can use to manage all of your AWS cloud resources using a web browser, including compute, storage, and networking
- There are two ways to sign in: as the **root user** or as an **Identity and Access Management (IAM) user**.
  -  **root user**: enter the **email address** and **password** associated with your AWS account 
  -  To log in as an **IAM user**: enter the enter your **account ID or account alias** + **IAM user name** + **Password**
- **Resource groups**: let you view, manage, and automate tasks on multiple AWS resources at a time.
  - A resource group is a collection of AWS resources in the same region that match the results of a query. You can create a resource group from a query based on resource tags or from a CloudFormation Stack.
- **Resource tags** are optional metadata that you can assign to AWS resources. A tag must contain a label called a key and may optionally contain a value.
  - For example, you may tag your production resources using a key named Environment and a value named Production.

## The AWS Command Line Interface
- AWS Command Line Interface (AWS CLI) is a unified command-line tool to manage your AWS resources.

## Software Development Kits
- Application developers can use an SDK to integrate their applications with AWS services easily and reliably. 
- SDKs save application developers from having to write low-level code to interact directly with the AWS service API endpoints. 
- Instead, the developer just uses the SDK’s well-documented methods to learn how to incorporate it into their application.
- Mobile Software Development Kits
  - AWS also offers mobile SDKs for the development of applications for smartphones and tablets
