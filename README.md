# AWS Learning Notes

## Setup

- [Register for AWS account](https://aws.amazon.com/free)

- Install AWS CLI on macOS `brew install awscli`

## Run EC2 instance, connect with Session Manager

- [Setting up Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started.html)
  - [Complete Session Manager prerequisites](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-prerequisites.html)
  - [Verify or add instance permissions for Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-instance-profile.html)
    - [Default Host Management Configuration](https://docs.aws.amazon.com/systems-manager/latest/userguide/managed-instances-default-host-management.html)
      - Using default role `service-role/AWSSystemsManagerDefaultEC2InstanceManagementRole`

- [Amazon Machine Images with SSM Agent preinstalled](https://docs.aws.amazon.com/systems-manager/latest/userguide/ami-preinstalled-agent.html)

- [ ] [Launch EC2 instance](https://eu-north-1.console.aws.amazon.com/ec2/home?region=eu-north-1#LaunchInstances:)

- [ ] Connect to instance -- Session Manager

- [ ] Error -- Session Manager not able to connect

- [ ] [Verify or add permissions for Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-instance-profile.html)

- [ ] [Control user session access to managed nodes](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-restrict-access.html)

- [ ] [Configure session preferences](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-getting-started-configure-preferences.html)
