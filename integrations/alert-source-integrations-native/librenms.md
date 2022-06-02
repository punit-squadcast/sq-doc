---
title: LibreNMS
#tags: [New-Relic, OverOps]
keywords: 
last_updated: 
summary: "Send alerts to Squadcast from LibreNMS"
sidebar: mydoc_sidebar
permalink: docs/librenms
folder: mydoc
---

This document will help you integrate LibreNMS with Squadcast.

[LibreNMS](https://librenms.org/) is an auto-discovering PHP/MySQL-based network monitoring system.

Route detailed monitoring alerts from LibreNMS to the right users in Squadcast.

## How to integrate LibreNMS with Squadcast

### In Squadcast: Using LibreNMS as an Alert Source

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

![](../../.gitbook/assets/alert\_source\_1.png)

**(2)** Search for **LibreNMS** from the Alert Source drop-down and copy the Webhook URL

![](../../.gitbook/assets/librenms\_1.png)

{{site.data.alerts.yellow-note-i}}
<b>Important</b><br/><br/>
<p>For an Alert Source to turn active (indicated by a <b>green dot - Receiving alerts</b> against the name of the Alert Source in the drop-down), you can either generate a test alert or wait for a real-time alert to be generated by the Alert Source.</p>
<p>An Alert Source is active if there is a recorded incident via that Alert Source for the Service in the last 30 days.</p>
{{site.data.alerts.end}}

### In LibreNMS: Add a Squadcast Webhook

**(1)** From the home page, click on the **Alerts** tab on the top

![](../../.gitbook/assets/librenms\_2.png)

**(2)** Select **Alert Transports**

![](../../.gitbook/assets/librenms\_3.png)

**(3)** Click on **Create alert transport**

![](../../.gitbook/assets/librenms\_4.png)

**(4)** Next:

- Give the Alert Transport a **Name**
- Choose **Transport type** as `Api`
- **Default alert** is toggled to `ON`
- Choose **API Method** as `POST`
- In the placeholder for **API URL**, paste the copied Webhook from Squadcast
- In **Options**, add the template below **as is**:

{% raw %}
```json
device_id={{ $device_id }}
hostname= {{ $hostname }}
sysName={{ $sysName }}
sysDescr={{ $sysDescr }}
sysContact={{ $sysContact }}
os={{ $os }}
type={{ $type }}
ip={{ $ip }}
hardware={{ $hardware }}
version={{ $version }}
features={{ $features }}
serial={{ $serial }}
location={{ $location }}
uptime={{ $uptime }}
uptime_short={{ $uptime_short }}
uptime_long={{ $uptime_long }}
description={{ $description }}
notes={{ $notes }}
alert_notes={{ $alert_notes }}
ping_timestamp={{ $ping_timestamp }}
ping_loss={{ $ping_loss }}
ping_min={{ $ping_min }}
ping_max={{ $ping_max }}
ping_avg={{ $ping_avg }}
title={{ $title }}
elapsed={{ $elapsed }}
builder={{ $builder }}
id={{ $id }}
uid={{ $uid }}
state={{ $state }}
severity={{ $severity }}
rule={{ $rule }}
name={{ $name }} 
proc={{ $proc }} 
timestamp={{ $timestamp }} 
transport={{ $transport }} 
transport_name={{ $transport_name }}
```
{% endraw %}

- Click on **Save Transport**

![](../../.gitbook/assets/librenms\_5.png)

**(5)** Once your Alert Transport has been created, click on the **Alerts** tab on the top and select **Alert Rules**

![](../../.gitbook/assets/librenms\_6.png)

**(6)** You can either **Add alert rule** or modify an existing one. Choose the **Alert Rule** for which Squadcast Webhook should be triggered.

Here, in **Transports**:
- Select the **Squadcast Webhook** that was previously created 
- Enable the toggle for **Recovery Alerts** to `ON`
- Click on **Save Rule**

![](../../.gitbook/assets/librenms\_7.png)

**(7)** Back in the **Alert Rule** dashboard, you can verify the rules for which **Squadcast Webhook** is added as a **Transport**

![](../../.gitbook/assets/librenms\_8.png)

That is it, your integration with LibreNMS is complete and you are good to go!

Now, every time there is an alert in LibreNMS, the alert will be sent to Squadcast and an incident will be triggered, notifying the right people. Similarly, when the alert gets resolved in LibreNMS, the corresponding incident will get **auto-resolved** in Squadcast as well.