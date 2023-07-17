# Connect EC2, EFS With IAM Role

## UI

- [ ] [Getting Started With Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/getting-started.html)

- [Create Your Amazon EFS File System](https://docs.aws.amazon.com/efs/latest/ug/gs-step-two-create-efs-resources.html)
  - [Amazon Elastic File System -- Create File System](https://console.aws.amazon.com/efs/)
  - Enter a name; select default VPC
  - Filesystem is created with [recommended settings](https://docs.aws.amazon.com/efs/latest/ug/gs-step-two-create-efs-resources.html)
  
- [ ] [Create Your EC2 Resources and Launch Your EC2 Instance](https://docs.aws.amazon.com/efs/latest/ug/gs-step-one-create-ec2-resources.html)

- [EC2 Dashboard -- Launch Instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#LaunchInstances:)

- Create new key pair

- Network
  - Select default VPC, same as used by EFS

- Subnet
  - Select some default subnet in any Availability Zone in the same Region

- Security group
  - Select existing security group -- default

- File systems
  - EFS -- select EFS file system created before
  - Mount point `/mnt/efs/fs1`

- [ ] [Clean Up Resources](https://docs.aws.amazon.com/efs/latest/ug/gs-step-five-cleanup.html)

- [ ] [Using VPC Security Groups for Amazon EC2 Instances and Mount Targets](https://docs.aws.amazon.com/efs/latest/ug/network-access.html)

## CLI

- [ ] [Walkthrough: Create an Amazon EFS File System and Mount It on an Amazon EC2 Instance Using the AWS CLI](https://docs.aws.amazon.com/efs/latest/ug/wt1-getting-started.html)

## Launch EC2 Instance

- [Launch EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:)

## Connect With SSH

- Create a key pair -- link in EC2 UI

- [Launch EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:) with key pair

- Instance list -- Instance -- Connect -- SSH instructions

## Terminate EC2 Instance

- [Terminate EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:)

## Resources

- [Getting Started With Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/getting-started.html)
- [Use Amazon EFS With EC2, Quick Create](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEFS.html)
- [Using VPC Security Groups for Amazon EC2 Instances and Mount Targets](https://docs.aws.amazon.com/efs/latest/ug/network-access.html)
- [Walkthrough: Create an Amazon EFS File System and Mount It on an Amazon EC2 Instance Using the AWS CLI](https://docs.aws.amazon.com/efs/latest/ug/wt1-getting-started.html)
