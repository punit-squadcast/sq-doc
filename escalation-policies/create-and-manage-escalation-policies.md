# Create & Manage Escalation Policies

Define rules indicating when and how alerts will escalate to various Users, Squads and (or) Schedules within your Organization

Escalation Policies ensure that the right people are notified at the right time. Incident notifications can be configured to escalate to Users, Squads or Schedules in a given order and time. You can create different Escalation Policies for different Services.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role for the user in the Team must have the necessary permissions in order to manage Escalation Policies.

### Creating an Escalation Policy <a href="#creating-an-escalation-policy" id="creating-an-escalation-policy"></a>

Ensure that the right Team is selected used the team picker at the top of the screen.

**(1)** Click on **Escalation Policies** from the navigation sidebar

**(2)** Click on **Add Escalation Policy** to create one from scratch

**(3)** Give the Escalation Policy a **Name** and an optional **Description**

**(4)** Add `Users`, `Squads` or `Schedules` as recipients of notifications at any level of the Escalation Policy

**(5)** Enter the appropriate time for **Escalate After**, giving enough notice for your recipients to acknowledge the alert after which it will escalate to the next level (if defined)

**(6)** There are two ways to add the medium of notification under **Notification Rules**:

From the dropdown, you can select either **Personal** or **Custom**

(a) **Custom** - As an Admin, you can select one or more of the available notification channels **(Email, Push, SMS and Phone)** to explicitly specify the channel via which the mapped users need to receive the incident notifications

(b) **Personal Notification Rules** - Allow users to set-up their preferred medium of notification for incidents

**(7)** Use **Add Rule** to add a new Escalation Rule (layer of escalation) in the policy

**(8)** **Repeat the **_**entire policy**_ if no one acknowledges the incident even after the Escalation Policy has been executed fully once

**(9)** Click on **Save** to save and view the Escalation Policy

### Editing/Deleting an Escalation Policy <a href="#editingdeleting-an-escalation-policy" id="editingdeleting-an-escalation-policy"></a>

**(1)** To edit an existing Escalation Policy, click on **More Options** for that particular Escalation Policy

**(2)** Choose **Edit** to modify the existing Escalation Policy or **Delete** to delete the Escalation Policy entirely

**(3)** After modifying the Escalation Policy, click on **Save**

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** Can I add members from different Teams into an Escalation Policy for my Team?

No, adding members from across Teams into an Escalation Policy is not allowed. Any member that needs to be added in the Escalation Policy for a Team must be a part of the same Team.

**(2)** Is there a way to introduce Round Robin assignment of incidents to different entities within an escalation level?

Yes, please refer to the documentation [here](https://support.squadcast.com/docs/round-robin-advanced-escalations)
