# Slack

Trigger, Acknowledge, Resolve & Reassign incidents from Slack

We understand that most of your work happens over Slack. You can integrate Squadcast and Slack to collaborate efficiently with your team while working on incidents. Here’s a brief of all that is possible.

You can review Squadcast’s Privacy Policy [here](https://www.squadcast.com/privacy).

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the Account Owner and Users with the `Manage Extensions` permission will be able to enable, disable and manage Extensions in Squadcast

### Slack Notifications for Incidents <a href="#slack-notifications-for-incidents" id="slack-notifications-for-incidents"></a>

Squadcast sends a notification to the configured Slack Channel as soon as an incident is triggered. You can easily **Acknowledge**, **Resolve** and **Reassign** the populated incidents from within the Slack Channel itself.

#### Follow the steps below to integrate Squadcast and Slack <a href="#follow-the-steps-below-to-integrate-squadcast-and-slack" id="follow-the-steps-below-to-integrate-squadcast-and-slack"></a>

**(1)** navigate to **Settings** and select the **Extensions** tab from the left navigation sidebar

**(2)** Click on the **Integrate** button on the Slack tile

**(3)** Now, click on **Continue**

**(4)** You will be redirected to Slack for approval of certain permissions that Squadcast would need for this integration. First select the Slack Workspace that you wish to integrate with your Squadcast account and then, click on **Allow**

**(5)** Next, you will be asked to select a Slack Channel that would be the default Slack Channel for all your Squadcast Services

**(6)** You can either select an existing Channel from the dropdown or create a new Channel in Slack. If you have added a new Channel and don’t see the same in the dropdown, refresh the dropdown and it would appear. Once you have selected the Channel, click on **Save**

This completes the integration process between Squadcast and Slack. You can verify the same with the presence of the **Integrated** banner on the Slack tile as well as the selected Channel mentioned on the Slack tile

### Creating Slack Channel for Incidents <a href="#creating-slack-channel-for-incidents" id="creating-slack-channel-for-incidents"></a>

To create a Slack Channel for an Incident,

**(1)** Navigate to the Incident Details page, and click on the **+** icon or **+ Add Link** button

**(2)** Click on the **Create Slack Channel** option from the menu

**(3)** Type in the **Channel Name** for your Incident and click **Save**

This will generate a dedicated Slack Channel for your Incident.

### Updating the global Slack Channel for all Services in Squadcast <a href="#updating-the-global-slack-channel-for-all-services-in-squadcast" id="updating-the-global-slack-channel-for-all-services-in-squadcast"></a>

**(1)** Click on **Select Channel**

**(2)** Select the new Slack Channel that would be the default Slack Channel for all your Squadcast Services

**(3)** Click on **Save**

Now, you will start receiving alert notifications for _all_ Squadcast incidents in the configured Slack Channel, in this case, the `incidents-internal` Channel. You can then choose to **Acknowledge**, **Resolve** and **Reassign** these incidents from within the Channel, in this case, the `incidents-internal` Channel.

### Configuring Service Specific Slack Channels <a href="#configuring-service-specific-slack-channels" id="configuring-service-specific-slack-channels"></a>

Additionally, you can associate one Slack Channel per Service so as to receive notifications for incidents affecting only that Service in this Slack Channel.

Follow the steps below to configure the same:

**(1)** From the sidebar, navigate to **Services**

**(2)** Click on the three horizontal dots for the Service of your choice

**(3)** Select **Slack Channel**

**(4)** By default, the configured global Slack Channel is populated. Now, select a Channel from the drop-down to which incident notifications should be sent for this Service and click on **save**

**(5)** **Save** the configuration

You will be able to see the associated Slack Channel on the bottom-right corner of the Service tile.

### Triggering Incidents from Slack <a href="#triggering-incidents-from-slack" id="triggering-incidents-from-slack"></a>

You can trigger incidents in Squadcast directly from a Slack Channel.

**(1)** To trigger an incident from Slack, within the Slack Channel, type `/create_incident` and select the first option as seen in the screenshot

**(2)** In the pop-up:

(a) Pick the Service for which you want to trigger the incident

(b) Give the incident a meaningful title

(c) Provide informative description if needed

Click on **Create** to trigger the incident

**(3)** You will now be able to see the newly triggered incident in Squadcast. You will also be notified in the globally configured or the Service specific Slack Channel for the same

### Using Slack as an Alert Source <a href="#using-slack-as-an-alert-source" id="using-slack-as-an-alert-source"></a>

To create incidents automatically in Squadcast from Slack, check out [Slack as an alert source](<../.gitbook/assets/slack as an alert source>).

### FAQs <a href="#faqs" id="faqs"></a>

1.  **How can a user in Slack be given access to add Public Channels?**

    Please follow the [documentation by Slack](https://slack.com/intl/en-nl/help/articles/360017938993-What-is-a-Channel) to give access to your user to create Public Channels.
2. **Our Squadcast Organization is integrated with our Slack account. However, we see `error messages` such as the ones below. What do they mean?**

*   **You have not linked your Slack account with your Squadcast account.**

    This error message simply means that you are not added as a user of your Squadcast Organization. One needs to be added as a user in their Squadcast Organization to be able to take actions on incidents from Slack. **Additionally, your Slack user Email and Squadcast user Email must be the exact same**.
*   **You are not a part of this Organization on Squadcast. Please contact your Admin.**

    This error message simply means that you are a user of Squadcast for an Organization that is **not the same** as the one that the incident in Slack is for. One needs to be added as a user of all those Squadcast Organizations in order to take actions on incidents of those particular Organizations. Please contact an Admin of your Team and have them add you as a user of the right Squadcast Organization.
*   **You are a part of this Organization as a Stakeholder. You cannot take actions on incidents. Please contact your Admin to upgrade your role.**

    Stakeholders in Squadcast have read-only access to the platform. As a `Stakeholder`, one will not be able to take any actions on the incidents. To be able to take actions on incidents, you must be added as a `User` or an `Admin`. Please contact an Admin of your Team and have your User Type changed from Stakeholder to `User` or with the right User Permissions.
