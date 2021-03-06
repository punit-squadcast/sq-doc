---
title: StatHat
keywords: null
last_updated: null
summary: Send alerts to Squadcast from Stathat
sidebar: mydoc_sidebar
permalink: docs/stathat
folder: mydoc
description: Send alerts to Squadcast from Stathat
---

# StatHat

This document will help you integrate StatHat with Squadcast.

[StatHat](https://www.stathat.com/) makes detailed time series charts of all your stats. Compare multiple stats from the past hour to the past 10 years to know where your stats are headed. It will analyze all your data and create forecasts for you with estimates for the next 30 days. Route detailed monitoring alerts from StatHat to the right users in Squadcast.

### How to integrate StatHat with Squadcast

#### In Squadcast: Using StatHat as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **StatHat** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/stathat\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

#### In StatHat: Create a Squadcast Webhook

**(1)** In the app, navigate to **Settings**

![](../../.gitbook/assets/stathat\_2.png)

**(2)** Click on **Manage Alert Destinations** to add the Webhook

![](../../.gitbook/assets/stathat\_4.png)

**(3)** Under **Webhooks**, give it a meaningful _Name_ and paste the copied Webhook _URL_ from Squadcast and click on **Add**

![](../../.gitbook/assets/stathat\_3.png)

**(4)** Now, navigate back to **Settings**. You can enable _Squadcast Webhook_ to be triggered for _Automatic Alerts_ and _Manual Alerts_ on a global level.

![](../../.gitbook/assets/stathat\_5.png)

Or, you can specify within each of your **Alerts** to trigger _Squadcast Webhook_ in case of an anomaly.

![](../../.gitbook/assets/stathat\_6.png)

That is it, you are now good to go! Whenever an alert is triggered in StatHat, an incident will be created automatically in Squadcast.

### FAQ

**Q:** If an alert gets resolved in StatHat, does StatHat send auto-resolve signals to Squadcast?

**A:** No, StatHat does not send auto-resolve signals to Squadcast. Hence, Squadcast incidents from StatHat should be resolved manually.
