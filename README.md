# :package: Cloudwatch-alarm-to-slack-python
Send AWS Cloudwatch Alarm to Slack using AWS Lambda.

Note: If you want solution in node runtime. You may check this solution: https://github.com/widdix/cloudwatch-alarm-to-slack

# Configurations

## → Lambda Configs
Clone the repository, go to repository folder and use following commands to create lambda package:
```
pip install requests -t ./
chmod -R 755 .
zip -r ../myDeploymentPackage.zip .
```
Note: We have do this because we're using 3rd party package "requests" which doesn't come with python lambda runtime. So we have to include it in our package.

## → AWS Configs
1. Create SNS Topic.
2. Setup AWS Cloudwatch Alarm on your required matrics and set SNS topic as the SNS Topic created in previous step.
3. Create Lambda function.
4. Upload Lambda deployment package to lambda function.
5. Setup Lambda environment variable "SLACK_WEBHOOK_URL" and set it to your incoming slack webhook url.
6. Create subscriber on SNS topic as lambda function and select the lambda created in previous step.

## → Slack Configs
1. Create slack channel.
2. Go to slack workspace settings and setup incoming webhook.
3. Select the channel created in first step for incoming webhook.
4. And boom, you should start receiving your alarm notifications on slack channel.

# License
Licensed Under GPL 2.0.
