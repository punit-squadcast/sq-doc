---
title: Domotz
summary: Send alerts to Squadcast from Domotz
tags:
  - integration
  - domotz
keywords: null
sidebar: mydoc\_sidebar
permalink: docs/domotz
folder: mydoc
description: Send alerts to Squadcast from Domotz
---

# Domotz

[Domotz](https://www.domotz.com/) is a network monitoring software to easily monitor remote networks and devices with powerful and affordable software, providing actionable insights & easy-to-use interface.

Route detailed alerts from Domotz to the right users in Squadcast.

### Using Domotz as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **Domotz** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/domotz\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

### Create a Squadcast Webhook Shared Alert in Domotz

**(1)** Login to your Domotz dashboard. Head over to the **Alerts Settings** tab and click on **Shared Alerts & Ticketing Systems**

![](../../.gitbook/assets/domotz\_2.png)

**(2)** Scroll to the bottom of the **Contact Channels** list, and click on **Add webhook** under **Webhooks**

![](../../.gitbook/assets/domotz\_3.png)

**(3)** Here, fill in the **Description**. Paste the previously copied Squadcast Webhook URL in the placeholder for **Webhook address**. Then, click on **Add**

![](../../.gitbook/assets/domotz\_4.png)

**(4)** Scroll to the top of the **Alerts Settings** page and click on **Create a Shared Alert**

![](../../.gitbook/assets/domotz\_5.png)

**(5)** Enable the toggle and specify the name of the Shared Alert under **Alert Name**. Select the events for the Shared Alert under the **Events Lists**. Then, click on **Select Contact Channels**. Select the Squadcast webhook and click on **Add**.

Finally, click on **Create**.

![](../../.gitbook/assets/domotz\_6.png)

![](../../.gitbook/assets/domotz\_7.png)

**(6)** Navigate to Device/Network Details and click on **Alerts**. Then, click on **Add Shared Alerts** and select your newly created Shared Alert under **Available Shared Alerts**.

![](../../.gitbook/assets/domotz\_8.png)

![](../../.gitbook/assets/domotz\_9.png)

![](../../.gitbook/assets/domotz\_10.png)

That's it, you are good to go! Your Domotz integration is now complete. Whenever Domotz fires an alert, an incident will be created in Squadcast for it. Also, when an alert is resolved in Domotz, the corresponding incident gets **auto-resolved** in Squadcast.

The integration will also create incidents for heartbeat monitoring alerts.

.btttn:hover{box-shadow: 0 10px 20px 0 rgba(15,97,221,.25); transform: translate(0,-2px);}Ready to try Squadcast?[Start Now For Free!](https://app.squadcast.com/register) [Schedule a Demo](https://calendly.com/renuka-squadcast/30min)
