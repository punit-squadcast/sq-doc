---
title: Rollbar
tags:
  - set-up-your-profile
  - managing-all-users
keywords: null
last_updated: null
datatable: null
summary: Get alerts from Rollbar into Squadcast
sidebar: mydoc_sidebar
permalink: docs/rollbar
folder: mydoc
description: Get alerts from Rollbar into Squadcast
---

# Rollbar

Follow the steps below to configure a service so as to push related alert data from [Rollbar](https://docs.rollbar.com/docs/getting-started) onto Squadcast.

Squadcast will then process this information to create incidents for this service as per your preferences.

### Using Rollbar as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **Rollbar** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/rollbar\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

### Create a Squadcast Webhook in Rollbar

**(1)** Navigate to the project you want to configure, then click Settings → Notifications → Webhook

**(2)** Paste the webhook URL you copied from Squadcast. Click `Save Settings`.

![](../../.gitbook/assets/rollbar\_2.png)

**(3)** Under **Add Rule** select the rules you want to configure for creating incidents in Squadcast.

You can select `New Item`,`Item Reopened`,`Item Reactivated` and `10^nth Occurence` for creating incidents in Squadcast and select `Item Resolved` for auto resolving incidents in Squadcast.

![](../../.gitbook/assets/rollbar\_3.png)

Your Rollbar Alert Source integration is good to go. Whenever an alert is triggered in Rollbar, an incident will be triggered in Squadcast as well.

Squadcast will **Auto-Resolve** the incident, if the alerts get resolved in Rollbar and doesn't require any manual intervention from the user.
