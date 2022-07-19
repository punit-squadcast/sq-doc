---
description: >-
  Define rules indicating when and how alerts will escalate to various Users,
  Squads and (or) Schedules within your Organization
---

# Create & Manage Escalation Policies

Escalation Policies ensure that the right people are notified at the right time. Incident notifications can be configured to escalate to Users, Squads or Schedules in a given order and time. You can create different Escalation Policies for different Services.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role for the user in the Team must have the necessary permissions in order to manage Escalation Policies.

### Creating an Escalation Policy <a href="#creating-an-escalation-policy" id="creating-an-escalation-policy"></a>

Ensure that the right Team is selected using the team picker at the top of the screen.

**(1)** Click on **Escalation Policies** from the navigation sidebar

![](../.gitbook/assets/create\_escalation\_1.png)

**(2)** Click on **Add Escalation Policy** to create one from scratch

![](../.gitbook/assets/create\_escalation\_2.png)

**(3)** Give the Escalation Policy a **Name** and an optional **Description**

![](<../.gitbook/assets/create\_escalation\_3 (1).png>)

**(4)** Add <mark style="color:red;">`Users`</mark>, <mark style="color:red;">`Squads`</mark> or <mark style="color:red;">`Schedules`</mark> as recipients of notifications at any level of the Escalation Policy

![](../.gitbook/assets/create\_escalation\_4.png)

**(5)** Enter the appropriate time for **Escalate After**, giving enough notice for your recipients to acknowledge the alert after which it will escalate to the next level (if defined)

![](../.gitbook/assets/create\_escalation\_5.png)

{% hint style="info" %}
**Notify your team members as soon as an incident is triggered in Squadcast**

If you want to notify your team members as soon as an incident is triggered in Squadcast, set the **Escalate After** time for the first layer of escalation (first Escalation Rule) to **0 mins**. As and when an alert reaches Squadcast for the Service, an incident is created for it and the mapped users as in the Escalation Policy will get notified **of** it immediately based on the notification channels selected.

![](../.gitbook/assets/create\_escalation\_13.png)
{% endhint %}

{% hint style="info" %}
**Escalate After and the Order of Rules**

The time in (mins) input in the `Escalation After` text box takes the absolute time from the time of the incident creation.

That is, the time input in all the levels of escalation is calculated from the time of the incident trigger.

The order of the rules will be carried out based on the time input. That is, from the shortest to the longest time, irrespective of the order in which the rules are placed while defining.
{% endhint %}

**(6)** There are two ways to add the medium of notification under **Notification Rules**:

From the dropdown, you can select either **Personal** or **Custom**

![](../.gitbook/assets/create\_escalation\_6.png)

(a) **Custom** - As an Admin, you can select one or more of the available notification channels **(Email, Push, SMS and Phone)** to explicitly specify the channel via which the mapped users need to receive the incident notifications

![](../.gitbook/assets/create\_escalation\_7.png)

(b) **Personal Notification Rules** - Allow users to **set up** their preferred medium of notification for incidents

{% hint style="info" %}
**Note:**

By default, **Personal Notification Rules** (as indicated by **the Personal** option in the dropdown) are enabled for all the mapped users in the Escalation Rule.
{% endhint %}

**(7)** Use **Add Rule** to add a new Escalation Rule (layer of escalation) in the policy

![](../.gitbook/assets/create\_escalation\_8.png)

**(8)** **Repeat the \_entire policy**\_ if no one acknowledges the incident even after the Escalation Policy has been executed fully once

![](../.gitbook/assets/create\_escalation\_9.png)

{% hint style="warning" %}
**Maximum Repeats Possible**

You can repeat any Escalation Policy for a **maximum of 3 times** only.

![](../.gitbook/assets/create\_escalation\_12.png)
{% endhint %}

**(9)** Click on **Save** to save and view the Escalation Policy

![](../.gitbook/assets/create\_escalation\_10.png) ![](../.gitbook/assets/create\_escalation\_11.png)

{% hint style="warning" %}
**Important**

If the incident has transitioned away from the **Triggered** state when it was assigned to a specific Escalation Policy, then the rest of the rules in the Escalation Policy will not be executed.
{% endhint %}

### Editing/Deleting an Escalation Policy <a href="#editingdeleting-an-escalation-policy" id="editingdeleting-an-escalation-policy"></a>

**(1)** To edit an existing Escalation Policy, click on **More Options** for that particular Escalation Policy

**(2)** Choose **Edit** to modify the existing Escalation Policy or **Delete** to delete the Escalation Policy entirely

![](../.gitbook/assets/edit\_escalation\_1.png)

**(3)** After modifying the Escalation Policy, click on **Save**

{% hint style="info" %}
**Note**

Before deleting an Escalation Policy, **ensure that it is not associated with any of the Services or that there are no open incidents associated with the Escalation Policy**, otherwise**,** you will be prohibited from deleting it.
{% endhint %}

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** Can I add members from different Teams into an Escalation Policy for my Team?

No, adding members from across Teams into an Escalation Policy is not allowed. Any member that needs to be added in the Escalation Policy for a Team must be a part of the same Team.

**(2)** Is there a way to introduce Round Robin assignment of incidents to different entities within an escalation level?

Yes, please refer to the documentation [here](https://support.squadcast.com/docs/round-robin-advanced-escalations)
