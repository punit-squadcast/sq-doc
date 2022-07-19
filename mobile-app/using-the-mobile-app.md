---
description: >-
  This document briefly explains all that you can do on our native mobile
  application available for both iOS and Android.
---

# Using the Mobile App

You can use our mobile app to Acknowledge, Reassign, take Action, and Resolve from the mobile app. You can also view who is on-call from the Schedules Tab. The mobile app will walk you into the **Incident List** view where you will be able to view incidents organized by Incident status, that is, Triggered, Acknowledged and Resolved.

{% hint style="info" %}
**Note**\
In order to use the mobile app, make sure you have verified your email address. You can do that by opening the verification link sent in your email in a browser.
{% endhint %}

{% hint style="success" %}
**SSO login now available on Mobile App**

We have enabled SSO login for mobile applications. Check the [SSO login for the mobile apps section](https://support.squadcast.com/docs/using-the-mobile-app#sso-login-support-for-mobile-apps) for more details.
{% endhint %}

### Incident List <a href="#incident-list" id="incident-list"></a>

Once you are logged into the application, you will be navigated to the **Incident List** page. Incidents are organized according to incident status. In the tab above, you will be able to view the number of incidents in the open state (Triggered & Acknowledged).

![](<../.gitbook/assets/using\_mobile\_1 (1).png>)

The **Incident List** holds the ability to filter to view incidents by time. You can do so by using the **filter icon** on the top right corner of the **Incident List** page.

![](../.gitbook/assets/using\_mobile\_2.png)

You can search for specific incidents by using the **search icon** on the top right corner of the page.

![](../.gitbook/assets/using\_mobile\_search\_button.png)

### ![](../.gitbook/assets/using\_mobile\_3.png) <a href="#unique-sound-for-squadcast-push-notifications" id="unique-sound-for-squadcast-push-notifications"></a>

### Unique sound for Squadcast push notifications <a href="#unique-sound-for-squadcast-push-notifications" id="unique-sound-for-squadcast-push-notifications"></a>

All the Squadcast push notifications have a unique sound on both iOS and Android applications to differentiate them from other push notifications.

This should ensure that you get alerted on incidents and it doesn’t get lost in the noise of other push notifications

### Incident Details Page <a href="#incident-details-page" id="incident-details-page"></a>

On the **Incident Details** page, you can take all the actions that are supported on our web app. The page has 4 major sections, namely:

* Details - The Incident details that come in from the incident payload
* Incident Activity Timeline - The Incident Activity Timeline specifies activities, such as Acknowledging or Resolving an Incident, Reassignment of an incident (mentioning both assigned and assignee), Actions that are run and so on.
* Events - The Incidents Events that are deduplicated against the parent incident
* Incident Notes & Starred Notes - All the notes created and starred for the incident

![](../.gitbook/assets/using\_mobile\_4.png)

The **Incident Details** page allows for quick actions:

* Acknowledge - Acknowledge the incident
* Resolve - Resolve the incident
* Reassign - Reassign the incident to a different user
* Respond with Action - Take JIRA or CircleCI actions on an incident enables quick actions (Acknowledge and Resolve), and more options provide reassign and squad actions

#### ****![](../.gitbook/assets/using\_mobile\_5.png)****

#### **Incident Activity Timeline**

The **Incident Activity Timeline** provides all the recorded logs taken against the incident

![](<../.gitbook/assets/using\_mobile\_6 (1).png>)

#### **Incident Notes**

Each incident gets its own notes section. One can @mention users and invite them to collaborate and resolve the incident. When this is done, the mentioned user will receive an email and push notification to inform them of this.

![](<../.gitbook/assets/incident\_notes\_12 (1).png>)

### Notification Rules <a href="#notification-rules" id="notification-rules"></a>

You can configure how you want to receive incident notifications. We support Call, SMS, Email, and Push notifications. You can also choose the order in which any of these notifications should come through.

You can add as many rules as you see fit.

![](../.gitbook/assets/using\_mobile\_8.png)

{% hint style="info" %}
**Note**\
If you **Acknowledge** / **Reassign** / **Resolve** an incident, the system understands that the pending notifications can be stopped. So, you will not receive any further notifications for the incident post this unless it has been reassigned to you again.
{% endhint %}

### Teams <a href="#teams" id="teams"></a>

**Team** lists all users in the organization. Additionally, if the user is on call, there will be a small green dot against the user's avatar.

![](../.gitbook/assets/using\_mobile\_9.png)

You can view any specific user’s profile by clicking on their avatar from the **Team** page. The user profile lists all the user info including the user’s **Notification Rules**, **Schedules**, **Escalation Policies** and **Squads**.

![](../.gitbook/assets/using\_mobile\_10.png)

### Schedules <a href="#schedules" id="schedules"></a>

The **Schedules page** lists all the **Schedules** organized against date and time.

![](<../.gitbook/assets/using\_mobile\_11 .png>)

### SSO login support for mobile apps <a href="#sso-login-support-for-mobile-apps" id="sso-login-support-for-mobile-apps"></a>

We have started supporting SSO login for mobile apps from version 2.8.37 onwards. Read below to know how to make it work on [Android](https://play.google.com/store/apps/details?id=com.squadcast.incidents\&hl=en) & [iOS](https://apps.apple.com/app/id1501689101).

{% hint style="warning" %}
**Important Note**

SSO login for the Mobile app works only if you access your SSO dashboard from your web browser. Login using SSO provider apps is not supported due to limitations imposed by the SSO providers.
{% endhint %}

### SSO Login Flow for Android Application <a href="#sso-login-flow-for-android-application" id="sso-login-flow-for-android-application"></a>

1. Open the Squadcast Mobile App
2. Open your mobile browser and log in to the SSO dashboard from the mobile browser.
3. Click on the Squadcast logo in your SSO dashboard.

That’s it, you will be logged in to the mobile app automatically.

### SSO Login Flow for iOS Application <a href="#sso-login-flow-for-ios-application" id="sso-login-flow-for-ios-application"></a>

1. Open your mobile browser and log in to the SSO dashboard from the mobile browser.
2. Click on the Squadcast logo in your SSO dashboard.

That’s it, you will be logged in to the mobile app automatically.
