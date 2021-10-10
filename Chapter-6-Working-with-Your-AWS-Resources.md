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
- A CloudWatch alarm watches over the value of a single metric. 
- If the metric crosses a threshold that you specify (and stays there), the alarm will take an action.
- The action can be one of the following:
  - Notification using Simple Notification Service
  - Auto Scaling action
    - By specifying an EC2 Auto Scaling action, the EC2 Auto Scaling service can add or remove EC2 instances in response to changing demand.
  - EC2 action
    - If you’re monitoring a specific instance that’s having a problem, you can use an EC2 action to stop, terminate, or recover the instance. 

#### CloudWatch Dashboards
- CloudWatch dashboards are your one-stop shop for keeping an eye on all of your important metrics. 
- You can create multiple dashboards and add to them metric graphs, the latest values for a metric, and CloudWatch alarms.

#### CloudWatch Logs
- CloudWatch Logs collects and stores log files from AWS and non-AWS sources and makes it easy to view, search, and extract custom metrics from them
- A **log event** is analogous to a line in a log file and always contains a timestamp and an event message.
- CloudWatch Logs organizes log events by **log streams** by storing log events from the same source in a single log stream.
- CloudWatch further organizes log streams into **log groups**.
- CloudWatch Logs stores log events indefinitely by default, but you can configure a log group’s retention settings to delete events automatically.
- A **metric filter** extracts data from log events in a log group and stores that data in a custom CloudWatch metric.

#### CloudWatch Events
- The CloudWatch Events feature lets you continuously monitor for specifi c events that represent a change in your AWS resources—particularly write-only API operations—and take an action when they occur.
- CloudWatch Events can then automatically and immediately take actions in response to those events.
  -  For example, an EC2 instance going from the running state to the stopped state would be an event.
  -  An IAM user logging into the AWS Management Console would also be an event.
- CloudWatch responds to events as they occur, in real time. Unlike CloudWatch alarms, which take action when a metric crosses and remains crossing a numeric threshold, CloudWatch events trigger immediately.

## CloudTrail
- CloudTrail keeps detailed event logs of every action that occurs against your AWS resources. 
- Each event that CloudTrail logs includes the following parameters:
  - The service. Specifically, this is the address of the service’s global endpoint, such as iam.amazonaws.com for IAM (Event Source ???)
  - The name of the API action performed, such as RunInstances, CreateUser, or PutObject
  - The region the resource is located in. For global services, this is always us-east-1
  - Response elements. In the case of an API operation that changes or creates a resource, this contains information about the results of the action. For example, the response elements for a RunInstances action to launch an EC2 instance would yield information such as the instance ID and private IP address
  - The principal that made the request. This may include the type of principal (IAM user or role), its Amazon resource name (ARN), and the name
  - The date and time of the request, given in coordinated universal time (UTC)
  - The IP address of the requester
- **```API and Non-API Events```**
  - API actions include things such as launching an instance, creating an S3 bucket, creating a new IAM user, or taking an EBS snapshot
    - Note that the term API action has nothing to do with how the action was performed. For example, terminating an EC2 instance is an API event whether you do it via the AWS Management Console, the AWS command-line interface, or an AWS software development kit.
  - Non-API actions include everything else, such as logging into the management console
- **```Management and Data Events(???)```**
  - Management events — also known as control plane operations — are operations that a principal (such as a user or service) attempts to execute against an AWS resource 
  - Data events consist of S3 object-level activity and Lambda function executions, both of which tend to be high volume. As such, CloudTrail treats data events as separate from management events.
- Event History
  - When you open an AWS account, CloudTrail begins logging all of your management events automatically.
  - It stores 90 days of management events in the event history, which you can view, search, and download at any time. 
  - The event history log doesn’t record data events. 
- A **trail** is a confi guration that directs CloudTrail to record specifi ed events in log files and deliver them to an S3 bucket
  - You can also confi gure CloudTrail to send a trail log to CloudWatch Logs, making them available for storage, searching, and metric filtering. 
