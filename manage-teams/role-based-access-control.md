---
description: Understanding the Roles and Access Controls for Teams and Custom Roles
---

# Role Based Access Control

Roles are a _set of permissions_ granted that are specific to the Team that the user is a member of. There are pre-defined Roles that can be directly assigned to the members of the Team. If one wants to define [Custom Roles](broken-reference/), that is also doable.

It is critical to thoroughly note that **Roles are Team-specific**, that is, **Roles will allow you specific abilities for just that Team that you are a part of**.

### Default Types of Roles and Abilities <a href="#default-types-of-roles-and-abilities" id="default-types-of-roles-and-abilities"></a>

There are 4 different default Roles that can be assigned to a Team member in Squadcast. See below to understand what they are, along with their abilities.

### 1. Manage Teams <a href="#1-manage-teams" id="1-manage-teams"></a>

This Role will allow you to manage just this Team. The abilities are:

| Entity | Abilities                |
| ------ | ------------------------ |
| Teams  | `read` `update` `delete` |

### 2. Admin <a href="#2-admin" id="2-admin"></a>

| Entity              | Abilities                         |
| ------------------- | --------------------------------- |
| Escalation Policies | `create` `read` `update` `delete` |
| Postmortems         | `create` `read` `update` `delete` |
| Runbooks            | `create` `read` `update` `delete` |
| Schedules           | `create` `read` `update` `delete` |
| Services            | `create` `read` `update` `delete` |
| SLOs                | `create` `read` `update` `delete` |
| Squads              | `create` `read` `update` `delete` |
| Status Pages        | `create` `read` `update` `delete` |
| Team analytics      | `read`                            |

### 3. User <a href="#3-user" id="3-user"></a>

| Entity              | Abilities       |
| ------------------- | --------------- |
| Escalation Policies | `read` `update` |
| Postmortems         | `read` `update` |
| Runbooks            | `read` `update` |
| Schedules           | `read` `update` |
| Services            | `read` `update` |
| SLOs                | `read` `update` |
| Squads              | `read` `update` |
| Status Pages        | `read` `update` |
| Team analytics      | `read`          |

### 4. Observer <a href="#4-observer" id="4-observer"></a>

| Abilities | Entity              |
| --------- | ------------------- |
| `read`    | Escalation Policies |
| `read`    | Postmortems         |
| `read`    | Runbooks            |
| `read`    | Schedules           |
| `read`    | Services            |
| `read`    | SLOs                |
| `read`    | Squads              |
| `read`    | Status Pages        |
| `read`    | Team analytics      |

![](../../.gitbook/assets/rbac\_roles.png)

{% hint style="warning" %}
**Important:**`Stakeholders` can be added with only `Observer` Role within a Team.
{% endhint %}

### Manage Roles and Abilities <a href="#manage-roles-and-abilities" id="manage-roles-and-abilities"></a>

Follow the steps below manage Roles for a Team:

1. Click on **Settings** in the sidebar

![](<../../.gitbook/assets/add\_and\_delete\_users\_1 (1) (1) (1) (4).png>)

2\. Click on **Teams** from the secondary navigation menu and select the Team you want to manage _Roles and Access Controls_ for

![](<../../.gitbook/assets/add\_and\_delete\_teams\_1 (1) (2).png>)

3\. Click on **Roles** from the horizontal menu and you will have the option to <mark style="color:red;">`edit`</mark> or <mark style="color:red;">`delete`</mark> the Roles and Access Controls via the <mark style="color:red;">`More Option`</mark>

![](../../.gitbook/assets/rbac\_2.png)

{% hint style="info" %}
**Note:** Roles are Team specific, i.e. roles will allow you specific abilities for just that team that you’re a part of.
{% endhint %}

### Custom Roles <a href="#custom-roles" id="custom-roles"></a>

There might be situations where the predefined _Roles and Abilities_ available for members of a Team in Squadcast, by default, are not sufficient or that they do not align with how you want your Team members to be organized (in terms of Access Controls).

In such situations, you can either choose to modify one of the default Roles itself or you can create **Custom Roles** to provide special, customised permissions to specific types of users in your Organization for that Team.

It is critical to thoroughly note that only members of the Team with **Manage Team** Role permissions can create and manage **Custom Roles**.

### Creating a Custom Role <a href="#creating-a-custom-role" id="creating-a-custom-role"></a>

Follow the steps below to create a Custom Role for a Team:

1. Click on **Settings** in the sidebar

![](<../../.gitbook/assets/add\_and\_delete\_users\_1 (1) (1) (1) (8).png>)

2\. Click on **Teams** from the secondary navigation menu and select the Team for which you want to add the **Custom Role**

![](<../../.gitbook/assets/add\_and\_delete\_teams\_1 (1) (1).png>)

3\. Click on **Roles** from the horizontal menu and scroll down to the bottom of the page

![](../../.gitbook/assets/rbac\_3.png)

4\. Click on **Add new team role**. Here:

* Give the Custom Role a **Name** indicating the Role type
* Next, for the available Entities (Escalation Policies, Postmortems, Schedules, Services, Squads, Status Pages), select the Access Controls (<mark style="color:red;">`read`</mark>, <mark style="color:red;">`create`</mark>, <mark style="color:red;">`update`</mark>, <mark style="color:red;">`delete`</mark>)

5\. Click on **Save** to create the new Custom Role for the Team

![](../../.gitbook/assets/rbac\_4.png)
