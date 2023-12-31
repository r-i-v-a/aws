# EC2

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

- (Connect with SSH, confirm SSM Agent is running)
  - `sudo systemctl status amazon-ssm-agent`

- [Attach or replace an instance profile](https://aws.amazon.com/premiumsupport/knowledge-center/attach-replace-ec2-instance-profile/)
  - `SessionManagerRoleForEC2` role
  - Short wait for instance profile to take effect

- Instance list -- Instance -- Connect -- Session Manager

### Default Host Management Configuration

- [Verify or add instance permissions for Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-instance-profile.html)
  - [Default Host Management Configuration](https://docs.aws.amazon.com/systems-manager/latest/userguide/managed-instances-default-host-management.html)
    - Also tried this setting at account level, but it did not result in Session Manager being able to connect to EC2 instances by default

## Terminate EC2 Instance

- [Terminate EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#Home:)
