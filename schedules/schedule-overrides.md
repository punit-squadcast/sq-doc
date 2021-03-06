---
description: >-
  This feature allows you to create schedules which will override your normal
  schedules
---

# Schedule Overrides

Make one-time adjustments to existing on-call schedules and help on-call engineers with planned vacations, unplanned illnesses, or other events that happen during their on-call shifts. This way, only the users in override schedules will get notified of incidents during the scheduled time period.

### Creating a Schedule Override <a href="#creating-a-schedule-override" id="creating-a-schedule-override"></a>

Ensure that the right Team is selected from the team picker present at the top.

**(1)** Click on **Schedules** in the primary navigation

![](../.gitbook/assets/schedules\_1.png)

**(2)** On the calendar, click on a date or drag over the date(s) on which you’d like to create the override shift

![](../.gitbook/assets/schedule\_overrides\_1.png)

**(3)** Select the Schedule for which this override shift will be implemented from the dropdown

![](../.gitbook/assets/schedule\_overrides\_2.png)

**(4)** Fill in the Override Shift details i.e. Start date, Start time, End date and End time

![](<../.gitbook/assets/schedule\_overrides\_3 (1).png>)

**(5)** Check the **Is Override** box

![](<../.gitbook/assets/schedule\_overrides\_4 (1).png>)

**(6)** **Optional** - Fill in the repetition configuration as per the requirement

![](../.gitbook/assets/schedule\_overrides\_5.png)

**(7)** Add the User(s) who would take over the shift

![](../.gitbook/assets/schedule\_overrides\_6.png)

**(8)** Click on **Create** to save this as an override shift. The Override shift would be displayed for the selected date(s)

![](../.gitbook/assets/schedule\_overrides\_7.png)

#### Points to note about Scheduled Overrides <a href="#points-to-note-about-scheduled-overrides" id="points-to-note-about-scheduled-overrides"></a>

* Creating an override shift is identical to normal shifts, except for the fact that they are marked as **Override**
* If an override shift overlaps with one or more shifts in the same on-call schedule, **only the assignees in the override shift are notified**
* If an override shift does not overlap with any other shift, it behaves like a normal shift. It will still be marked as an **Override**. If a new normal schedule is created during an existing override shift period, the override shift will continue to override the new schedule for the scheduled override period
* If two or more override shifts overlap, assignees from all of the override shifts will be notified when an incident is triggered
