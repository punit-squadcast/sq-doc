# Notification Rules

Notification Rules determine how an individual user is notified for an incident that is assigned to them. One can set up rules to be notified on any of the following notification channels:

* Email
* Push notification on the Squadcast mobile app
* SMS
* Phone

{% hint style="info" %}
**Edit Notification Rules for other users of Squadcast**

Irrespective of your User Role in Squadcast, you will only be able to set/edit your own Notification Rules. You will not be able to do it for any other member of Squadcast. If you wish to explicitly specify Notification Channels for all the users, this can be done in the Escalation Policy by selecting **Custom** from the drop-down.
{% endhint %}

### Edit Notification Rules <a href="#edit-notification-rules" id="edit-notification-rules"></a>

1. Click on the user icon in the upper right corner and select **Profile**

![](<../../.gitbook/assets/notification\_rules\_1 (1) (1).png>)

2\. You will be taken into the **My Profile** section where you can see the User Details on the left and the **Notification Rules** on the right. Click on the **Edit** button to edit the rules

![](<../../.gitbook/assets/notification\_rules\_2 (2) (1) (1) (2).png>)

3\. Choose the medium from the drop-down and enter the amount of time after the incident trigger when you wish to get notified

4\. You can also add new rules by clicking **Add More Rules** at the bottom

5\. Select **Save** after making changes to save the configuration

![](<../../.gitbook/assets/notification\_rules\_3 (1) (4).png>)

{% hint style="info" %}
**Note:**

By default, every new user’s **Notification Rules** would be defined by Squadcast as indicated by the screenshot below:

<img src="../../.gitbook/assets/notification_rules_4.png" alt="" data-size="original">
{% endhint %}

You’re good to go. Now, when an incident is assigned to **you**, you will be notified based on your notification preferences set in the **Notification Rules** section.

{% hint style="warning" %}
**Things to Note:**

1. You can set up a rule to be notified immediately, as soon as the incident is triggered, if you input 0 in the text box that asks for time.
2. You cannot add `SMS` and `Phone` multiple times within your Notification Rules. The required repetition can be achieved by setting up the Escalation Policies right. However, there are no such limits for `Push` or `Email`.
{% endhint %}
