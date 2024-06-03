# Monitoring Infrastructure

## Lab Overview

The ability to monitor applications and infrastructure is critical for delivering reliable, consistent IT services. Monitoring requirements range from collecting statistics for long-term analysis to quickly reacting to changes and outages. Monitoring can also support compliance reporting by continuously checking that infrastructure meets organizational standards.

This lab demonstrates how to use Amazon CloudWatch Metrics, Amazon CloudWatch Logs, and AWS Config to monitor your applications and infrastructure.

## Objectives

By the end of this lab, I was able to:

- Use the AWS Systems Manager Run Command to install the CloudWatch agent on Amazon EC2 instances.
- Monitor application logs using CloudWatch agent and CloudWatch Logs.
- Monitor system metrics using CloudWatch agent and CloudWatch Metrics.
- Track infrastructure compliance using AWS Config.

## Tasks Completed

### Task 1: Installing the CloudWatch Agent

I used the AWS Systems Manager Run Command to install the CloudWatch agent on an EC2 instance. The CloudWatch agent was configured to collect both application and system metrics.

![install-agent](https://github.com/Mohamed-kittany/Canvas-Lab-186-MonitoringInfrastructure/assets/161580792/7c783b6f-0fb7-40b6-95ad-2cb3363a44df)

#### Steps:

1. Navigated to the Systems Manager in the AWS Management Console.
2. Used the Run Command to deploy a pre-written command that installs the CloudWatch agent.
3. Configured the command parameters to install the latest version of the CloudWatch agent on the web server instance.
4. Verified the successful installation of the agent.

### Task 2: Monitoring Application Logs Using CloudWatch Logs

I configured the CloudWatch agent to collect web server logs and general system metrics, and then monitored these logs using CloudWatch Logs.

![cloudwatch-logs](https://github.com/Mohamed-kittany/Canvas-Lab-186-MonitoringInfrastructure/assets/161580792/fcb574e0-d52e-46bc-b814-df2813643321)

#### Steps:

1. Configured the CloudWatch agent to collect web server access and error logs.
2. Stored the configuration file in AWS Systems Manager Parameter Store.
3. Used the Run Command to start the CloudWatch agent with the configuration stored in the Parameter Store.
4. Generated log data by accessing the web server and attempting to access a page that does not exist.
5. Monitored the logs in CloudWatch Logs and created a metric filter to identify 404 Errors.
6. Set up an alarm to send notifications when too many 404 Not Found errors are received.

### Task 3: Monitoring Instance Metrics Using CloudWatch

I used CloudWatch Metrics to monitor system performance and captured metrics about CPU, disk, and network usage on the EC2 instance.

![cloudwatch-metrics](https://github.com/Mohamed-kittany/Canvas-Lab-186-MonitoringInfrastructure/assets/161580792/7ac74b8a-2fb2-4e67-aaf6-54692160f469)

#### Steps:

1. Examined the metrics presented in the Monitoring tab of the EC2 instance.
2. Used the CloudWatch Metrics console to explore various metrics captured by the CloudWatch agent.
3. Selected metrics that are critical to system performance and set up dashboards to visualize these metrics.

## Conclusion

This lab provided hands-on experience in setting up and using Amazon CloudWatch for monitoring infrastructure and applications. By installing the CloudWatch agent, configuring log collection, setting up metric filters and alarms, and exploring system metrics, I demonstrated the ability to effectively monitor and manage AWS infrastructure.
