# AWS-Shell-Scripting-Project
**Shell script to automate the process of listing all the active resources in an AWS account.**
---
### Description:
<br>
This shell script takes two user inputs, `region` and `service_name`, and outputs a list of active resources belonging to the specified AWS service in the specified region. It uses the AWS CLI to fetch and filter resources, and displays their IDs, names, and types.
<br>
*Usage: ./aws_resource_list.sh  <aws_region> <aws_service>*
<br>
*Example: ./aws_resource_list.sh us-east-1 ec2*
---
### Steps to run:
1. Install the AWS CLI
2. Configure the AWS CLI
3. Run the script
---
### Additionally you can add cronjob like:
Automated cron job runs daily to list active AWS resources and sends alerts to Slack channel, enabling real-time visibility. This helps in cost optimization by identifying unused or underutilized services early.
<br>
*Example server in IST (cronjob @6:00PM):*
<br>
```In crontab:
0 18 * * * /path/to/aws_resource_list.sh <region> <service> | /path/to/send_to_slack.sh
