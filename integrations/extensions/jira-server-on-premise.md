# Jira Server (On-Premise)

Create issues in JIRA with the incidents from Squadcast and vice versa and also sync the status bidirectionally.

You can use this extension guide to install and configure the Squadcast extension in JIRA Server (On-Premise) in order to automatically create issues in JIRA projects from Squadcast and vice versa. The status of the issues on JIRA and incidents in Squadcast will automatically be in sync.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

**(1)** A valid Squadcast cloud subscription or a trial account (in either the Pro or Enterprise [plans](https://squadcast.com/pricing))

**(2)** You should have JIRA Server (On-Premise) version installed on your machine with a publicly accessible URL

**(3)** A user account in JIRA Server with `Administrator` privileges

**(4)** Base URL must be set in JIRA settings and it must be publicly accessible as mentioned above

**(5)** Only the Account Owner and Users with the `Manage Extensions` permission will be able to enable, disable and manage Extensions in Squadcast

**(6)** Install the Squadcast Plugin from the [Atlassian App Store](https://marketplace.atlassian.com/apps/1221739/squadcast-for-jira-server?hosting=server\&tab=overview)

### Configuring the Extension <a href="#configuring-the-extension" id="configuring-the-extension"></a>

**(1)** In Squadcast, navigate to **Settings** and select the **Extensions** tab from the left navigation sidebar. Move over to the JIRA Cloud extension and click on **Integrate**

**(2)** Now click on **Configure** to receive a **token**

**(3)** Copy the displayed **token**

**(4)** Go to **Manage Apps** page on your JIRA Server Account from the **Settings** drop-down

**(5)** Select the Squadcast Plugin from the **User-installed apps** and Click **Configure**

**(6)** In the configuration page, paste the Squadcast token in the **JIRA Integration Key** text box. Then click **Integrate**

**(7)** Move over to Squadcast and click on **Test Connection**. You will then receive a success message right below the text box. Post this, click on **Next**

**(8)** Select the Jira project in which issue needs to be created and select the issue type and click **Next**

**(9)** Then map the Jira issue status to the available Squadcast statuses and click **Next**

**(10)** Then select the mode in which you want to add an incident to Jira: **Manually** or **Automatically** Now, there are 2 sections:

* Add Services to Jira
* JQL - Service Mapping

**Add Services to Jira:** If an incident is created for any service selected in this section, a corresponding Jira ticket would be created in the configured _project_ having the configured _issueType_.

**JQL - Service Mapping:** If a ticket is created in Jira, then the mappings defined in this section would be iterated one-by-one and incident would be created for the service corresponding to the first JQL that evaluated to be true for that Jira ticket. If none of the JQL matched, then no incident would be created in Squadcast.

So, to summarize:

**Add Services to Jira:** Handles Jira ticket creation corresponding to incident creation in Squadcast.

**JQL - Service Mapping:** Handles Squadcast incident creation corresponding to ticket creation in Jira.

That’s it! Your JIRA Server Integration is good to go.

The statuses of the Squadcast Incident and JIRA Issue will be automatically synced as per the mapping configured.

### Usage of the Automatic and Manual Modes <a href="#usage-of-the-automatic-and-manual-modes" id="usage-of-the-automatic-and-manual-modes"></a>

#### Automatic mode <a href="#automatic-mode" id="automatic-mode"></a>

If you have chosen the Automatic mode while configuring Jira Server then you need not do anything. Any incident triggered for the selected service will automatically create an issue in the selected Jira project with the configured issue type.

#### Manual mode <a href="#manual-mode" id="manual-mode"></a>

If the chosen mode is Manual, follow the below steps to create a issue in Jira.

**(1)** Open the incident in Squadcast and click on **More Actions** button

**(2)** Select **Jira Server** action and click on **Create a issue in Jira** button

An issue will be created in the selected Jira project with the configured issue type and this action will be recorded in the incident timeline with a hyperlink to the created Jira issue.

Similarly, if there was an error in creating a ticket in Jira, it will be reflected in the Incident Timeline.

You can use Tagging Rules to map your issue priority and project by following the steps below :

**(1)** Create a tagging rule that helps you set the priority and configure Jira project for an incident in Squadcast by using the tags:

* `priority`- `Jira Priority`
* `issuetype` - `Issue Type Name`
* `project`- `Project Key`

Now the Jira ticket will be created based on the tag values

#### Example of configuring the Tags using Tagging Rules <a href="#example-of-configuring-the-tags-using-tagging-rules" id="example-of-configuring-the-tags-using-tagging-rules"></a>
