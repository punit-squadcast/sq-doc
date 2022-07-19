---
description: View triggered incidents on Google Hangouts
---

# Google Hangouts

You can use this guide to integrate with [Hangouts Chat](http://chat.google.com/).

{% hint style="warning" %}
**Important:**

EU Customers can use the Google Hangouts Bot for EU under the name **squadcast\_eu**
{% endhint %}

#### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the Account Owner and Users with the <mark style="color:red;">`Manage Extensions`</mark> permission will be able to enable, disable and manage Extensions in Squadcast

#### Enabling Google Hangouts Extension <a href="#enabling-google-hangouts-extension" id="enabling-google-hangouts-extension"></a>

**(1)** Navigate to **Settings** and select the **Extensions** tab from the left navigation sidebar

**(2)** Move over to the Google Hangouts extension and click on **Integrate**

![](../.gitbook/assets/hangouts\_1.png)

**(3)** Copy the **Integration Key** shown

![](../.gitbook/assets/hangouts\_2.png)

#### Configuration in Google Hangouts <a href="#configuration-in-google-hangouts" id="configuration-in-google-hangouts"></a>

**(1)** Move over to your Hangouts Chat account and select the room in which you want to install the bot

**(2)** Type **Squadcast**, add the **Squadcast BOT** from the options

![](../.gitbook/assets/hangouts\_3.png)

**(3)** In order to integrate this chat room with your Squadcast Organization, send the **Squadcast BOT** a message in the following format

<mark style="color:red;">`@Squadcast connect <your integration key>`</mark>

Add the copied integration key in the <mark style="color:red;">`<your integration key>`</mark> space.

![](../.gitbook/assets/hangouts\_4.png)

That’s it! Your Google Hangouts extension integration is now good to go.

![](../.gitbook/assets/hangouts\_5.png)

Here’s how the Incident Details are shown in Google Hangouts.

You can click on <mark style="color:red;">`View On Squadcast`</mark> to take you straight to the [Incident Details](../incidents-page/incidents-details.md) page of that incident.

![](../.gitbook/assets/hangouts\_6.png)
