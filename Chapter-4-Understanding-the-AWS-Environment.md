# Chapter 4: Understanding the AWS Environment

## AWS Regions
- https://aws.amazon.com/about-aws/global-infrastructure/

- When you request an **instance of an AWS service**, the underlying hardware of that instance will be carved out of a server running in **one — and only one — AWS Region**.
- Dividing resources among regions lets you do the following:
  - Locate your infrastructure geographically closer to your users to allow access with the lowest possible latency
  - Locate your infrastructure within national borders to meet regulatory compliance with legal and banking rules
  - Isolate groups of resources from each other and from larger networks to allow the greatest possible security
- Some AWS resources are not visibly tied to any one region. Even if those resources are, technically, running on hardware that must exist within a single region, AWS presents them as global. Here are some examples of global services:
  - AWS Identity and Access Management (IAM) is the service for managing the way access to your account resources is achieved by way of users and groups, roles, and policies.
  - Amazon CloudFront is the content delivery network you can use to lower access latency for your application users by storing cached versions of frequently requested data at AWS edge locations
  - While Amazon S3 buckets must, as we mentioned earlier, exist within a single region, S3 is nevertheless considered a global service ??? - WHY

## Availability Zones
- An AWS Region encompasses at least two distinct Availability Zones connected to each other with low-latency network links
- A single AZ is made up of at least one fully independent data center that’s built on hardware and power resources used by no other AZ.
- AWS resources based in a single region can be requested and run within any AZ in the region
- The advantage of this level of separation is that if one AZ loses power or suffers some kind of catastrophic outage, the chances of it spreading to a second AZ in the region are minimal. You can assume that no two AZs will ever share resources from a single physical data center.
- You’ll only get the full value out of the resources you run within an AWS Region by **properly organizing them into network segments (or subnets)**.
  - **A subnet is really nothing more than a single block of Internet Protocol (IP) addresses.**
  - Any compute device that requires network connectivity must be identified by an IP address that’s unique to the network.
  - The servers or other networked devices that are assigned an IP address within one subnet are generally able to communicate with each other by default but might have traffic coming into and/or out of the subnet restricted by firewall rules.
  -  AWS describes the address range available to a particular subnet as something like *172.31.16.0/20* or *172.31.48.0/20*. Whenever you see such a notation in an AWS configuration dialog, you’ll now know that you’re looking at the IP address range for a subnet.
- AWS slays the application failure dragon using **autoscaling and load balancing**:
  - Autoscaling can be configured to replace or replicate a resource to ensure that a predefined service level is maintained regardless of changes in user demand or the availability of existing resources.
  - Load balancing orchestrates the use of multiple parallel resources to direct user requests to the server resource that’s best able to provide a successful experience. A common use case for load balancing is to coordinate the use of primary and (remote) backup resources to cover for a failure

## Edge Locations
- An edge location is a site where AWS deploys physical server infrastructure to provide lowlatency user access to Amazon-based data.
- The important difference is that your garden-variety data centers are designed to offer the full range of AWS services, including the complete set of EC2 instance types and the networking infrastructure customers would need to shape their compute environments. Edge locations, on the other hand, are much more focused on a smaller set of roles and will therefore stock a much narrower set of hardware.
- Perhaps the best-known tenant of edge locations is CloudFront, Amazon’s CDN service. How does that work? Let’s say you’re hosting large media fi les in S3 buckets. If users would have to retrieve their files directly from the bucket each time they were requested, delivery—especially to end users living continents away from the bucket location—would be relatively slow. But if you could store cached copies of the most popular fi les on servers located geographically close to your users, then they wouldn’t have to wait for the original file to be retrieved but could be enjoying the cached copy in a fraction of the time.
- **AWS edge locations are globally distributed data servers that can store cached copies of AWS-based data from which — on behalf of the CloudFront service — they can be efficiently served to end users**

## Shared Responsibility Model
- The cloud itself consists of the physical buildings, servers, and networking hardware used by AWS data centers. 
- AWS is responsible for making sure that its locations are secure, reliably powered, and properly maintained. 
- AWS is also on the hook for patching, encrypting (where relevant), and maintaining the operating systems and virtualization software running its physical servers and for the software running its managed services
- What exactly is “managed” and what’s “unmanaged”:
- ![image](https://user-images.githubusercontent.com/57194114/135784608-fa74bce0-2a52-4ae3-b6ae-83265c9677bb.png)
- ![image](https://user-images.githubusercontent.com/57194114/135784657-0ec3c9a9-4bd6-4147-afda-56dbb5b1f3f2.png)

