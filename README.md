# AWS Learning Notes

## Setup

- [Register for AWS account](https://aws.amazon.com/free)

- Install AWS CLI on macOS `brew install awscli`

- [ ] Enable 2FA for root account

## Launch EC2 Instance

- [Launch EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:)

## Connect With SSH

- Create a key pair -- link in EC2 UI

- [Launch EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:) with key pair

- Instance list -- Instance -- Connect -- SSH instructions

## Connect With Session Manager

- [Setting up Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started.html)

- [Complete Session Manager prerequisites](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-prerequisites.html)

- [Verify or add instance permissions for Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-instance-profile.html)
  - [Create a custom IAM role for Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/getting-started-create-iam-instance-profile.html)
    - Create policy `SessionManagerPolicy`
    - Create role `SessionManagerRoleForEC2`; add `SessionManagerPolicy`

SessionManagerPolicy

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ssm:UpdateInstanceInformation",
                "ssmmessages:CreateControlChannel",
                "ssmmessages:CreateDataChannel",
                "ssmmessages:OpenControlChannel",
                "ssmmessages:OpenDataChannel"
            ],
            "Resource": "*"
        }
    ]
}
```

SessionManagerRoleForEC2 trusted entities

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "sts:AssumeRole"
            ],
            "Principal": {
                "Service": [
                    "ec2.amazonaws.com"
                ]
            }
        }
    ]
}
```

- [Launch EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:)
  - Use an [Amazon Machine Image with SSM Agent preinstalled](https://docs.aws.amazon.com/systems-manager/latest/userguide/ami-preinstalled-agent.html)

### Default Host Management Configuration

- [Verify or add instance permissions for Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-instance-profile.html)
  - [Default Host Management Configuration](https://docs.aws.amazon.com/systems-manager/latest/userguide/managed-instances-default-host-management.html)
    - Also tried this setting at account level, but it did not result in Session Manager being able to connect to EC2 instances by default

## Run EC2 Instance, Connect




For now, allow SSH

- [ ] Check SSM Agent is running `sudo systemctl status amazon-ssm-agent`

Yes

- [ ] Connect to instance -- Session Manager

- [ ] Error -- Session Manager not able to connect

- [ ] Check if role is attached to instance?

- [ ] [Attach or replace an instance profile](https://aws.amazon.com/premiumsupport/knowledge-center/attach-replace-ec2-instance-profile/)

- [ ] [Modify IAM role for instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#ModifyIAMRole)

- [ ] [Control user session access to managed nodes](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-restrict-access.html)

- [ ] [Configure session preferences](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-configure-preferences.html)
