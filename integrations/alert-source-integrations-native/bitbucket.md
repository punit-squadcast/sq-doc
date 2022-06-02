---
title: Bitbucket
keywords: 
last\_updated: 
summary: "Send events to Squadcast from Bitbucket"
sidebar: mydoc\_sidebar
permalink: docs/bitbucket
folder: mydoc
---

This document will help you integrate Bitbucket with Squadcast.

[Bitbucket](https://bitbucket.org/) is a Git-based source code repository hosting service.

Route detailed alerts from Bitbucket to the right users in Squadcast.

## How to integrate Bitbucket with Squadcast

### In Squadcast: Using Bitbucket as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **Bitbucket** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/bitbucket\_1.png)

{{site.data.alerts.yellow-note-i}}
<b>Important</b><br/><br/>
<p>For an Alert Source to turn active (indicated by a <b>green dot - Receiving alerts</b> against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.</p>
<p>An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.</p>
{{site.data.alerts.end}}

### In Bitbucket: Set up a Webhook for Squadcast

**(1)** Open the repository where you want to add the Webhook for Squadcast and click on **Repository settings**

![](../../.gitbook/assets/bitbucket\_2.png)

**(2)** From the links on the **Settings** page, click the **Webhooks** link

![](../../.gitbook/assets/bitbucket\_3.png)

**(3)** Select the **Add webhook** button to create a Webhook for the repository

![](../../.gitbook/assets/bitbucket\_4.png)

**(4)** In the **Add new webhook** page, enter a **Title**, paste the previously copied Webhook URL from Squadcast and select the below in the **Triggers** field:
- `Repository push`
- `Pull request created`
- `Pull request merged`

Click on **Save**

![](../../.gitbook/assets/bitbucket\_5.png)

{{site.data.alerts.yellow-note-i-md}}
**NOTE:** 

This integration supports the below events:
- `Repository push`
- `Pull request created`
- `Pull request merged`

{{site.data.alerts.end}}

**NOTE:** For the event type `Issue`, integrate with our [Jira-cloud](https://support.squadcast.com/docs/jira-cloud-alert-source) as an alert source integration since, Bitbucket uses Jira to create and manage issues. This way, everytime you create an issue in Bitbucket, an issue for it is created in Jira, for which an incident is triggered in Squadcast.

That is it, you are good to go! Everytime a Push or Pull Request event occurs in Bitbucket, an incident would be created in Squadcast. When a Pull Request is merged in Bitbucket, the corresponding incident in Squadcast will be **automatically resolved**.