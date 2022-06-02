---
title: ServiceNow
keywords: 
last_updated: 
summary: "Send ticket details to Squadcast from ServiceNow"
sidebar: mydoc_sidebar
permalink: docs/servicenow
folder: mydoc
---

This document will help you integrate ServiceNow with Squadcast.

[ServiceNow](https://www.ServiceNow.com/) transforms your business with digital IT workflows by modernizing your operations to optimize productivity, cost, and resilience with a single platform for IT.

Route detailed ticket alerts from ServiceNow to the right users in Squadcast.

## How to integrate ServiceNow with Squadcast

### In Squadcast: Using ServiceNow as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **ServiceNow** from the **Alert Source** drop-down menu and copy the Webhook

![](../../.gitbook/assets/servicenow\_1.png)

{{site.data.alerts.yellow-note-i}}
<b>Important</b><br/><br/>
<p>For an Alert Source to turn active (indicated by a <b>green dot - Receiving alerts</b> against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.</p>
<p>An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.</p>
{{site.data.alerts.end}}

### In ServiceNow: Create a Squadcast Webhook

**(1)** Download the [servicenow.js](https://github.com/SquadcastHub/squadcast-servicenow-integration/blob/master/servicenow.js) file

**(2)** Navigate to the filter box and search for **Business Rules**. Click on **System Definition > Business Rules**

![](../../.gitbook/assets/servicenow\_2.png)

**(3)** Click on **New**

![](../../.gitbook/assets/servicenow\_3.png)

**(4)** Provide any suitable **Name**, select **Incident** in the drop-down and check the **Advanced** option

![](../../.gitbook/assets/servicenow\_4.png)

**(5)** Navigate to **when to run** and fill the form as shown in the screenshot below

![](../../.gitbook/assets/servicenow\_5.png)

**(6)** Paste the previously downloaded and copied snippet into the **Script** text box

**(7)** Replace <**Squadcast Webhook URL**> with the previously copied Webhook URL and click on **Submit**

![](../../.gitbook/assets/servicenow\_6.png)

{{site.data.alerts.yellow-note-i-md}}
**Important:**

Understanding how the integration works:

- Trigger a new incident:

For `state: 1` in the ServiceNow ticket payload, an incident is triggered in Squadcast.

- Resolve an existing incident:

For `state: 6`, `state: 7` and `state: 8`, incidents are resolved in Squadcast (pertaining to auto-resolution of an existing, *open* incident)

Please ensure that the right `status` is being sent within the payload for the tickets into Squadcast. If values other than the ones mentioned above are sent for `status`, the integration will not work as expected.

In case of any queries, please feel free to reach out to our [Support team](mailto:support@squadcast.com).

{{site.data.alerts.end}}

That is it, you are now good to go! Whenever a ticket is created with the `New` status, an incident will be created in Squadcast for it. When the ticket is moved to `Resolved`, `Closed` or `Deleted` status in ServiceNow, the corresponding incident will automatically get resolved in Squadcast as well.