---
title: Freshdesk
keywords: 
last_updated: 
summary: "Send ticket details to Squadcast from Freshdesk"
sidebar: mydoc_sidebar
permalink: docs/freshdesk
folder: mydoc
---

This document will help you integrate Freshdesk with Squadcast.

[Freshdesk](https://freshdesk.com/) solves your unique challenges, from ticketing and phone to messaging apps and social media, with Freshdesk's modern omnichannel support.

Route detailed ticket alerts from Freshdesk to the right users in Squadcast.

## How to integrate Freshdesk with Squadcast

### In Squadcast: Using Freshdesk as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **Freshdesk** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/freshdesk\_1.png)

{{site.data.alerts.yellow-note-i}}
<b>Important</b><br/><br/>
<p>For an Alert Source to turn active (indicated by a <b>green dot - Receiving alerts</b> against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.</p>
<p>An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.</p>
{{site.data.alerts.end}}

### In Freshdesk: Create a Squadcast webhook alert

**(1)** In the app, go to **Admin > Workflows > Automations** to create the webhook

![](../../.gitbook/assets/freshdesk\_2.png)

**(2)** Click on **New Rule**

![](../../.gitbook/assets/freshdesk\_3.png)

**(3)** Fill in the form as shown in the subsequent screenshots (you can put your own checks):

![](../../.gitbook/assets/freshdesk\_4.png)

**(4)** Fill **Perform these actions** form as shown below:

- Select **Trigger webhook**
- **Request Type**: `POST`
- **URL**: Paste the previously copied Squadcast webhook here
- **Encoding** `JSON`
- **Content**: `Simple`

![](../../.gitbook/assets/freshdesk\_5.png)

**All the following variables have to be added** in order to send this information associated with the ticket to create the incident in Squadcast:
- `Subject`
- `Description`
- `Ticket ID`
- `Ticket URL`
- `Product Specific Ticket URL`
- `Tags`
- `Status`
- `Priority`
- `Source`
- `Group Name`
- `Contact Name`
- `Contact Phone`
- `Contact Email`
- `Agent Name`
- `Agent Email`
- `Due by Time`

![](../../.gitbook/assets/freshdesk\_6.png)

**(4)** Do the following for sending **resolve alert** to Squadcast:

**(a)** Navigate to **Ticket Updates** tab and click on **New Rule**

![](../../.gitbook/assets/freshdesk\_7.png)

**(b)** Fill the below form according to your requirements. 

For example:

![](../../.gitbook/assets/freshdesk\_8.png)

**(c)** Fill **Perform these actions** form as shown below: 

![](../../.gitbook/assets/freshdesk\_9.png)

Find more details on Rule creation [here](https://support.freshdesk.com/support/solutions/articles/132589)

**(5)** Next, to create the alert, follow the steps below: 

**(a)** Click on **New > New Ticket** or,

![](../../.gitbook/assets/freshdesk\_10.png)

**(b)** Fill the form below and click on **Create**

- status **Open -> to trigger incident at Squadcast**
- status **Resolved -> to resolve incident at Squadcast**
- status **Closed -> to resolve incident at Squadcast**

![](../../.gitbook/assets/freshdesk\_11.png)

That is it, you are now good to go! Whenever a ticket is `created` or `updated`, an incident will be created in Squadcast. When the ticket is either `resolved` or `closed` in Freshdesk, the corresponding incident will automatically get resolved in Squadcast as well.

{{site.data.alerts.yellow-note-i-md}}
**Note:**

Please ensure you are not sending the **<** character or any **HTML Tag** within the ticket description that would come in the **Description** ticket variable. This will cause the content of the description to break and the entire information will not be displayed.
{{site.data.alerts.end}}