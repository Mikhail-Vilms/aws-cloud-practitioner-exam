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
  - AWS Mobile SDK for Android
  - AWS Mobile SDK for iOS
  - AWS Mobile SDK for Unity
  - AWS Mobile SDK for .NET and Xamarin
  - AWS Amplify
- Internet of Things Device Software Development Kits
  - You can use the AWS IoT SDKs to create applications that run on Internet of Things (IoT) devices, such as sensors, microcontrollers, smart appliances, smart lightbulbs, and AWS IoT buttons.

## CloudWatch
- Amazon CloudWatch is a key service that helps you plan, monitor, and fine-tune your AWS infrastructure and applications. 
- It lets you collect, search, and visualize data from your applications and AWS resources in the form of logs, metrics, and events.

#### CloudWatch Metrics 
- A **metric** is a variable that contains a time-ordered set of data points. 
  - Each data point contains a timestamp, a value, and optionally a unit of measure. 
  - For example, a data point for the CPU Utilization metric for an EC2 instance may contain a timestamp of December 25, 2018 13:37, a value of 75, and Percent as the unit of measure.

#### CloudWatch Alarms 
