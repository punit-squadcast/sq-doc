---
description: Acknowledge, Resolve & Reassign incidents from MS Teams
---

# MS Teams

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=V7N4Vq61z5A" %}

We understand that most of your work happens over MS Teams. You can integrate Squadcast and MS Teams to collaborate efficiently with your team while working on incidents. Here’s a brief of all that is possible.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the Account Owner and Users with the <mark style="color:red;">`Manage Extensions`</mark> permission will be able to enable, disable and manage Extensions in Squadcast
* Only MS Teams Admins can add the Squadcast-MS Teams app in their workspace

### MS Teams Notifications for Incidents <a href="#ms-teams-notifications-for-incidents" id="ms-teams-notifications-for-incidents"></a>

Squadcast sends a notification to the configured MS Teams channel as soon as an incident is triggered. You can easily **Acknowledge**, **Resolve** and **Reassign** the populated incidents from within the MS Teams channel.

{% hint style="info" %}
**Note:**

The `email address` used with your _user in MS Teams_ and your _user in Squadcast_ should be the same, if not, the integration will not work as expected.
{% endhint %}

### Follow the steps below to integrate Squadcast and MS Teams <a href="#follow-the-steps-below-to-integrate-squadcast-and-ms-teams" id="follow-the-steps-below-to-integrate-squadcast-and-ms-teams"></a>

**(1)** Download the MS Teams app bundle by clicking on one of these links.

MS Teams app bundle for the US data center: download link

MS Teams app bundle for the EU data center: [download link](https://github.com/SquadcastHub/extensions/blob/main/bundles/Squadcast-EU-1.6.0.zip?raw=true)

**(2)** Navigate to the **Apps** section

![](../.gitbook/assets/teams\_app.png)

**(3)** Click on **Upload a customised app**, and upload the previously downloaded app bundle by clicking on **Upload for my organization**

![](../.gitbook/assets/msteams\_custom\_app.png)

**(4)** Once successfully uploaded, you will see the Squadcast-MS Teams app in-built for your organization

**(5)** Click on the app card to open the app’s configuration modal and then, click on **Add** to add the app

![](../.gitbook/assets/msteams\_app\_modal.png)

**(6)** Once successfully added, you will recieve an authorize message. Click on **Authorize** button to initiate the authorization flow

![](../.gitbook/assets/msteams\_authorise\_message.png)

**(7)** On doing so, you will be redirected to the **Extensions** page in Squadcast, indicating **successful integration of MS Teams and Squadcast**

![](../.gitbook/assets/msteam\_successfull\_integration.png)

### Adding MS Teams Channels <a href="#adding-ms-teams-channels" id="adding-ms-teams-channels"></a>

**(1)** By default, only the bot conversation will appear in the default channel

**(2)** To add more channels, navigate to the Squadcast app in MS Teams and click on the drop-down next to the **Open** button to open the configuration options. Click on **Add to a team**

![](../.gitbook/assets/msteams\_app\_add\_to\_team.png)

**(3)** Select the **team** and a **channel** to add this app and click on **Set up a bot**

![](../.gitbook/assets/msteams\_select\_channel.png)

![](../.gitbook/assets/msteams\_setup\_bot.png)

**(4)** Once successfully added, all of these will appear in Squadcast’s MS Teams Extension configuration

![](../.gitbook/assets/msteams\_team\_channel.png)

{% hint style="info" %}
**List of channels appearing in the default channel**

Once the Squadcast app is added to a team in MS Teams, all the channels for that team will appear in the **DEFAULT MS TEAM NOTIFICATION CHANNEL**. To add more teams to Squadcast, refer step 2 & onwards.
{% endhint %}

#### Updating the Global MS Teams Channel for all Services in Squadcast <a href="#updating-the-global-ms-teams-channel-for-all-services-in-squadcast" id="updating-the-global-ms-teams-channel-for-all-services-in-squadcast"></a>

**(1)** Click on the **DEFAULT MS TEAM NOTIFICATION CHANNEL** drop-down

**(2)** Select the new MS Teams channel that would be the default channel for all your Squadcast Services

![](<../.gitbook/assets/msteams\_team\_channel (1).png>)

**(3)** Click on **Save**

![](../.gitbook/assets/msteams\_team\_save.png)

Now, you will start receiving alert notifications for _all_ Squadcast incidents in the configured MS Teams channel, in this case, the <mark style="color:red;">`internal-testing-Production-alerts`</mark> channel. You can then choose to **Acknowledge**, **Resolve** and **Reassign** these incidents from within the channel, in this case, the <mark style="color:red;">`internal-testing-Production-alerts`</mark> channel.

{% hint style="info" %}
**This integration supports bi-directional status sync**

When an incident is acknowledged, resolved or reassigned from MS Teams, the status change of the incident is propagated to Squadcast and updated automatically. Similarly, if an incident is acknowledged, resolved or reassigned in Squadcast, you will be notified in the configured MS Teams channel for it.
{% endhint %}

{% hint style="info" %}
**Note**: If an incident is auto-resolved by the alert source (monitoring tool), then the notification will indicate the same.
{% endhint %}

{% hint style="info" %}
&#x20;**Note:**

Global MS Teams channel = default MS Teams channel for all Services

By default, the configured global MS Teams channel is applicable to every Service in Squadcast. This means, all the alerts coming for every Service in Squadcast will be routed to the default MS Teams channel configured.
{% endhint %}

#### Configuring **Service-Specific** MS Teams Channels <a href="#configuring-service-specific-ms-teams-channels" id="configuring-service-specific-ms-teams-channels"></a>

Additionally, you can associate one MS Teams channel per Squadcast Service so as to receive notifications for incidents affecting only that Service in this MS Teams channel.

Follow the steps below to configure the same:

**(1)** Enable the checkbox to activate <mark style="color:red;">`TEAM/SERVICE SPECIFIC CHANNEL`</mark>

![](../.gitbook/assets/msteams\_teams\_service\_specific.png)

**(2)** Select the Team to open the Team configuration option

![](../.gitbook/assets/msteam\_team\_config.png)

**(3)** Select the Squadcast **Team** here

![](../.gitbook/assets/msteams\_select\_sq\_team.png)

**(4)** All the Services that are a part of that Squadcast Team will appear in the next Services drop-down, select the Service(s)

**(5)** Select a channel in opened Teams so for example all the channels in the <mark style="color:red;">`internal-testing`</mark> team are shown and we can select a channel to create a Squadcast(Team, service) to MS Teams Channel mapping

![](../.gitbook/assets/msteams\_select\_team\_channels.png)

**(6)** Click on **Save** to save the configuration

### Capabilities of MS Teams App <a href="#capabilities-of-ms-teams-app" id="capabilities-of-ms-teams-app"></a>

* You can <mark style="color:red;">`Acknowledge`</mark>, <mark style="color:red;">`Resolve`</mark> and <mark style="color:red;">`Reassign`</mark> incidents from within MS Teams itself by clicking on the corresponding CTAs. In addition to this, you can also add notes to the incidents which will be directly reflected in the Incident Details page for the incident.

![](../.gitbook/assets/msteams\_message.png)

* Once the app is added as a bot in a specific MS Teams channel, you can run the bot command <mark style="color:red;">`whos-on-call`</mark> to view the on-call schedules for all the Teams created in your Squadcast organization.

![](../.gitbook/assets/msteams\_sq\_command.png)

### Additional Information on Errors <a href="#additional-information-on-errors" id="additional-information-on-errors"></a>

Errors encountered when taking action on the incident:



This error is either because you are not part of the organization for which this incident is triggered in Squadcast, or you are not authorised to take this action.

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** What happens when I link multiple organizations with the same [tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant)?

If you link multiple organizations with the same [tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant), then the previous organization-tenant mapping will get deactivated.

**(2)** What does unlinking an account lead to?

Unlinking an account deactivates all the organizations for a given [tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant).
