# MS Teams

Acknowledge, Resolve & Reassign incidents from MS Teams

We understand that most of your work happens over MS Teams. You can integrate Squadcast and MS Teams to collaborate efficiently with your team while working on incidents. Here’s a brief of all that is possible.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the Account Owner and Users with the `Manage Extensions` permission will be able to enable, disable and manage Extensions in Squadcast
* Only MS Teams Admins can add the Squadcast-MS Teams app in their workspace

### MS Teams Notifications for Incidents <a href="#ms-teams-notifications-for-incidents" id="ms-teams-notifications-for-incidents"></a>

Squadcast sends a notification to the configured MS Teams channel as soon as an incident is triggered. You can easily **Acknowledge**, **Resolve** and **Reassign** the populated incidents from within the MS Teams channel.

### Follow the steps below to integrate Squadcast and MS Teams <a href="#follow-the-steps-below-to-integrate-squadcast-and-ms-teams" id="follow-the-steps-below-to-integrate-squadcast-and-ms-teams"></a>

**(1)** Download the MS Teams app bundle by clicking on one of these links.

MS Teams app bundle for the US data center: download link

MS Teams app bundle for the EU data center: [download link](https://github.com/SquadcastHub/extensions/blob/main/bundles/Squadcast-EU-1.6.0.zip?raw=true)

**(2)** Navigate to the **Apps** section

**(3)** Click on **Upload a customised app**, and upload the previously downloaded app bundle by clicking on **Upload for my organization**

**(4)** Once successfully uploaded, you will see the Squadcast-MS Teams app in-built for your organization

**(5)** Click on the app card to open the app’s configuration modal and then, click on **Add** to add the app

**(6)** Once successfully added, you will recieve an authorize message. Click on **Authorize** button to initiate the authorization flow

**(7)** On doing so, you will be redirected to the **Extensions** page in Squadcast, indicating **successful integration of MS Teams and Squadcast**

### Adding MS Teams Channels <a href="#adding-ms-teams-channels" id="adding-ms-teams-channels"></a>

**(1)** By default, only the bot conversation will appear in the default channel

**(2)** To add more channels, navigate to the Squadcast app in MS Teams and click on the drop-down next to the **Open** button to open the configuration options. Click on **Add to a team**

**(3)** Select the **team** and a **channel** to add this app and click on **Set up a bot**

**(4)** Once successfully added, all of these will appear in Squadcast’s MS Teams Extension configuration

#### Updating the Global MS Teams Channel for all Services in Squadcast <a href="#updating-the-global-ms-teams-channel-for-all-services-in-squadcast" id="updating-the-global-ms-teams-channel-for-all-services-in-squadcast"></a>

**(1)** Click on the **DEFAULT MS TEAM NOTIFICATION CHANNEL** drop-down

**(2)** Select the new MS Teams channel that would be the default channel for all your Squadcast Services

**(3)** Click on **Save**

Now, you will start receiving alert notifications for _all_ Squadcast incidents in the configured MS Teams channel, in this case, the `internal-testing-Production-alerts` channel. You can then choose to **Acknowledge**, **Resolve** and **Reassign** these incidents from within the channel, in this case, the `internal-testing-Production-alerts` channel.

#### Configuring Service Specific MS Teams Channels <a href="#configuring-service-specific-ms-teams-channels" id="configuring-service-specific-ms-teams-channels"></a>

Additionally, you can associate one MS Teams channel per Squadcast Service so as to receive notifications for incidents affecting only that Service in this MS Teams channel.

Follow the steps below to configure the same:

**(1)** Enable the checkbox to activate `TEAM/SERVICE SPECIFIC CHANNEL`

**(2)** Select the Team to open the Team configuration option

**(3)** Select the Squadcast **Team** here

**(4)** All the Services that are a part of that Squadcast Team will appear in next Services drop-down, select the Service(s)

**(5)** Select a channel in opened Teams so for example in all the channels in `internal-testing` team is shown and we can select a channel to create a Squadcast(Team, service) to MS Teams Channel mapping

**(6)** Click on **Save** to save configuration

### Capabilities of MS Teams App <a href="#capabilities-of-ms-teams-app" id="capabilities-of-ms-teams-app"></a>

* You can `Acknowledge`,`Resolve` and `Reassign` incidents from within MS Teams itself by clicking on the corresponding CTAs. In addition to this, you can also add notes to the incidents which will directly reflect in the Incident Details page for the incident.
* Once the app is added as a bot in a specific MS Teams channel, you can run the bot command `whos-on-call` to view the on-call schedules for all the Teams created in your Squadcast organization.

### Additional Information on Errors <a href="#additional-information-on-errors" id="additional-information-on-errors"></a>

Errors encountered when taking actions on incident:

This error is either because you are not part a of the organization for which this incident is triggerd in Squadcast, or you are not authorised to take this action.

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** What happens when I link multiple organizations with the same [tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant)?

If you link multiple organizations with the same [tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant), then the previous organization-tenant mapping will get deactivated.

**(2)** What does unlinking an account lead to?

Unlinking an account deactivates all the organizations for a given [tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant).
