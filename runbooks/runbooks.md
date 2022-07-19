---
description: >-
  Create, attach, reference and mark progress for incident resolution using
  Runbooks
---

# Runbooks

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=b0SA-6Cl530" %}

### Understanding Runbooks <a href="#understanding-runbooks" id="understanding-runbooks"></a>

A Runbook is a compilation of routine procedures and operations that are documented for reference while working on a critical incident. Sometimes, it can also be referred to as a Playbook.

Typically, organizations store their incident checklists in various places such as Google Docs, Notion, Confluence etc., and sometimes even stored in a physical notebook. Valuable time is lost in searching for these different checklists and following up on the list items while working on critical incidents.

In order to avoid delays, scrambling between multiple tools and tabs to find the right checklist, Squadcast brings to you Runbooks. This feature will help you access the relevant Runbook, associate it with incidents and assign tasks to relevant users.

Simple Runbooks are a checklist of tasks that need to be performed manually for an incident. These could either be procedures that need to be performed during the occurrence of a Sev1 incident, or technical/functional instructions to debug and fix a certain issue, along with the code that needs to be manually executed.

One can easily create Runbooks and use it as a reference once it is attached to an incident. Additionally, one can mark the progress against each step in the Runbook.

{% hint style="info" %}
**Note:**

Simple Runbooks will be available for accounts in the [Pro and Enterprise plans](https://squadcast.com/pricing).
{% endhint %}

### Creating Runbooks <a href="#creating-runbooks" id="creating-runbooks"></a>

#### RBAC Prerequisites <a href="#rbac-prerequisites" id="rbac-prerequisites"></a>

Runbooks are a Team-level entity and in order to create a Runbook, the user role should have the following Team-level Role permissions:

* <mark style="color:red;">`create`</mark> permission to create Runbooks
* <mark style="color:red;">`read`</mark> permission for viewing Runbooks
* <mark style="color:red;">`update`</mark> permission for editing Runbooks
* <mark style="color:red;">`delete`</mark> permission for deleting Runbooks

![](../.gitbook/assets/Runbook-role-permission.png)

**(1)** To create a Runbook, the user needs to click on the **Runbook** menu on the left navigation bar and click on the **Create Runbook** button

![](../.gitbook/assets/Runbooks-left-nav.png)

**(2)** In the **Create Runbook** page:

* Enter a **Name** for the Runbook
* Start adding steps for the Runbook by clicking on the **+ Add Step** button

You can add as many steps as you like. Every step supports <mark style="color:red;">`Markdown`</mark>, hence you can use Markdown formatting features like Code Blocks, Bold, Italic, Ordered & Unordered List, Images & Links. You can manually upload images and attachments as well.

![](../.gitbook/assets/create-runbook-md.png)

Although you can add all the series of actions within a single step, we recommend you add each action as a separate step. It would be helpful to mark the progress of each step by checking it done.

![](../.gitbook/assets/create-runbook-rearrange.png)

You can switch between the <mark style="color:red;">`Edit`</mark> mode & <mark style="color:red;">`View`</mark> mode (Preview) by using the Visual/Markdown option. You can also drag & drop each step to rearrange their order.

After adding all the details, click on the **Save** button and the Runbook is created.

![](../.gitbook/assets/create-runbook-visual.png)

Once created, you can view, edit or delete an existing Runbook.

{% hint style="info" %}
**Note:**

The Runbooks created here to act as a template and any update to the Runbook will only get applied to subsequent incidents and not to any previously attached incidents.
{% endhint %}

### Attaching Runbooks to Incidents <a href="#attaching-runbooks-to-incidents" id="attaching-runbooks-to-incidents"></a>

**(1)** Open an incident and click on the **Runbooks & Tasks** tab and then click on the **Attach Runbook** option

![](../.gitbook/assets/incidents-attach-runbooks.png)

**(2)** Select the Runbook(s) that you want to be attached to the incident and click on the final **Attach Runbooks** button

![](../.gitbook/assets/attach-runbooks.png)

You have the option to attach more than one Runbook to an incident.

![](../.gitbook/assets/multiple-runbooks.png)

**(3)** The Runbook will be attached and listed. One can then follow the Runbook and perform the steps. They can also mark the completion of each step by checking the checkbox for each step

![](../.gitbook/assets/attached-runbooks-expanded-progress.png)

{% hint style="info" %}
**Note:**

Every action on a Runbook, such as adding a Runbook, or completing a step - of it gets recorded in the Incident Timeline automatically.
{% endhint %}

### Incident Tasks <a href="#incident-tasks" id="incident-tasks"></a>

Tasks are instructions or to-dos for other team members or even follow-up tasks for an incident. The ability to have tasks associated with an incident comes in handy for critical incidents where most often than not, there would be a list of tasks that need to be completed even post-incident closure, to ensure final fixes are in place.

### Creating Tasks <a href="#creating-tasks" id="creating-tasks"></a>

**(1)** To create a task, click on the **Add Task** option under the **Runbooks & Tasks** tab

![](../.gitbook/assets/add-task-incident.png)

**(2)** Here, enter the details of the task. You can use <mark style="color:red;">`Markdown`</mark> formatting for it. Then, click on the final **Add Task** button to generate your task list

![](../.gitbook/assets/add-task.png)

**(3)** Similar to Runbook actions, the completion of the task can also be marked using the checkbox

![](../.gitbook/assets/task-added.png)

{% hint style="info" %}

{% endhint %}

For any queries on Runbooks and Tasks, reach out to our Support Team and they will be happy to assist you.
