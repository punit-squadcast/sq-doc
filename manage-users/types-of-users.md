---
description: >-
  Understanding the different User Types supported in Squadcast - Account
  Owners, Users and Stakeholders
---

# Types of Users

Squadcast has **three different types of users**:

{% file src="../.gitbook/assets/Incidents.mp4" %}

### Account Owner <a href="#account-owner" id="account-owner"></a>

Squadcast allows only one Account Owner per Organization. An Account Owner has all the privileges in that Organization and by default will also be responsible for the billing of the account.

{% hint style="info" %}
**Note:** The user that first signs-up for the account & creates an Organization is by _default_ the `Account Owner`. Learn about transferring ownership of the account to another user, [here](change-account-owner.md).
{% endhint %}

{% hint style="warning" %}
**Important:**

Each Squadcast Organization can have only **one** `Account Owner` type of user.
{% endhint %}

### User <a href="#user" id="user"></a>

Users, by default, have the ability to customize their Profile, Notification Rules, Respond to, and Resolve incidents. Typically, Users are the Engineers, SREs, Systems Engineers or anyone in your team that handles incident management & on-call.

### Stakeholder <a href="#stakeholder" id="stakeholder"></a>

As the name implies, these are typically other participants from the Organization who may have an interest in the incident management process. They could be Product Managers, Customer Support Representatives, CxOs, and so on.

Stakeholders have **view-only access** of all incidents. This means that Stakeholders are **not notified by default** for any of the incidents created in Squadcast. If Stakeholders need to be notified of incidents, [this](../incidents-page/incident-notes.md#mentioning-users-squads-and-teams-in-notes) is how it can be done.

Stakeholders also have the ability to create manual incidents should they notice something wrong and want to notify the on-call team of it.

{% hint style="warning" %}
**Important:**

* Stakeholders will not receive SMS/Phone call notifications for incidents in Squadcast.
* Stakeholders cannot be added to Schedules or Escalation Policies.
{% endhint %}
