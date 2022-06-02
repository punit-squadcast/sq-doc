---
description: Create Maintenance Mode windows for Services
---

# Maintenance Mode

Maintenance Mode enables you to reduce alert noise during the scheduled maintenance window. Alerts generated during active maintenance windows would be automatically suppressed and hence, no notifications are generated for those suppressed alerts. One can quickly list incidents that are in the suppressed state by simply filtering them in the [Incidents](../incident-list/incident-list-view.md#quick-filter-by-incident-status) page.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Maintenance Windows).

### Setting up a Maintenance Mode window for a Service <a href="#setting-up-a-maintenance-mode-window-for-a-service" id="setting-up-a-maintenance-mode-window-for-a-service"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

1. Click on **Services** in the primary navigation

![](../.gitbook/assets/maintenance\_1.png)

1. Click on the **More options** icon for the Service of your choice and select **Maintenance Mode** from the drop-down
2. Toggle the button **on** to enable Maintenance Mode window creation
3. Enter the **Date and Time range** during which maintenance would be carried out

Maintenance windows can also be scheduled i.e. you can also choose to repeat it every day, every 7 days or 30 days

5\. **Save** the set configuration

That’s it, the maintenance window has now been created for the Service!

{% hint style="info" %}
**Indication of Services under Maintenance**

\
A Service in Maintenance Mode is indicated with an "Under Maintenance" tag on the Service card as seen in the screenshot below
{% endhint %}

### FAQs <a href="#faqs" id="faqs"></a>

1. Where can I see all the suppressed incidents?

Suppressed incidents can be viewed on the **Dashboard** by clicking on the `Suppressed` tab as shown below:

On the **Incidents** page, suppressed incidents can be viewed under the `Suppressed` state as shown below:

2\. How do I know if an incident is suppressed due to scheduled maintenance and not due to any other Suppression Rule?

In the Incident’s Activity Timeline the reason for suppression is displayed, in this case it will be <mark style="color:red;">`auto suppressed due to scheduled maintenance`</mark>.

3\. Is a maintenance window global to the associated Service?

Yes, it is global to the associated Service.

4\. Can I change the state of a suppressed incident?

No, <mark style="color:red;">`suppressed`</mark> would be the final state of an incident. It cannot be changed.

5\. I am able to view Services for my Team but am unable to add a maintenance window to it. What am I missing?

The User Role associated with your user in the Team must have required permissions (such as <mark style="color:red;">`Update`</mark>) to manage/edit Services.
