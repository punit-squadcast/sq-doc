---
title: AWS RDS
keywords: null
last_updated: null
summary: Send alerts from Amazon RDS to Squadcast
sidebar: mydoc_sidebar
permalink: docs/amazon-rds
folder: mydoc
description: Send alerts from Amazon RDS to Squadcast
---

# Amazon RDS

This document will help you integrate Amazon RDS with Squadcast.

[Amazon RDS](https://aws.amazon.com/rds/) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks, such as hardware provisioning, database setup, patching, and backups.

Route detailed alerts from Amazon RDS to the right users in Squadcast.

### How to integrate Amazon RDS with Squadcast

#### In Squadcast: Using AWS CloudWatch Event Rules as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **AWS Cloudwatch Event Rules** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/event\_rules\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

#### In AWS: Configure SNS Endpoint

**(1)** Log in to your AWS account and proceed to **SNS**

**(2)** Click on **Create topic**

**(3)** Within the dialog box, fill in the details as per your requirements and then click on **Create topic**

![](../../.gitbook/assets/event\_rules\_2.png)

**(4)** Inside the topic, click on **Create subscription**

![](../../.gitbook/assets/event\_rules\_3.png)

**(5)** Select the protocol as **HTTPS** and in the endpoint enter the URL you obtained from previous step

**(6)** Finally, click on **Create subscription** to create the subscription

![](../../.gitbook/assets/event\_rules\_4.png)

{% hint style="warning" %}
**Important:**

The **Subscription ID** for the subscription should immediately change to **Confirmed** from **PendingConfirmation**. Click on the refresh button to verify the same.
{% endhint %}

#### In AWS: Configure Amazon RDS

**(1)** Headover to your RDS dashboard and navigate to **Event Subscriptions**

![](../../.gitbook/assets/rds\_1.png)

**(2)** Click on **Create event subscription**

![](../../.gitbook/assets/rds\_2.png)

**(3)** Enter a suitable **Name**

![](../../.gitbook/assets/rds\_3.png)

**(4)** Next, select **Target** as **Amazon Resource Name (ARN)** and select the previously created ARN from the drop-down

![](../../.gitbook/assets/rds\_4.png)

**(5)** Select the appropriate **Source type** from the drop-down and click on **Create**

![](../../.gitbook/assets/rds\_5.png)

That's it, you are good to go! Your Amazon RDS integration is complete. Now, whenever an event is triggered by Amazon RDS, an incident will be created in Squadcast for it.
