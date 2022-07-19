---
description: List view for all your Team's incidents
---

# Incident List View

The **Incident List** view gives you a clear view of all your incidents along with their relevant information at a single glance.

### Accessing the **Incident List** view <a href="#accessing-the-incident-list-view" id="accessing-the-incident-list-view"></a>

First, select the **Team** from the team picker on the top

**(1)** Click on **Incidents** from the sidebar

![](../.gitbook/assets/incident\_list\_1.png)

**(2)** View the following details for every listed incident:

* **Incident Message**
* **Created At**
* **Service** it is affecting
* **Assigned To**
* The **current status** of the incident

![](../.gitbook/assets/incident\_list\_2.png)

#### Quick Filter by Incident Status <a href="#quick-filter-by-incident-status" id="quick-filter-by-incident-status"></a>

Filter incidents by status by using the status drop-down and choosing the appropriate option.

![](../.gitbook/assets/incident\_list\_3.png)

#### Bulk Actions <a href="#bulk-actions" id="bulk-actions"></a>

**Acknowledge** and **Resolve** multiple incidents in one go by bulk selecting the listed incidents and choosing the appropriate action button.

![](../.gitbook/assets/incident\_list\_4.png)

{% hint style="info" %}
**Note:**&#x20;

When an action is selected, it is performed instantly without asking for confirmation so be wary while performing the action.
{% endhint %}

#### Create an Incident Manually <a href="#create-an-incident-manually" id="create-an-incident-manually"></a>

**(1)** Click on **Create new incident**

![](../.gitbook/assets/incident\_list\_5.png)

**(2)** Enter the _Incident Title_, _Incident Description_, select the _Service_, specify who should be notified under _Assign To_, add _Tags_ and click on _Create new incident_ to create the incident

![](../.gitbook/assets/incident\_list\_6.png)

#### Filter Incidents <a href="#filter-incidents" id="filter-incidents"></a>

**(1)** Click on **Add Filter** to filter incidents and create [custom views](save-filter-view.md) for your Team

![](../.gitbook/assets/incident\_list\_7.png)

**(2)** Incidents can be filtered by:

* Date & Time
* Service
* Alert Source
* Assigned To
* Tags
* Status
* Postmortem

![](../.gitbook/assets/incident\_list\_8.png)

Learn more about each filter value [here](filter-incidents.md).

{% hint style="info" %}
**Using the Status Filter**

If you want to filter incidents that are in a particular state (Triggered, Acknowledged, Resolved or Suppressed), in addition to the other filters you use, add the **Status** filter as well.
{% endhint %}

#### Export Incidents <a href="#export-incidents" id="export-incidents"></a>

**(1)** Add the filters of your choice and click on the **download** icon and select either the **CSV** or the **JSON** format option from the drop-down

![](../.gitbook/assets/incident\_list\_9.png)

{% hint style="danger" %}
**Incident Export Limit**

At the moment, you can export only a maximum of 1000 incidents at once. Please tweak your filters to ensure the count of listed incidents is within the limit for every export. There are no limits on the number of times you can export incidents.
{% endhint %}

**(2)** The exported **CSV** or **JSON** file will have the following fields:

* Incident ID
* Title
* Description
* Status
* Service
* Alert Source
* Assignee
* Created At
* Acknowledged At
* Resolved At
* Tags
* Event Count
* TTA (Time to Acknowledge)
* TTR (Time to Resolve)
* Activity Logs

{% hint style="success" %}
**Export Incidents: Public API**

Exporting incidents as **CSV** or **JSON** is available as a Public API. Check out the API documentation [here](https://apidocs.squadcast.com/#3d00d5c6-6b9b-410c-a11b-0da72c60d419).
{% endhint %}

#### Incident List Search <a href="#incident-list-search" id="incident-list-search"></a>

Search for incidents based on either the **Incident Message** or the **Incident Description** using the Text Search box.

![](../.gitbook/assets/incident\_list\_10.png)

#### Load More Incidents <a href="#load-more-incidents" id="load-more-incidents"></a>

In order to load more incidents, just scroll to the end of the list and the available existing incidents will be automatically displayed.

![](../.gitbook/assets/incident\_list\_11.png)
