---
title: SolarWinds Orion
summary: Send alerts to Squadcast from SolarWinds Orion
tags:
  - integration
  - solarwinds orion
keywords: null
sidebar: mydoc_sidebar
permalink: docs/solarwinds-orion
folder: mydoc
description: Send alerts to Squadcast from SolarWinds Orion
---

# SolarWinds Orion

[SolarWinds Orion](https://www.solarwinds.com/) is a powerful, scalable infrastructure monitoring and management platform designed to simplify IT administration for on-premises, hybrid, and software as a service (SaaS) environments in a single pane of glass.

{% hint style="info" %}
**Note:**

All of the SolarWinds offerings in the suite integrate with **SolarWinds Orion** to generate alerts. Users can use this document to set up SolarWinds Orion and route alerts from Orion, and other the offerings in the suite through Orion, to Squadcast.
{% endhint %}

Route detailed alerts from Solarwinds Orion to the right users in Squadcast.

### Using SolarWinds Orion as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **SolarWinds Orion** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/solarwinds\_orion\_1.png)

{% hint style="warning" %}
**Important**

For an Alert Source to turn active (indicated by a **green dot - Receiving alerts** against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.

An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.
{% endhint %}

### Create a Squadcast Webhook Alert in SolarWinds Orion

**(1)** Login to your SolarWinds Orion dashboard. Head over to the **ALERTS & ACTIVITY** tab. Then select **Alerts**

![](../../.gitbook/assets/solarwinds\_orion\_2.png)

**(2)** Click on **Manage Alerts**, then under the **ALERT MANAGER** section, click on **ADD NEW ALERT**

![](../../.gitbook/assets/solarwinds\_orion\_3.png)

![](../../.gitbook/assets/solarwinds\_orion\_4.png)

**(3)** Under Alert Properties, set the **Name of alert definition** and the **Description of alert definition**. Toggle the **Enabled (On/Off)** switch to **ON** and click on **NEXT**

![](../../.gitbook/assets/solarwinds\_orion\_5.png)

**(4)** Set the **Trigger Conditions** and **Reset Conditions** and click on **NEXT**

![](../../.gitbook/assets/solarwinds\_orion\_6.png)

![](../../.gitbook/assets/solarwinds\_orion\_7.png)

**(5)** Under **Trigger Actions**, click on **Add Action**. Then select **Send a GET or POST Request to a Web Server** and click on **CONFIGURE ACTION**

![](../../.gitbook/assets/solarwinds\_orion\_8.png)

![](../../.gitbook/assets/solarwinds\_orion\_9.png)

**(6)** Set the **name of action**. Paste the previously copied Squadcast Webhook URL in the placeholder for **URL**. Select **Use HTTP/S POST** and paste the variables mentioned below in the **Body to POST** box. Set **ContentType** as **application/x-www-form-urlencoded** and **None** under **Authentication**. Click on **ADD ACTION**, then on **NEXT**

![](../../.gitbook/assets/solarwinds\_orion\_10.png)

```
EventID=${N=Alerting;M=AlertObjectID}-${N=Alerting;M=AlertID}&AcknowledgeLink=${N=Alerting;M=AcknowledgeLink}&AcknowledgeUrl=${N=Alerting;M=AcknowledgeUrl}&Acknowledged=${N=Alerting;M=Acknowledged}&AcknowledgedBy=${N=Alerting;M=AcknowledgedBy}&AcknowledgedTime=${N=Alerting;M=AcknowledgedTime;F=DateTime}&AlertActiveID=${N=Alerting;M=AlertActiveID}&AlertDefID=${N=Alerting;M=AlertDefID}&AlertDescription=${N=Alerting;M=AlertDescription}&AlertDetailsUrl=${N=Alerting;M=AlertDetailsUrl}&AlertID=${N=Alerting;M=AlertID}&TimeOfDay=${N=Alerting;M=TimeOfDay}&Severity=${N=Alerting;M=Severity}&ObjectType=${N=Alerting;M=ObjectType}&Notes=${N=Alerting;M=Notes}&LongAlertTriggerTime=${N=Alerting;M=LongAlertTriggerTime;F=DateTime}&LastEdit=${N=Alerting;M=LastEdit;F=DateTime}&DownTime=${N=Alerting;M=DownTime}&AlertTriggerTime=${N=Alerting;M=AlertTriggerTime;F=DateTime}&AlertTriggerCount=${N=Alerting;M=AlertTriggerCount}&AlertObjectID=${N=Alerting;M=AlertObjectID}&AlertName=${N=Alerting;M=AlertName}&AlertMessage=${N=Alerting;M=AlertMessage}&Status=Triggered
```

\{{site.data.alerts.blue-note-md\}} **Note: Custom User Defined Variables**

Users can define two custom variables under Trigger Actions. The two variables can be added in the format mentioned below :

**\&CustomVariable1Name=\[Name]\&CustomVariable1Value=\[Value]\&CustomVariable2Name=\[Name]\&CustomVariable2Value=\[Value]**

Replace the **\[Name]** & **\[Value]** with proper values and add at the end of the variables mentioned in **Step 6**. This is how it would look like :

```
EventID=${N=Alerting;M=AlertObjectID}-${N=Alerting;M=AlertID}&AcknowledgeLink=${N=Alerting;M=AcknowledgeLink}&AcknowledgeUrl=${N=Alerting;M=AcknowledgeUrl}&Acknowledged=${N=Alerting;M=Acknowledged}&AcknowledgedBy=${N=Alerting;M=AcknowledgedBy}&AcknowledgedTime=${N=Alerting;M=AcknowledgedTime;F=DateTime}&AlertActiveID=${N=Alerting;M=AlertActiveID}&AlertDefID=${N=Alerting;M=AlertDefID}&AlertDescription=${N=Alerting;M=AlertDescription}&AlertDetailsUrl=${N=Alerting;M=AlertDetailsUrl}&AlertID=${N=Alerting;M=AlertID}&TimeOfDay=${N=Alerting;M=TimeOfDay}&Severity=${N=Alerting;M=Severity}&ObjectType=${N=Alerting;M=ObjectType}&Notes=${N=Alerting;M=Notes}&LongAlertTriggerTime=${N=Alerting;M=LongAlertTriggerTime;F=DateTime}&LastEdit=${N=Alerting;M=LastEdit;F=DateTime}&DownTime=${N=Alerting;M=DownTime}&AlertTriggerTime=${N=Alerting;M=AlertTriggerTime;F=DateTime}&AlertTriggerCount=${N=Alerting;M=AlertTriggerCount}&AlertObjectID=${N=Alerting;M=AlertObjectID}&AlertName=${N=Alerting;M=AlertName}&AlertMessage=${N=Alerting;M=AlertMessage}&Status=Triggered&CustomVariable1Name=[Name]&CustomVariable1Value=[Value]&CustomVariable2Name=[Name]&CustomVariable2Value=[Value]
```

\{{site.data.alerts.blue-note-md\}} **Note: Custom User Defined Incident Message**

Users can define custom Incident Message under Trigger Actions. The variable can be added in the format mentioned below :

**\&CustomIncidentMessage=\[IncidentMessage]**

Replace the **\[IncidentMessage]** with proper values and add at the end of the variables mentioned in **Step 6**. This is how it would look like :

```
EventID=${N=Alerting;M=AlertObjectID}-${N=Alerting;M=AlertID}&AcknowledgeLink=${N=Alerting;M=AcknowledgeLink}&AcknowledgeUrl=${N=Alerting;M=AcknowledgeUrl}&Acknowledged=${N=Alerting;M=Acknowledged}&AcknowledgedBy=${N=Alerting;M=AcknowledgedBy}&AcknowledgedTime=${N=Alerting;M=AcknowledgedTime;F=DateTime}&AlertActiveID=${N=Alerting;M=AlertActiveID}&AlertDefID=${N=Alerting;M=AlertDefID}&AlertDescription=${N=Alerting;M=AlertDescription}&AlertDetailsUrl=${N=Alerting;M=AlertDetailsUrl}&AlertID=${N=Alerting;M=AlertID}&TimeOfDay=${N=Alerting;M=TimeOfDay}&Severity=${N=Alerting;M=Severity}&ObjectType=${N=Alerting;M=ObjectType}&Notes=${N=Alerting;M=Notes}&LongAlertTriggerTime=${N=Alerting;M=LongAlertTriggerTime;F=DateTime}&LastEdit=${N=Alerting;M=LastEdit;F=DateTime}&DownTime=${N=Alerting;M=DownTime}&AlertTriggerTime=${N=Alerting;M=AlertTriggerTime;F=DateTime}&AlertTriggerCount=${N=Alerting;M=AlertTriggerCount}&AlertObjectID=${N=Alerting;M=AlertObjectID}&AlertName=${N=Alerting;M=AlertName}&AlertMessage=${N=Alerting;M=AlertMessage}&Status=Triggered&CustomVariable1Name=[Name]&CustomVariable1Value=[Value]&CustomVariable2Name=[Name]&CustomVariable2Value=[Value]&CustomIncidentMessage=[IncidentMessage]
```

**(7)** Under **RESET ACTIONS**, click on **Add Action**. Then select **Send a GET or POST Request to a Web Server** and click on **CONFIGURE ACTION**

![](../../.gitbook/assets/solarwinds\_orion\_11.png)

![](../../.gitbook/assets/solarwinds\_orion\_12.png)

**(8)** Set the **name of action**. Paste the previously copied Squadcast Webhook URL in the placeholder for **URL**. Select **Use HTTP/S POST** and paste the variables mentioned below in the **Body to POST** box. Set **ContentType** as **application/x-www-form-urlencoded** and **None** under **Authentication**. Click on **ADD ACTION**, then on **NEXT**

![](../../.gitbook/assets/solarwinds\_orion\_13.png)

```
EventID=${N=Alerting;M=AlertObjectID}-${N=Alerting;M=AlertID}&AcknowledgeLink=${N=Alerting;M=AcknowledgeLink}&AcknowledgeUrl=${N=Alerting;M=AcknowledgeUrl}&Acknowledged=${N=Alerting;M=Acknowledged}&AcknowledgedBy=${N=Alerting;M=AcknowledgedBy}&AcknowledgedTime=${N=Alerting;M=AcknowledgedTime;F=DateTime}&AlertActiveID=${N=Alerting;M=AlertActiveID}&AlertDefID=${N=Alerting;M=AlertDefID}&AlertDescription=${N=Alerting;M=AlertDescription}&AlertDetailsUrl=${N=Alerting;M=AlertDetailsUrl}&AlertID=${N=Alerting;M=AlertID}&TimeOfDay=${N=Alerting;M=TimeOfDay}&Severity=${N=Alerting;M=Severity}&ObjectType=${N=Alerting;M=ObjectType}&Notes=${N=Alerting;M=Notes}&LongAlertTriggerTime=${N=Alerting;M=LongAlertTriggerTime;F=DateTime}&LastEdit=${N=Alerting;M=LastEdit;F=DateTime}&DownTime=${N=Alerting;M=DownTime}&AlertTriggerTime=${N=Alerting;M=AlertTriggerTime;F=DateTime}&AlertTriggerCount=${N=Alerting;M=AlertTriggerCount}&AlertObjectID=${N=Alerting;M=AlertObjectID}&AlertName=${N=Alerting;M=AlertName}&AlertMessage=${N=Alerting;M=AlertMessage}&Status=Resolved
```

**(9)** Finalize the Alert Details on the **SUMMARY** page and click on **SUBMIT**

![](../../.gitbook/assets/solarwinds\_orion\_14.png)

That's it, you are good to go! Your SolarWinds Orion integration is now complete. Whenever SolarWinds Orion fires an alert through **Trigger Actions**, an incident will be created in Squadcast for it. Also, when an alert has been **RESET** in SolarWinds Orion, the corresponding incident gets **auto-resolved** in Squadcast.

.btttn:hover{box-shadow: 0 10px 20px 0 rgba(15,97,221,.25); transform: translate(0,-2px);}Ready to try Squadcast?[Start Now For Free!](https://app.squadcast.com/register) [Schedule a Demo](https://calendly.com/renuka-squadcast/30min)
