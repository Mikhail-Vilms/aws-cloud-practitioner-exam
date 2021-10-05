# Securing Your AWS Resources

## AWS Identity and Access Management

### Authentication
- **Secure Shell Key Pairs**:
  - The industry-standard tool for safely encrypting remote login sessions is the **Secure Shell (SSH) protocol**.
  - Encryption converts those plain-text data packets into what looks like gibberish. Indeed, ideally—assuming no one has yet cracked the encryption algorithm you’re using—that text is and will remain gibberish, unless you happen to have the decryption key required to decrypt it. The SSH protocol manages the encryption and decryption steps in the process as long as compatible keys are present at both ends of the connection
  - When you launch a new EC2 Linux instance (and a heavy majority of EC2 instances are running one flavor or another of Linux), you’ll be prompted either to use an existing SSH key pair or to create a new one.
  - Once the private key is downloaded, you open SSH sessions to your instances by invoking the key in a connection command that might look something like this: ```ssh -i keyname.pem ec2-user@<public_ip_address_of_instance>```
  
### Users, Groups, and Roles
