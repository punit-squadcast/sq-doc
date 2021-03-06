---
title: AWS CloudTrail via CloudWatch
tags:
  - integration
  - aws cloudtrail via cloudwatch
keywords: null
last\_updated: null
summary: Get CloudTrail alerts into Squadcast using CloudWatch and SNS endpoints
sidebar: mydoc\_sidebar
permalink: docs/aws-cloudtrail-via-cloudwatch
folder: mydoc
description: Get CloudTrail alerts into Squadcast using CloudWatch and SNS endpoints
---

# AWS CloudTrail via CloudWatch

Please use this integration guide to configure CloudTrail alerts so they can be received in Squadcast. This integration should be used only for getting CloudTrail alerts via CloudWatch and a SNS endpoint.

For CloudTrail log alerts, use the [AWS CloudTrail Logs integration](aws-cloudtrail-logs/).

For regular AWS CloudWatch alarms (like EC2 alerts), use the [AWS CloudWatch Integration](amazon-cloudwatch-aws/).

### Using AWS CloudTrail via CloudWatch as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **AWS CloudTrail via CloudWatch** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/cloudwatch\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

### Create CloudTrail Alarm Endpoint in AWS SNS

Now log in to your AWS account and proceed to SNS.

Click on "**Create topic**" to get "Create new topic" dialog box. Fill in the details as per your requirements and then click on "**Create topic**"

![](../../.gitbook/assets/cloudwatch\_2.png)

Now inside the topic, click on "**Create subscription**" to get "Create subscription" dialog box. Select the protocol as "**HTTPS**" and in the endpoint enter the URL you obtained from previous step. Finally, click on "**Create subscription**" to create the subscription.

![](../../.gitbook/assets/cloudwatch\_3.png)

![](../../.gitbook/assets/cloudwatch\_4.png)

The "**Subscription ID**" for the subscription should immediately change to "**Confirmed**" from "**PendingConfirmation**". Click on the refresh button to verify the same.

![](../../.gitbook/assets/cloudwatch\_5.png)

Then you can [configure your CloudTrail alerts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudwatch-alarms-for-cloudtrail.html#cloudwatch-alarms-for-cloudtrail-security-group) and assign this topic as the notification option and you are good to go.
