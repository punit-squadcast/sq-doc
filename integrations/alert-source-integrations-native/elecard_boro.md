---
title: Elecard Boro
summary: Send alerts to Squadcast from Elecard Boro
tags:
  - integration
  - elecard boro
keywords: null
sidebar: mydoc_sidebar
permalink: docs/elecard-boro
folder: mydoc
description: Send alerts to Squadcast from Elecard Boro
---

# Elecard Boro

[Elecard Boro](https://www.elecard.com/products/quality-control/boro-service) is an IPTV monitoring software solution for UDP, RTP, HTTP, HLS and DASH streams quality control and measurement of QoS and QoE parameters in all segments of distributed networks.

Route detailed alerts from Elecard Boro to the right users in Squadcast.

### Using Elecard Boro as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **Elecard Boro** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/elecard\_boro\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

### Create a Squadcast Webhook Notification in Elecard Boro

**(1)** Login to your Elecard Boro dashboard. Head over to the **MY PROJECTS** tab. Then, select the project of your choice

![](../../.gitbook/assets/elecard\_boro\_2.png)

**(2)** Click on **Project Settings**. Under the **Notifications** section, click on **WEBHOOK**

![](../../.gitbook/assets/elecard\_boro\_3.png)

**(3)** Under **WEBHOOK**, click on **Create profile**. Set the preferred **Language** and the **Timezone**. Enable the **Send error notifications via Webhook** and paste the previously copied Squadcast Webhook URL in the placeholder for **URL**

![](../../.gitbook/assets/elecard\_boro\_4.png)

**(4)** Scroll down, set up your event triggers. Then click on **Save**

![](../../.gitbook/assets/elecard\_boro\_5.png)

That's it, you are good to go! Your Elecard Boro integration is now complete. Whenever Elecard Boro fires an alert, an incident will be created in Squadcast for it. Also, when an alert has been **Cleared** in Elecard Boro, the corresponding incident gets **auto-resolved** in Squadcast.

.btttn:hover{box-shadow: 0 10px 20px 0 rgba(15,97,221,.25); transform: translate(0,-2px);}Ready to try Squadcast?[Start Now For Free!](https://app.squadcast.com/register) [Schedule a Demo](https://calendly.com/renuka-squadcast/30min)
