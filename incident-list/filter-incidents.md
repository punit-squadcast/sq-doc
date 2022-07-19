---
description: Filter Incidents
---

# Filter Incidents

Filter Incidents by different parameters like Date & Time of creation affected **Services**, **Alert Sources**, to whom an incident was **Assigned To** or custom **Tags** associated with the incidents.

### Getting Started <a href="#getting-started" id="getting-started"></a>

First, select the **Team** from the team picker on the top

**(1)** Click on **Incidents** on the sidebar

![](../.gitbook/assets/incident\_list\_1.png)

**(2)** Click on **Add Filter** to customize your incident list by applying multiple filters

![](../.gitbook/assets/incident\_list\_7.png)

**(3)** The filters that are available at the moment are:

* Date & Time
* Service
* Alert Source
* Assigned To
* Tags
* Status
* Postmortem

![](../.gitbook/assets/incident\_list\_8.png)

#### Date & Time <a href="#date--time" id="date--time"></a>

This filter allows you to filter down incidents to a **specific time range**. By default, the incidents within the last **30 days** are displayed. Change the filter by choosing a different option.

![](../.gitbook/assets/filter\_1.png)

**Custom Range**

This option allows you to give a custom time range within which you would like to view your incidents. Here, you can also select the exact time by which you would like to filter.

{% hint style="info" %}
**Note:** You will be limited to choosing the custom time range here based on the [plan](https://squadcast.com/pricing) that you are currently on (data retention by the plan).
{% endhint %}

![](../.gitbook/assets/filter\_2.png)

#### Service <a href="#service" id="service"></a>

Filter incidents by [**Services**](../services/adding-a-service.md).

You can choose to filter by multiple Services, so use the checkbox to select all the Services. You can also use the search box to narrow down your options.

![](../.gitbook/assets/filter\_3.png)

#### Alert Source <a href="#alert-source" id="alert-source"></a>

Filter incidents by [**Alert Sources**](../services/adding-a-service.md#alert-sources-integrations).

You can choose to filter by multiple Alert Sources, so use the checkbox to select all the Alert Sources. You can also use the search box to narrow down your options.

![](../.gitbook/assets/filter\_4.png)

#### Assigned To <a href="#assigned-to" id="assigned-to"></a>

Filter incidents by the [**Users**](../manage-users/types-of-users.md), [**Squads**](../manage-teams/squads.md) or [**Escalation Policies**](../escalation-policies/create-and-manage-escalation-policies.md) using this filter.

You can choose to filter by multiple values, so use the checkbox to select all the values. You can also use the search box to narrow down your options.

![](../.gitbook/assets/filter\_5.png)

#### Tags <a href="#tags" id="tags"></a>

Filter Incidents by [**Tags**](../services/event-tagging.md).

![](../.gitbook/assets/filter\_6.png)

* In order to filter by **Tags**, first, select the <mark style="color:red;">`key`</mark>.

![](../.gitbook/assets/filter\_7.png)

* Then select the <mark style="color:red;">`value`</mark> of the **Tag**. You can use the search box to narrow down your options.

![](../.gitbook/assets/filter\_8.png)

**Note:** When you are not filtering by any **Services**, tags across all the **Services** will be displayed. To narrow down your **Tags** by **Service**, make sure to apply the **Service** filter first.

**Search for Custom Tags**

If you are unable to find the option you want to filter by, then you can input custom values for **the Tag** search. In order to do so, enter the custom <mark style="color:red;">`key`</mark> / <mark style="color:red;">`value`</mark> and click on the <mark style="color:red;">`+`</mark> icon to add the custom **Tag** filter.

![](../.gitbook/assets/filter\_9.png) ![](../.gitbook/assets/filter\_10.png)

**Add / Delete Multiple Tag Filters**

To add a new **Tag** filter, open the tags filter and click on the <mark style="color:red;">`+ new tag`</mark> button, and select the <mark style="color:red;">`key`</mark> and <mark style="color:red;">`value`</mark> of the new **Tag**.

To delete a **Tag** filter, click on the cross button of the corresponding **Tag**.

![](../.gitbook/assets/filter\_11.png)

{% hint style="info" %}
**Multiple Tag Filters**

Choosing multiple **Tag** values will serve as a logical `AND` operation. Should you want to see the list of incidents for each **Tag**, make sure to do so in multiple steps.
{% endhint %}

#### Status <a href="#status" id="status"></a>

Filter Incident by **Incident Status**.

Select the _Statuses_ of your choice to filter out incidents by status.

![](../.gitbook/assets/filter\_12.png)

#### Postmortem <a href="#postmortem" id="postmortem"></a>

Filter incidents by checking for the presence or absence of a Postmortem being created and associated with them. Select the options _Included_ **or** _Excluded_ accordingly after selecting the _Postmortem_ option from the filter drop-down.

![](../.gitbook/assets/filter\_16.png)

![](../.gitbook/assets/filter\_17.png)
