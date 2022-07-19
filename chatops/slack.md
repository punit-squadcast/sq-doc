---
description: Trigger, Acknowledge, Resolve & Reassign incidents from Slack
---

# Slack

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=xeYbgoGSHKo" %}

We understand that most of your work happens over Slack. You can integrate Squadcast and Slack to collaborate efficiently with your team while working on incidents. Here’s a brief of all that is possible.

You can review Squadcast’s Privacy Policy [here](https://www.squadcast.com/privacy).

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the Account Owner and Users with the <mark style="color:red;">`Manage Extensions`</mark> permission will be able to enable, disable and manage Extensions in Squadcast

### Slack Notifications for Incidents <a href="#slack-notifications-for-incidents" id="slack-notifications-for-incidents"></a>

Squadcast sends a notification to the configured Slack Channel as soon as an incident is triggered. You can easily **Acknowledge**, **Resolve** and **Reassign** the populated incidents from within the Slack Channel itself.

{% hint style="info" %}
**Note**

The **email address** used with your **user in Slack** and your **user in Squadcast** should be the same, if not, the integration will not work as expected.
{% endhint %}

#### Follow the steps below to integrate Squadcast and Slack <a href="#follow-the-steps-below-to-integrate-squadcast-and-slack" id="follow-the-steps-below-to-integrate-squadcast-and-slack"></a>

**(1)** Navigate to **Settings** and select the **Extensions** tab from the left navigation sidebar

![](../.gitbook/assets/slack\_squadcast\_1.png)

**(2)** Click on the **Integrate** button on the Slack tile

![](../.gitbook/assets/slack\_squadcast\_2.png)

**(3)** Now, click on **Continue**

![](../.gitbook/assets/slack\_integration\_modal\_select\_workspace.png)

**(4)** You will be redirected to Slack for approval of certain permissions that Squadcast would need for this integration. First select the Slack Workspace that you wish to integrate with your Squadcast account and then, click on **Allow**

![](../.gitbook/assets/slack\_squadcast\_3.png)

**(5)** Next, you will be asked to select a Slack Channel that would be the default Slack Channel for all your Squadcast Services

![](../.gitbook/assets/slack\_integration\_modal\_select\_channel.png)

**(6)** You can either select an existing Channel from the dropdown or create a new Channel in Slack. If you have added a new Channel and don’t see the same in the dropdown, refresh the dropdown and it would appear. Once you have selected the Channel, click on **Save**

![](../.gitbook/assets/slack\_integration\_modal\_select\_channel\_dropdown.png)

{% hint style="info" %}
**List of Slack Channels displayed in the dropdown**

By default, all the Public Slack Channels and the Private Slack Channels in which the Squadcast Bot is added to your Slack Workspace would be listed in the dropdown. If you do not see the Channel of your choice listed in the dropdown, then:

1. Head over to your Slack Workspace
2. Open the Channel that should have been present in the integration dropdown
3. In this Channel, call the Squadcast Bot by using **@squadcast**
4. Back in Squadcast, click on the Refresh button beside the Channel dropdown to refresh the list. Your Channel should be populated in the list now
{% endhint %}

This completes the integration process between Squadcast and Slack. You can verify the same with the presence of the **Integrated** banner on the Slack tile as well as the selected Channel mentioned on the Slack tile

![](../.gitbook/assets/slack\_integration\_integrated\_card.png)

{% hint style="info" %}
**Revoke Slack integration from Squadcast**

You can simply click on **Revoke** to remove the configured Slack integration at any given time
{% endhint %}

### Creating Slack Channel for Incidents <a href="#creating-slack-channel-for-incidents" id="creating-slack-channel-for-incidents"></a>

To create a Slack Channel for an Incident,

**(1)** Navigate to the Incident Details page, and click on the **+** icon or **+ Add Link** button

![](../.gitbook/assets/slackchannel\_1.png)

**(2)** Click on the **Create Slack Channel** option from the menu

![](<../.gitbook/assets/slackchannel\_2 (1).png>)

**(3)** Type in the **Channel Name** for your Incident and click **Save**

![](../.gitbook/assets/slackchannel\_3.png)

This will generate a dedicated Slack Channel for your Incident.

{% hint style="info" %}
**Note**\
All notifications of this specific incident like Acknowledged, Re-assigned, and Resolved will be sent to this channel in addition to the regular channel (if configured).
{% endhint %}

{% hint style="info" %}
**Note**\
Once the Incident is resolved, you can archive the Slack Channel using the **Archive** button on the right.

![](../.gitbook/assets/slackchannel\_4.png)
{% endhint %}

### Updating the global Slack Channel for all Services in Squadcast <a href="#updating-the-global-slack-channel-for-all-services-in-squadcast" id="updating-the-global-slack-channel-for-all-services-in-squadcast"></a>

**(1)** Click on **Select Channel**

![](../.gitbook/assets/slack\_integration\_select\_channel\_button.png)

**(2)** Select the new Slack Channel that would be the default Slack Channel for all your Squadcast Services

![](<../.gitbook/assets/slack\_integration\_modal\_select\_channel\_dropdown (1).png>)

**(3)** Click on **Save**

![](../.gitbook/assets/slack\_integration\_modal\_save\_channel.png)

Now, you will start receiving alert notifications for _all_ Squadcast incidents in the configured Slack channel, in this case, the <mark style="color:red;">`incidents-internal`</mark> Channel. You can then choose to **Acknowledge**, **Resolve** and **Reassign** these incidents from within the Channel, in this case, the <mark style="color:red;">`incidents-internal`</mark> Channel.

{% hint style="info" %}
**This integration supports bi-directional status sync**

When an incident is _acknowledged_, _resolved_ or _reassigned_ from Slack, the status change of the incident is propagated to Squadcast and updated automatically. Similarly, if an incident is _acknowledged_, _resolved_ or _reassigned_ in Squadcast, you will be notified in the configured Slack Channel for it.

**Note**: If an incident is auto-resolved by the alert-source, then the notification indicates the same.

![](../.gitbook/assets/slack\_auto\_resolve\_notification.png)
{% endhint %}

{% hint style="info" %}
**Note: Global Slack Channel = default Slack Channel for all Services**

By default, the configured global Slack Channel is applicable to every Service in Squadcast. This means, that all the alerts coming for every Service in Squadcast will be routed to the default Slack Channel configured
{% endhint %}

### Configuring **Service-Specific** Slack Channels <a href="#configuring-service-specific-slack-channels" id="configuring-service-specific-slack-channels"></a>

Additionally, you can associate one Slack Channel per Service so as to receive notifications for incidents affecting only that Service in this Slack Channel.

Follow the steps below to configure the same:

**(1)** From the sidebar, navigate to **Services**

![](../.gitbook/assets/slack\_squadcast\_8.png)

**(2)** Click on the three horizontal dots for the Service of your choice

![](../.gitbook/assets/slack\_squadcast\_9.png)

**(3)** Select **Slack Channel**

![](../.gitbook/assets/slack\_squadcast\_10.png)

**(4)** By default, the configured global Slack Channel is populated. Now, select a Channel from the drop-down to which incident notifications should be sent for this Service and click on **save**

![](../.gitbook/assets/slack\_squadcast\_11.png)

{% hint style="info" %}
**List of Channel shown**

By default**,** all the Public Channels and only the Private Channels in which Squadcast bot is already called in your Slack workspace would be listed in Squadcast. If you do not see your Channel in the list, then:

1. Move to your Slack Workspace
2. Open the Channel that you wish to map in Squadcast
3. Call Squadcast by using **@squadcast**
4. Now, map the Channel in Squadcast under the Service of your choice
{% endhint %}

**(5)** **Save** the configuration



You will be able to see the associated Slack Channel in the bottom-right corner of the Service tile.

![](../.gitbook/assets/slack\_squadcast\_13.png)

### Triggering Incidents from Slack <a href="#triggering-incidents-from-slack" id="triggering-incidents-from-slack"></a>

You can trigger incidents in Squadcast directly from a Slack Channel.

**(1)** To trigger an incident from Slack, within the Slack Channel, type <mark style="color:red;">`/create_incident`</mark> and select the first option as seen in the screenshot

![](../.gitbook/assets/slack\_squadcast\_14.png)

**(2)** In the pop-up:

(a) Pick the Service for which you want to trigger the incident

(b) Give the incident a meaningful title

(c) Provide informative description if needed

Click on **Create** to trigger the incident

![](../.gitbook/assets/slack\_squadcast\_15.png)

**(3)** You will now be able to see the newly triggered incident in Squadcast. You will also be notified in the globally configured or the Service specific Slack Channel for the same

![](../.gitbook/assets/slack\_create\_incident\_success.png)

{% hint style="danger" %}
**Adding private Slack Channels for Service-specific Slack Channels**

First, within the private Slack Channel, add the Squadcast bot. You can do so by executing the command - `@squadcast`. Once this is done, in Squadcast, you can map that particular Channel to the Service of your choice.
{% endhint %}

{% hint style="info" %}
**Note: Global Slack Channel = default Slack Channel for all Services**

You will be able to view tags (if present) associated with an incident in the incident notification that you receive within the Slack Channel
{% endhint %}

![](../.gitbook/assets/slack\_incident\_action\_buttons.png)

### Using Slack as an Alert Source <a href="#using-slack-as-an-alert-source" id="using-slack-as-an-alert-source"></a>

To create incidents automatically in Squadcast from Slack, check out [Slack](../integrations/alert-source-integrations-native/slack\_alert\_source\_integration.md) as an alert source.

### FAQs <a href="#faqs" id="faqs"></a>

1.  **How can a user in Slack be given access to add Public Channels?**

    Please follow the [documentation by Slack](https://slack.com/intl/en-nl/help/articles/360017938993-What-is-a-Channel) to give access to your user to create Public Channels.
2. **Our Squadcast Organization is integrated with our Slack account. However, we see **<mark style="color:red;">**`error messages`**</mark>** such as the ones below. What do they mean?**

*   **You have not linked your Slack account with your Squadcast account.**

    This error message simply means that you are not added as a user of your Squadcast Organization. One needs to be added as a user in their Squadcast Organization to be able to take actions on incidents from Slack. **Additionally, your Slack user Email and Squadcast user Email must be the exact same**.
*   **You are not a part of this Organization on Squadcast. Please contact your Admin.**

    This error message simply means that you are a user of Squadcast for an Organization that is **not the same** as the one that the incident in Slack is for. One needs to be added as a user of all those Squadcast Organizations in order to take action on incidents of those particular Organizations. Please contact an Admin of your Team and have them add you as a user of the right Squadcast Organization.
*   **You are a part of this Organization as a Stakeholder. You cannot take action on incidents. Please contact your Admin to upgrade your role.**

    Stakeholders in Squadcast have read-only access to the platform. As a <mark style="color:red;">`Stakeholder`</mark>, one will not be able to take any actions on the incidents. To be able to take action on incidents, you must be added as a <mark style="color:red;">`User`</mark> or an <mark style="color:red;">`Admin`</mark>. Please contact an Admin of your Team and have your User Type changed from Stakeholder to <mark style="color:red;">`User`</mark> or with the right User Permissions.
