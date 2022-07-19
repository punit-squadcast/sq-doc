---
description: >-
  Create tickets in Jira with the incidents from Squadcast and sync status
  bidirectionally
---

# Jira Cloud

{% embed url="https://squadcast.wistia.com/medias/ldkmvj4z9e" %}

You can use this integration guide to install and configure the Squadcast extension in Jira Cloud to _create issues in Jira projects_ when there is an incident in Squadcast either _Automatically_ or _Manually_ and _sync the status bidirectionally_.

### Pre-requisites <a href="#pre-requisites" id="pre-requisites"></a>

* A valid Squadcast cloud subscription or a trial account (in either the Pro or Enterprise [plans](https://squadcast.com/pricing))
* A user account in Jira Cloud version with <mark style="color:red;">`Administrator`</mark> privileges
* Only the Account Owner and Users with the <mark style="color:red;">`Manage Extensions`</mark> permission will be able to enable, disable and manage Extensions in Squadcast

### Configuring the Extension <a href="#configuring-the-extension" id="configuring-the-extension"></a>

#### In Jira Cloud: Installing Squadcast App <a href="#in-jira-cloud-installing-squadcast-app" id="in-jira-cloud-installing-squadcast-app"></a>

**(1)** Login to your Jira Cloud account and install the Squadcast Jira Cloud plugin corresponding to your data centre.

Plugin for the US data center - [Squadcast Jira Cloud plugin](https://marketplace.atlassian.com/apps/1221041/squadcast-for-jira-cloud?hosting=cloud\&tab=overview)

Plugin for the EU data center - [Squadcast for Jira Cloud (EU only version)](https://marketplace.atlassian.com/apps/1227594/squadcast-for-jira-cloud-eu-only-version?tab=overview\&hosting=cloud)

![](../../.gitbook/assets/jira\_cloud\_squadcast\_1.png)

**(2)** Click on **Configure** once the app has been installed

![](../../.gitbook/assets/jira\_cloud\_squadcast\_12.png)

**(3)** Copy the <mark style="color:red;">`Jira Client Token`</mark> that is available in _Step 2_ of the _Configuration page_

![](../../.gitbook/assets/jira\_cloud\_squadcast\_13.png)

#### In Squadcast: Configuring Jira Cloud Extension <a href="#in-squadcast-configuring-jira-cloud-extension" id="in-squadcast-configuring-jira-cloud-extension"></a>

This would be the global configuration for the Jira Cloud extension. After configuring the same, you can map a particular Jira Cloud project to one or more Squadcast Services by following the steps [here](jira-cloud.md).

**(1)** In Squadcast, navigate to **Settings** and select the **Extensions** tab from the left navigation sidebar

**(2)** Move over to the Jira Cloud extension and click on **Integrate**

![](../../.gitbook/assets/jira\_cloud\_squadcast\_2.png)

**(3)** Paste the previously copied <mark style="color:red;">`Jira Client Token`</mark> <mark style="color:red;"></mark><mark style="color:red;"></mark> and click on **Save & Next**

![](../../.gitbook/assets/jira\_cloud\_squadcast\_3.png)

**(4)** Select the <mark style="color:red;">`Jira Project`</mark> in which tickets need to be created, select the <mark style="color:red;">`Issue Type`</mark> and click **Next**

![](<../../.gitbook/assets/jira\_cloud\_squadcast\_4 (1).png>)

**(5)** Then, map the <mark style="color:red;">`Jira Issue Status`</mark> to the available _Squadcast incident statuses_ and click **Next**

![](../../.gitbook/assets/jira\_cloud\_squadcast\_5.png)

**(6)** Select the **Mode** in which you want to add tickets to Jira for incidents in Squadcast: **Manually** or **Automatically** and then, select the _Service(s)_, for whose incidents Jira tickets must be created by Squadcast and click on **Save & Integrate**

![](../../.gitbook/assets/jira\_cloud\_squadcast\_6.png)

That’s it! Your Jira Cloud integration is good to go.

### Usage of the Automatic and Manual Modes <a href="#usage-of-the-automatic-and-manual-modes" id="usage-of-the-automatic-and-manual-modes"></a>

#### Automatic mode <a href="#automatic-mode" id="automatic-mode"></a>

If you have chosen the **Automatic mode** while configuring Jira cloud then you need not do anything. Any incident triggered for the selected Service(s) will automatically _create an issue_ in the _selected Jira Project_ with the _configured Issue Type_.

#### Manual mode <a href="#manual-mode" id="manual-mode"></a>

If **Manual Mode** is chosen, follow the below steps to create a ticket in Jira:

**(1)** Open the incident in Squadcast and click on the **More Actions** button on the **Incident Details** page

![](../../.gitbook/assets/jira\_cloud\_squadcast\_7.png)

**(2)** Select **Jira Cloud** action and click on **Create a ticket in Jira**

![](<../../.gitbook/assets/jira\_cloud\_squadcast\_8 (1).png>) ![](<../../.gitbook/assets/jira\_cloud\_squadcast\_9 (2).png>)

A ticket will be created in the _selected Jira Project_ with the _configured Issue Type_. This action will be recorded in the _Incident Timeline with a hyperlink to the created Jira ticket_.

![](../../.gitbook/assets/jira\_cloud\_squadcast\_10.png) ![](../../.gitbook/assets/jira\_cloud\_squadcast\_11.png)

### Configuring a Jira Project for each Squadcast Service <a href="#configuring-a-jira-project-for-each-squadcast-service" id="configuring-a-jira-project-for-each-squadcast-service"></a>

If you would like for tickets to be created for incidents of each Service in a different Jira Project, you can configure so within the Services page.

**(1)** For a Service, click the **More** options

![](../../.gitbook/assets/jira\_cloud\_squadcast\_14.png)

**(2)** Select **Jira Cloud Project**

![](../../.gitbook/assets/jira\_cloud\_squadcast\_15.png)

**(3)** Here, map the _Jira Project_ of your choice and select the required _Type_

![](../../.gitbook/assets/jira\_cloud\_squadcast\_16.png)

**(4)** Next, you can choose to either create tickets **Manually** or **Automatically** for the Service in the previously selected Project. Additionally, you can map the available Project **Status** to the incident states in Squadcast - <mark style="color:red;">`Triggered`</mark>, <mark style="color:red;">`Acknowledged`</mark>, <mark style="color:red;">`Resolved`</mark>. Then, click **Save**

![](../../.gitbook/assets/jira\_cloud\_squadcast\_17.png)

If you configure a Jira Cloud Project for a Service, this setting will override the previously configured Jira Cloud Extensions settings (the global configuration in Settings > Extensions > Jira Cloud).
