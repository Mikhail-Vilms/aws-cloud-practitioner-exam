# Securing Your AWS Resources

## AWS Identity and Access Management

### Authentication
- **Secure Shell Key Pairs**:
  - The industry-standard tool for safely encrypting remote login sessions is the **Secure Shell (SSH) protocol**.
  - Encryption converts those plain-text data packets into what looks like gibberish. Indeed, ideally—assuming no one has yet cracked the encryption algorithm you’re using—that text is and will remain gibberish, unless you happen to have the decryption key required to decrypt it. The SSH protocol manages the encryption and decryption steps in the process as long as compatible keys are present at both ends of the connection
  - When you launch a new EC2 Linux instance (and a heavy majority of EC2 instances are running one flavor or another of Linux), you’ll be prompted either to use an existing SSH key pair or to create a new one.
  - Once the private key is downloaded, you open SSH sessions to your instances by invoking the key in a connection command that might look something like this: ```ssh -i keyname.pem ec2-user@<public_ip_address_of_instance>```
  
### Users, Groups, and Roles
- **IAM Users**: we can create IAM Users from IAM Dashboard
- **IAM Groups**: 
  - As your organization devotes more team members to your AWS infrastructure, manually assigning permissions to each individual user one at a time will become a tedious and timeconsuming chore.
  - Using groups to administrate the permissions associated with multiple users in batches can get all that done much more efficiently.
    - You could, for instance, have one group called EC2-admins and a second called S3-admins. When someone new signed up to your team, you would only need to create an IAM user and then attach it to the appropriate group. The user would automatically inherit all the permissions of that group.
- **IAM Role**:
  - Like users and groups, IAM roles define the limits for what can be done within your AWS account.
  - The important difference is that, unlike users and groups, roles are, for the most part, used by applications and services rather than people
  - When creating a role, you begin by defining a trusted entity—the entity (or beneficiary) that will be trusted to use the role.  That entity could be an AWS service (like EC2), an identity provided by a **third-party federated identify provider** (like Google or Amazon Cognito — which allow a digital identity to be linked across multiple identity management systems), or a different AWS account.

### Providing Federated Access
-  You can integrate third-party standards like the Security Assertion Markup Language 2.0 (SAML) or Microsoft’s Active Directory into your infrastructure. This lets you use users’ existing login sessions to add single sign-on (SSO) across your AWS infrastructure and enable seamless access between your mobile apps and backend resources like DynamoDB databases or S3-based objects
-  Besides the IAM role configuration options you saw a bit earlier in this chapter, federated access to AWS resources can be handled through the AWS Single Sign-On service.

### Credential Report
- Accessed from the IAM Dashboard, a credential report displays a simple interface with no more (or less) than one lonely button: Download Report.
- Reports contain important information about the state of your account security, listing all current IAM users and giving you key intelligence, such as when each of them last logged in, whether they have MFA enabled, whether they have active access keys, and when those keys were last rotated.

## Encryption
## Regulatory Compliance (AWS Artifact)
