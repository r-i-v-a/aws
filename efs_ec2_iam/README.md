# Connect EC2, EFS With IAM Role

## UI

- [ ] [Use Amazon EFS With EC2, Quick Create](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEFS.html)

- [ ] [Getting Started With Amazon Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/getting-started.html)

- [Create Your Amazon EFS File System](https://docs.aws.amazon.com/efs/latest/ug/gs-step-two-create-efs-resources.html)
  - [Amazon Elastic File System -- Create File System](https://console.aws.amazon.com/efs/)
  - Enter a name; select default VPC
  - Filesystem is created with [recommended settings](https://docs.aws.amazon.com/efs/latest/ug/gs-step-two-create-efs-resources.html)
  
- [Create Your EC2 Resources and Launch Your EC2 Instance](https://docs.aws.amazon.com/efs/latest/ug/gs-step-one-create-ec2-resources.html)
  - [EC2 Dashboard -- Launch Instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#LaunchInstances:)
  - Create new key pair
  - Network
    - Select default VPC, same as used by EFS
  - Subnet
    - Select a default subnet in any Availability Zone in the same Region
  - Security group
    - Select existing security group `default`
  - File systems
    - EFS -- select EFS file system created before
    - Mount point `/mnt/efs/fs1`

- [ ] [Test the EFS File System](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEFS.html#efs-test-file-system)

- [ ] Unable to SSH to EC2 instance (when using default security group)

```bash
$ df -T
Filesystem     Type            1K-blocks    Used        Available Use% Mounted on
devtmpfs       devtmpfs             4096       0             4096   0% /dev
tmpfs          tmpfs              463484       0           463484   0% /dev/shm
tmpfs          tmpfs              185396     456           184940   1% /run
/dev/nvme0n1p1 xfs               8310764 1555308          6755456  19% /
tmpfs          tmpfs              463488       0           463488   0% /tmp
tmpfs          tmpfs               92696       0            92696   0% /run/user/1000
127.0.0.1:/    nfs4     9007199254739968       0 9007199254739968   0% /mnt/efs/fs1
```

```bash
[ec2-user@ip-172-31-20-0 ~]$ sudo touch /mnt/efs/fs1/my_file_1.txt
[ec2-user@ip-172-31-20-0 ~]$ sudo touch /mnt/efs/fs1/my_file_2.txt
[ec2-user@ip-172-31-20-0 ~]$ ls /mnt/efs/fs1/
my_file_1.txt  my_file_2.txt
```

```bash
[ec2-user@ip-172-31-20-0 ~]$ sudo touch /mnt/efs/fs1/my_file_1.txt
[ec2-user@ip-172-31-20-0 ~]$ sudo touch /mnt/efs/fs1/my_file_2.txt
[ec2-user@ip-172-31-20-0 ~]$ ls /mnt/efs/fs1/
my_file_1.txt  my_file_2.txt
```

- [ ] [Delete the EFS File System](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEFS.html#efs-clean-up)

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
