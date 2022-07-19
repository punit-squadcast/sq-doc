---
title: Slack
tags:
  - integration
  - slack
keywords: null
last_updated: null
summary: Create incidents in Squadcast from Slack
sidebar: mydoc_sidebar
permalink: docs/slack-as-an-alert-source
folder: mydoc
description: Create incidents in Squadcast from Slack
---

# Slack

### Integrate with Slack

First, configure the [Slack Extension](https://support.squadcast.com/docs/slack) for your Squadcast Organization. Once this is done, you will be able to create incidents directly from Slack and view them on Squadcast.

### Create Incidents from Slack

In the Slack channel from which you want to create an incident in Squadcast, perform the following steps:

**(1)** Invoke the _Squadcast Bot_ by calling out `@squadcast`

![](../../.gitbook/assets/slack\_1.png)

**(2)** Once the bot is added, you will be able to take actions with respect to incidents directly from Slack

#### Using Slash Command in Slack

\{{site.data.alerts.blue-note-md\}} **Help Command**

You can call out `/create_incident help` to walk you through the process within your Slack channel to guide you through the process.

![](../../.gitbook/assets/slack\_2.png)

The command that is used to create an incident from Slack is:

`/create_incident <Incident Message Text>`

\{{site.data.alerts.note-md\}} **Note**

You can call the `/create_incident` or `/create_incident <Incident Message Text>` command to create an incident from Slack.

![](../../.gitbook/assets/slack\_3.png)

This will then prompt a UI pop-up where you can fill in additional information such as:

* Impacted **Service**
* **Incident Message**
* **Incident Description**

![](../../.gitbook/assets/slack\_4.png)

This newly created incident will now show up immediately in the Slack channel and in Squadcast as well. In Squadcast, you can navigate to either [Incident Dashboard](https://support.squadcast.com/docs/incident-dashboard) or [Incident List](https://support.squadcast.com/docs/incident-list-table-view) to view the newly triggered incident.

![](../../.gitbook/assets/slack\_create\_incident\_success\_2.png)

#### Using Message Actions in Slack

You can also choose to create an incident from an existing message in the Slack channel.

**(1)** Click on the **More Actions** icon for the chosen message

![](../../.gitbook/assets/slack\_6.png)

**(2)** Choose the **Create Incident** option from the dropdown shown

![](../../.gitbook/assets/slack\_7.png)

**(3)** In the UI pop-up, fill in all the relevant information needed to create the incident

![](../../.gitbook/assets/slack\_8.png)

The incident has now been created successfully.

![](../../.gitbook/assets/slack\_message\_action\_create\_incident\_success.png)

\{{site.data.alerts.note-md\}} **Important**

The **Squadcast Bot must be called into the channel** where you will want to take any of the above actions to create an incident.

#### How to Video
