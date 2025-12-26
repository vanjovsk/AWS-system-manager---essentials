# AWS-system-manager---essentials
set up

<h1> Use SSM Agent (from AWS Systems Manager) to update, manage, and configure instances(EC2), vitual machines and on-premises servers.</h1>

First, find if the SSM Agent is already installed in the Operation System when you launch an EC2 instance created from an AMI.

<p><b> This is how I verify the SSM Agent status :</b></p>

1- lounch the ec2 instance

2- Connect the Instance. You can use SSH to connect to Linux instances or use Remote Desktop to connect to Windows Server instances.

3- Check the status of SSM Agent by running the command for your instance's OS type

list of commands:

<p><b> Operating system	Command </b></p>

Amazon Linux  ---> sudo status amazon-ssm-agent

Amazon Linux 2 and Amazon Linux 2023 ---> sudo systemctl status amazon-ssm-agent

macOS ---> Agent status on macOS. You can check the status by locating and evaluating the agent log file /var/log/amazon/ssm/amazon-ssm-agent.log.

Windows Server ---> Get-Service AmazonSSMAgent

<h2><b> Troubleshooting SSM Agent: </b></h2>

Your network needs a clear path to reach the service. You have two choices:

Open Internet: Use your standard internet connection (via an Internet Gateway or NAT Gateway).

Private Path: If you want to stay off the public internet, you must set up a VPC Endpoint (a private bridge).

Check network connectivity!!

SSM Agent must allow HTTPS (port 443) outbound traffic to the following endpoints:

ssm. region .amazonaws.com

ssmmessages. region .amazonaws.com

ec2messages. region .amazonaws.com


1 -confirm the networking and access configuration is correct
