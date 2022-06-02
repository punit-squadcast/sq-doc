---
title: Conviva
tags: [set-up-your-profile, managing-all-users]
keywords: 
last\_updated: 
datatable: 
summary: "Send in your AI & Manual Alerts from Conviva into Squadcast"
sidebar: mydoc\_sidebar
permalink: docs/conviva
folder: mydoc
---

This document will help you integrate [Conviva](https://www.conviva.com/) with Squadcast.

Conviva is a streaming-video intelligence platform that provides metrics and analytics for better video optimization. 

Route detailed alerts from Conviva to the right users in Squadcast.

## How to integrate Conviva with Squadcast

### In Squadcast: Adding Conviva as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **Conviva** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/conviva\_1.png)

{{site.data.alerts.yellow-note-i}}
<b>Important</b><br/><br/>
<p>For an Alert Source to turn active (indicated by a <b>green dot - Receiving alerts</b> against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.</p>
<p>An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.</p>
{{site.data.alerts.end}}

### In Conviva: Create a Squadcast Webhook as a Notification Channel

**(1)** Log in to your Conviva web console, go to the **Settings** menu of your project and click on **Notification Channels**

![](../../.gitbook/assets/conviva\_2.png)

**(2)** Click on the **Alerts** tab to display the existing list of Webhooks

**(3)** Click on the **Add Webhook** button. If no webhooks are configured, a message prompt will appear

**(4)** Click on the **Add** button to go to the **Add Webhooks** page so you can configure webhooks

![](../../.gitbook/assets/conviva\_3.png)

**(5)** Enter a **Webhook Name**, an **Email** to notify users when an issue occurs with the Webhook notification, and the **Webhook URL** that was copied from the Squadcast Services page

![](../../.gitbook/assets/conviva\_4.png)

**(6)** Next set the **alert type(s)** to include in the webhook payload and the relevant information to be included in the payload for each alert type that is configured. 

In this screenshot, we have checked to include both **AI Alerts** and **Manual Alerts**.

![](../../.gitbook/assets/conviva\_5.png)

**(7)** Test the Webhook and then click on the **Add Webhook** button to save the Webhook configuration

Now when an event is triggered in Conviva, an incident will be created automatically in Squadcast.

{{site.data.alerts.red-note}}
<b>Auto-resolve</b>
<br/><br/><p>Today, Conviva does not support the auto-resolve functionality due to which, it is unavailable in Squadcast.</p>
{{site.data.alerts.end}}