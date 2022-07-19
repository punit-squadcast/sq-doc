---
description: Rosters for your customer support engineers or on-call teams
---

# Create and Manage On-call Schedules & Rotations

{% embed url="https://squadcast.wistia.com/medias/9wor2hwbo9" %}

### Creating an On-call Schedule <a href="#creating-an-on-call-schedule" id="creating-an-on-call-schedule"></a>

Ensure that the right Team is selected from the team picker present at the top.

1. Click on **Schedules** in the primary navigation

![](<../.gitbook/assets/schedules\_1 (2).png>)

2\. Click on **Add Schedule** on the right-hand side of the screen

![](../.gitbook/assets/schedules\_2.png)

3\. Enter the following information:

* **Schedule Name**: Give the schedule a name which you can use while adding the on-call schedule to the calendar
* **Schedule Description**: This is a short description of the schedule explaining what it is and why it exists
* **Schedule Color**: You can also set a colour for a specific schedule, which will be used while rendering the on-call on the calendar

![](../.gitbook/assets/schedules\_3.png)

4\. Pick **any day** of the calendar by clicking on it, to create an on-call shift starting from that day. You can also drag your cursor from one day to another, to automatically set the **Start Date** and **End date**

![](../.gitbook/assets/schedules\_4.png)

5\. **Shift Name** indicates the name of the particular _Shift_ being set up within the Schedule. This is a mandatory field and the user needs to enter a value for this before proceeding further

![](<../.gitbook/assets/schedules\_5 (1).png>)

6\. Choose the **Schedule** you want to create this on-call shift for, from the drop-down

![](../.gitbook/assets/schedules\_6.png)

7\. Input the **Start date**, **Start time**, **End date** and **End time** to determine when the shift begins and when it ends respectively

![](../.gitbook/assets/schedules\_7.png)

{% hint style="danger" %}
Do not check the <mark style="color:red;">`Is Override`</mark> box if you want to create a normal shift.
{% endhint %}

8\. **Repeats**- Repetitions can be daily, weekly or monthly. You can also restrict the schedules to specific times of the day or during specific days of the week, based on your need

Now, choose the appropriate option:

* **Everyday** - Use this to create a daily schedule (applicable for all 7 days of the week)

![](../.gitbook/assets/schedules\_8.png)

* **Weekly – Once a week** - Select this option to create a schedule that occurs only on one day of the week. You can select the day on which this shift will be active

![](../.gitbook/assets/schedules\_9.png)

* **Weekly – Particular Days Of a Week** - Select this option to create a schedule that occurs on particular days of the week. You can select the days on which this shift will be active

![](../.gitbook/assets/schedules\_10.png)

* **Custom** - Select this option to create any other custom shift of your choice. You can customize the number of days/weeks/months you want the on-call to repeat for

![](../.gitbook/assets/schedules\_11.png)

{% hint style="info" %}
To create a _recurring schedule_, mark **Ends** as **Never** (enable the checkbox). **Never** is enabled by default. If you do not want a recurring schedule, disable the checkbox and specify the end date.
{% endhint %}

9\. Add in the users who would be on call for this shift under the **Assignee Groups** section. Each group behaves as a different rotation. Use **Add Group** to add multiple such groups

![](../.gitbook/assets/schedules\_12.png)

{% hint style="info" %}
Adding **Squads** within an **Assignee Group** would mean every member of the Squad is on-call based on the shift defined. Squadcast does not pick members one by one from within a Squad and **rotates** between them. For a rotation to happen _between 1 or more entities (Users or Squads)_, add them to different Assignee Groups instead.
{% endhint %}

10\. Select the number of shifts after which you want to switch between the Assigned Groups

**Example 1**: <mark style="color:red;">`Buzz Lightyear`</mark> is part of the <mark style="color:red;">`#1 Group`</mark> and <mark style="color:red;">`Charlie Stark`</mark> is part of the <mark style="color:red;">`#2`</mark>` ```` `<mark style="color:red;">`Group`</mark>.

* If **Every Shift** is chosen then <mark style="color:red;">`#1 Group`</mark> and <mark style="color:red;">`#2 Group`</mark> would be on-call on alternate days
* If **Every 7 Shifts** is chosen then <mark style="color:red;">`#1 Group`</mark> would be on-call the first 7 days and <mark style="color:red;">`#2 Group`</mark> would be on-call the following 7 days and so on

![](../.gitbook/assets/schedules\_13.png)

11\. That’s it! Click on **Create** to save the schedule

{% hint style="info" %}
**Adding Schedules to Escalation Policies**

You will need to add a Schedule to an Escalation Policy for the on-call users to be notified when an incident is triggered for a Service
{% endhint %}

### Gaps in your Schedule <a href="#gaps-in-your-schedule" id="gaps-in-your-schedule"></a>

It is important to ensure that there are no gaps in your Schedules.

* If you have any gaps in your Schedules configuration, the system will prompt the banner **You have gaps in your schedule** right above the Schedules calendar view
* To know more details about the gaps, you can click on the **You have gaps in your schedule** banner and it will show you the name of the Schedule along with the date and time during which the gap has been detected

![](../.gitbook/assets/schedules\_14.png)

### Manage an Existing On-call <a href="#manage-an-existing-on-call" id="manage-an-existing-on-call"></a>

#### Update <a href="#update" id="update"></a>

1. Select an existing on-call by clicking over any assigned User/Squad on the calendar

![](../.gitbook/assets/schedules\_15.png)

2\. Click on **Edit**

![](../.gitbook/assets/schedules\_16.png)

3\. Select the appropriate **Update method**:

![](../.gitbook/assets/schedules\_17.png)

* **This Event Only** - to update only that particular event When this choice is made, you will not see the option to _Repeat_ as this is considered a one-off necessity to update. Also, this will only show the assignees of the current event picked for the update
* **This and proceeding events** - to update the selected event and all the events that come afterwards

In the last two **Update methods**, the modal shows the **Repeats** checkbox and also, shows all the Assignee Groups in the series.

{% hint style="danger" %}
You cannot update past events as it is meant to serve as an accurate record of the past on-call Schedule.
{% endhint %}

#### Choosing a different starting Group <a href="#choosing-a-different-starting-group" id="choosing-a-different-starting-group"></a>

Starting Group determines the Group that starts the defined Rotation. This can only be defined when the update method chosen is **This and the Following Shifts** option is selected in the update method.

![](../.gitbook/assets/schedules\_group\_2.png)

{% hint style="info" %}
**Note:**

By Default #1 Group will be the starting Group.

![](../.gitbook/assets/schedules\_group\_1.png)
{% endhint %}

#### Deleting an On-call <a href="#deleting-an-on-call" id="deleting-an-on-call"></a>

1. Delete an existing on-call by clicking the **Delete** button at the bottom right corner of the **Update on-call shift** dialogue box

![](../.gitbook/assets/schedules\_delete\_1.png)

2\. Choose the appropriate option:

* **This event only** - It will delete only the selected event of the series
* **This and proceeding events** - It will delete the event selected as well as all the future events belonging to that series

![](../.gitbook/assets/schedules\_delete\_2.png)

### FAQs <a href="#faqs" id="faqs"></a>

**Q:** How can I add users in different time zones to the Schedule?

**A:** The selected timezone will default to the local machine timezone. This is especially beneficial for geography-based on-call rotations. The Team members will be able to view any created on-call schedule in their local time.

**Q:** Can I send on-call reminder notifications?

**A:** Yes, users can choose to receive on-call reminder notifications ahead of their shifts. They can set this up according to their preference as mentioned [here](https://support.squadcast.com/docs/oncall-reminder-rules). If a created override shift has less than the time specified to begin, the notification will go out immediately after the override creation.

**Q:** Why cannot Stakeholders be added to the on-call Schedules?

**A:** _Stakeholders or Users with Observer roles_ are read-only users in Squadcast. Hence they cannot be added to an on-call schedule. When you try adding them you would see an error message as shown below.

![](../.gitbook/assets/schedules\_20.png)
