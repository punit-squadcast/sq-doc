# Using the Mobile App

This document briefly explains all that you can do on our native mobile application available for both iOS and Android.

You can use our mobile app to Acknowledge, Reassign, take Actions, and Resolve from the mobile app. You can also view who is on-call from the Schedules Tab. The mobile app will walk you into the **Incident List** view where you will be able to view incidents organized by Incident status, that is, Triggered, Acknowledged and Resolved.

#### Incident List <a href="#incident-list" id="incident-list"></a>

Once you are logged into the application, you will be navigated to the **Incident List** page. Incidents are organized according to incident status. In the tab above, you will be able to view the number of incidents in the open state (Triggered & Acknowledged).

The **Incident List** holds the ability to filter to view incidents by time. You can do so by using the **filter icon** on the top right corner of the **Incident List** page.

You can search for specific incidents by using the **search icon** on the top right corner of the page.

#### Unique sound for Squadcast push notifications <a href="#unique-sound-for-squadcast-push-notifications" id="unique-sound-for-squadcast-push-notifications"></a>

All the Squadcast push notifications have a unique sound on both iOS and Android applications to differentiate from other push notifications.

This should ensure that you get alerted on incidents and it doesn’t get lost in the noise of other push notifications

#### Incident Details Page <a href="#incident-details-page" id="incident-details-page"></a>

On the **Incident Details** page, you can take all the actions that are supported on our web app. The page has 4 major sections, namely:

* Details - The Incident details that come in from the incident payload
* Incident Activity Timeline - The Incident Activity Timeline specifies activities, such as Acknowledging or Resolving an Incident, Reassignment of an incident (mentioning both assigned and assignee), Actions that are run and so on.
* Events - The Incidents Events that are deduplicated against the parent incident
* Incident Notes & Starred Notes - All the notes created and starred for the incident

The **Incident Details** page allows for quick actions:

* Acknowledge - Acknowledge the incident
* Resolve - Resolve the incident
* Reassign - Reassign the incident to a different user
* Respond with Action - Take JIRA or CircleCI actions on an incident enables quick actions (Acknowledge and Resolve), and more options provide reassign and squad actions

**Incident Activity Timeline**

The **Incident Activity Timeline** provides all the recorded logs taken against the incident

**Incident Notes**

Each incident gets its own notes section. One can @mention users and invite them to collaborate and resolve the incident. When this is done, the mentioned user will receive an email and push notification to inform them of this.

#### Notification Rules <a href="#notification-rules" id="notification-rules"></a>

You can configure how you want to receive incident notifications. We support Call, SMS, Email, and Push notifications. You can also choose the order in which any of these notifications should come through.

You can add as many rules as you see fit.

#### Teams <a href="#teams" id="teams"></a>

**Team** lists all users in the organization. Additionally, if the user is on call, there will be a small green dot against the user avatar.

You can view any specific user’s profile by clicking on their avatar from the **Team** page. User profile lists all the user info including the user’s **Notification Rules**, **Schedules**, **Escalation Policies** and **Squads**.

#### Schedules <a href="#schedules" id="schedules"></a>

**Schedules** page lists all the **Schedules** organized against date and time.

#### SSO login support for mobile apps <a href="#sso-login-support-for-mobile-apps" id="sso-login-support-for-mobile-apps"></a>

We have started supporting SSO login for mobile apps from version 2.8.37 onwards. Read below to know how to make it work on [Android](https://play.google.com/store/apps/details?id=com.squadcast.incidents\&hl=en) & [iOS](https://apps.apple.com/app/id1501689101).

#### SSO Login Flow for Android Application <a href="#sso-login-flow-for-android-application" id="sso-login-flow-for-android-application"></a>

1. Open the Squadcast Mobile App
2. Open your mobile browser and login to the SSO dashboard from the mobile browser.
3. Click on the Squadcast logo in your SSO dashboard.

That’s it, you will be logged in to the mobile app automatically.

#### SSO Login Flow for iOS Application <a href="#sso-login-flow-for-ios-application" id="sso-login-flow-for-ios-application"></a>

1. Open your mobile browser and login to the SSO dashboard from the mobile browser.
2. Click on the Squadcast logo in your SSO dashboard.

That’s it, you will be logged in to the mobile app automatically.
