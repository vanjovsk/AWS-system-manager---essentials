# AWS-system-manager---essentials
set up

Use SSM Agent (from AWS Systems Manager) to update, manage, and configure instances(EC2), vitual machines and on-premises servers.

First, find if the SSM Agent is already installed in the Operation System when you launch an EC2 instance created from an AMI.

This is how I verify the SSM Agent status:
1- lounch the ec2 instance
2- Connect the Instance. You can use SSH to connect to Linux instances or use Remote Desktop to connect to Windows Server instances.
3- Check the status of SSM Agent by running the command for your instance's OS type

list of commands:

Operating system	Command

Amazon Linux  ---> sudo status amazon-ssm-agent

Amazon Linux 2 and Amazon Linux 2023 ---> sudo systemctl status amazon-ssm-agent

macOS ---> Agent status on macOS. You can check the status by locating and evaluating the agent log file /var/log/amazon/ssm/amazon-ssm-agent.log.

Windows Server ---> Get-Service AmazonSSMAgent
