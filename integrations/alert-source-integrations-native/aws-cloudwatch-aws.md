# AWS Cloudwatch (AWS)

Send events to Squadcast from AWS Cloudwatch (Amazon Web Services)

Follow the steps below to configure a service so as to push related alert data from AWS Cloudwatch onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

### Using Amazon CloudWatch as an Alert Source <a href="#using-amazon-cloudwatch-as-an-alert-source" id="using-amazon-cloudwatch-as-an-alert-source"></a>

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

**(2)** Search for **Amazon CloudWatch** from the Alert Source drop-down and copy the Webhook URL

### Create a Squadcast Webhook in Amazon CloudWatch <a href="#create-a-squadcast-webhook-in-amazon-cloudwatch" id="create-a-squadcast-webhook-in-amazon-cloudwatch"></a>

Now log in to your AWS account and proceed to SNS.

Click on “**Create topic**” to configure the display name and related details. Fill in the details as per your requirements and then click on “Create topic”.

Now inside the topic, click on “**Create subscription**” to get “Create subscription” page. Select the protocol as “HTTPS” and in the endpoint enter the URL that was copied from Squadcast. Finally, click on “Create subscription” to create the subscription.

The “**Subscription ID**” for the subscription should immediately change from “PendingConfirmation” to “Confirmed”. Click on the refresh button to verify the same.

Now you can go to any of your AWS services for which you want to set the Alarm. We’ll take the example of “EC2” in this case.

Right-click on your EC2 instance and go to “**CloudWatch Monitoring**”. Click on “**Add/Edit Alarms**”.

Click on “**Create Alarm**” and in the following dialog box for “Send a notification to” drop down, select the topic you created earlier. Configure the alarm as per your requirements and finally click on “**Create Alarm**”. Now you will start receiving incidents on Squadcast whenever this Alarm moves to “**ALARM” state**.

Under “**Actions**”, add a notification selecting “**Whenever this alarm: State is OK**” and “Send notification to:” as the topic you created earlier. Finally click on “**Save Changes**”.

Your Amazon CloudWatch Integration is now good to go!

Whenever an Alarm moves to OK state inside CloudWatch the corresponding incident will **automatically be resolved** in Squadcast.
