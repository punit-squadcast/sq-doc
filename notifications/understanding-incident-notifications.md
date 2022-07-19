---
description: Understanding the available incident notification channels in Squadcast
---

# Understanding Incident Notifications

Incident notifications represent alert information that is sent to users via the various available channels, which are Push, Email, SMS and Phone calls.

Notifications are sent out only for the incidents created in Squadcast and they cannot be manually created.

You can also choose to be notified of incidents in Squadcast via [Slack](../chatops/slack.md) and [Google Hangouts](../chatops/google-hangouts.md).

{% hint style="warning" %}
**Important:**

**(a)** Only users with [Organization Roles](../manage-users/types-of-users.md) `Account Owner` and `User` receive incident notifications. Users with `Stakeholder` Organization roles will not receive incident notifications. `Stakeholders` can be notified of incidents by using the steps mentioned [here](../incidents-page/incident-notes.md)

**(b)** All users in the Organization have to [verify the email address](../manage-users/add-and-delete-users.md) associated with their Profile in order to start receiving Email and Push notifications for incidents. Also, to receive Push notifications, the latest version of the [Squadcast mobile app](../mobile-app/using-the-mobile-app.md) must be downloaded

**(c)** To receive SMS and Phone call notifications for incidents:

* Users have to [OTP-verify the phone number](../manage-users/manage-your-profile.md) associated with their Profile
* SMS and Phone call notifications must be [enabled](../managing-your-squadcast-account/billing-faqs.md#3.-how-can-i-enable-sms-and-phone-calls-for-my-account) for the Organization
* On the [Free Plan](https://www.squadcast.com/pricing), post the exhaustion of the [free limits](../managing-your-squadcast-account/billing-faqs.md), one-time allowance of 100 notifications (SMS and Phone Calls) for an account, you will stop receiving SMS and Phone call notifications. However, you will still continue to receive Email and Push Notifications.
{% endhint %}

### Notification Phone Numbers <a href="#notification-phone-numbers" id="notification-phone-numbers"></a>

Squadcast uses the following numbers to notify you of incidents.

#### Phone Call Notifications <a href="#phone-call-notifications" id="phone-call-notifications"></a>

**1.** +17076844278

**2.** +17072447799

#### SMS Notifications <a href="#sms-notifications" id="sms-notifications"></a>

**1.** +17076844278

**2.** +17072447799

You can either save the above numbers on your devices or download the below vCard to set up a contact for Squadcast automatically.

\
Download Squadcast vCard

### Notification Details and Logs <a href="#notification-details-and-logs" id="notification-details-and-logs"></a>

Each incident notification can be traced to a source. You can access the Notification Logs for a particular incident by navigating to the [Incident Details](../incidents-page/incidents-details.md) page and clicking on **Notification Logs** in the **Responders** section.

![](../.gitbook/assets/notification\_logs\_1.png)

The Notification Logs for an incident will include:

**(1)** The **user name** of the user

**(2)** The **notification channel** is depicted by an icon followed by the **destination**

The destination for:

* Email notification is the **email address** of the user
* Phone and SMS notification is the **phone number** of the user
* Push notifications on the mobile app is **push**

**(3)** The **status** of the notification

An incident notification can have one of the following statuses:

**(a)** <mark style="color:red;">`scheduled`</mark>: When the notification is scheduled to be sent out from Squadcast

**(b)** <mark style="color:red;">`dispatched`</mark>: When the notification is dispatched from Squadcast and has been accepted by our providers for further delivery

**(c)** <mark style="color:red;">`sent`</mark>: When the notification is dispatched from the providers’ platform to the user

**(d)** <mark style="color:red;">`delivered`</mark>: When the notification has been delivered successfully to the user

**(e)** <mark style="color:red;">`failed`</mark>: When Squadcast is unable to send out the notification

**(f)** <mark style="color:red;">`cancelled`</mark>: When an incident has been acknowledged or resolved, the rest of the scheduled notifications will not be dispatched. The notification status of these notifications will be set to <mark style="color:red;">`cancel`</mark>

{% hint style="info" %}
**Note:**

We have implemented redundancies for each of our notification channels. We will continue to add different providers for each of the notification channels going forward in order to provide maximum reliability for our users.
{% endhint %}

You can get the **time of dispatch** for notifications that are in status <mark style="color:red;">`sent`</mark> or <mark style="color:red;">`delivered`</mark> by hovering over them.

**(4)** The **time** at which the notification was sent (or is yet to be sent)

**(5)** You can click on the refresh icon for the latest data

{% hint style="warning" %}
**Important:**

In some cases, even when notifications might have been _delivered_ to users, the status could still be set to _sent/dispatched_. We depend on our vendors, who in turn depend on hundreds of carriers worldwide, to get notification delivery information. In rare cases, these logs might not be completely reliable. We might have to look further into it to understand certain situations. If you wish to receive more details on the notifications sent out for an incident, you can reach out to our [Support team](mailto:support@squadcast.com) with the `Incident ID` of the incident.
{% endhint %}

{% hint style="info" %}
**Understanding push notifications:**

**(1)** You might see multiple push notifications being scheduled/dispatched if you have logged in to your Squadcast account on multiple mobile devices

**(2)** You will not see any push notifications in the logs if you have not installed and logged into the Squadcast mobile app even though you have push as a notification channel in your notification rule(s)
{% endhint %}

### Bypass Do Not Disturb (DND) for SMS and Phone Call Notifications <a href="#bypass-do-not-disturb-dnd-for-sms-and-phone-call-notifications" id="bypass-do-not-disturb-dnd-for-sms-and-phone-call-notifications"></a>

Bypassing Do Not Disturb is a powerful feature to receive Push, SMS, and Phone call notifciations for incidents even when your phone has the Do Not Disturb mode turned on.

Download the Squadcast vCard to create a contact for Squadcast, then follow the instructions below for mobile devices running on either Android or iOS.

#### Android <a href="#android" id="android"></a>

Once the vCard is downloaded, a contact for Squadcast is created like below.

![](../.gitbook/assets/notifications\_android\_1.png)

**Star this contact** before proceeding further.

**(1)** Head over to **Settings** and navigate to the section that lets you configure **Apps & Notifications** or **Sounds** (each device has this configuration differently)

![](../.gitbook/assets/notifications\_android\_2.png) ![](../.gitbook/assets/notifications\_android\_3.png)

**(2)** On the device we are using as an example, we navigated to the **Do Not Disturb** section

![](../.gitbook/assets/notifications\_android\_4.png)

**(3)** Here, navigate to **Exceptions** and configure the starred **Squadcast** contact to be allowed to notify even when the Do Not Disturb mode is enabled

Even if your Android mobile device is on Do Not Disturb mode, you will now continue to receive SMS and Phone call incident notifications.

#### iOS <a href="#ios" id="ios"></a>

Once the vCard is downloaded, a contact for Squadcast is created like below.

![](<../.gitbook/assets/notifications\_ios\_1 (2).png>)

**(1)** Launch the Contacts app, find the Squadcast contact, and tap **Edit**

![](../.gitbook/assets/notifications\_ios\_2.png)

**(2)** Scroll down until you see entries for **Ringtone** and **Text Tone**. **Emergency Bypass** can be set for each. Tap either **Ringtone** or **Text Tone**

![](../.gitbook/assets/notifications\_ios\_3.png)

**(3)** At the top of the menu, there is an option for **Emergency Bypass**. Toggle it on for each of the desired methods for this contact

![](../.gitbook/assets/notifications\_ios\_4.png)

Even if your iOS mobile device is on Do Not Disturb mode, you will now continue to receive SMS and Phone call incident notifications.

### Bypass Do Not Disturb (DND) for Squadcast Mobile App <a href="#bypass-do-not-disturb-dnd-for-squadcast-mobile-app" id="bypass-do-not-disturb-dnd-for-squadcast-mobile-app"></a>

Users can choose to override the DND settings on their mobile phones and receive critical incident notifications from Squadcast via Push. To do so, in the Squadcast mobile app:

**(1)** Head over to **My Profile**

**(2)** Enable the **Allow Critical Notifications** toggle

![](../.gitbook/assets/notifications\_override\_dnd\_1.png)

On an Android device, follow the steps as indicated below:

**(1)** Tap on **Allow Critical Notifications**

****![](../.gitbook/assets/notifications\_override\_dnd\_5.png)****

**(2)** You will be redirected to the **** app settings page

![](../.gitbook/assets/notifications\_override\_dnd\_6.png)

**(3)** Tap on **Manage Notifications** > **Tap on Incidents**

![](../.gitbook/assets/notifications\_override\_dnd\_7.png)

**(4)** Toggle **Allow notifications when Do not Disturb** on

![](../.gitbook/assets/notifications\_override\_dnd\_8.png)

{% hint style="info" %}
**Note:**

If in case you have declined critical alerts from the pop-up dialogue in the Squadcast iOS app, then you can simply navigate to the settings for the Squadcast app on your mobile device and toggle critical alerts on from there.
{% endhint %}

![](../.gitbook/assets/notifications\_override\_dnd\_2.png)

![](../.gitbook/assets/notifications\_override\_dnd\_3.png)

![](../.gitbook/assets/notifications\_override\_dnd\_4.png)

{% hint style="info" %}
**Note:**

**MIUI and EMUI (Huawei and Xiaomi devices)**

For these particular forks of Android, one may not be able to set sounds from the respective High and Low Urgency Notification Settings. Instead, one may need to perform the following steps additionally:

* Navigate to System Notification Settings
* Make sure High and Low Urgency Notifications are enabled
* From here, tap either High or Low Urgency to choose your sound

**OnePlus Devices**

OnePlus devices running on OS 10 do not fully support Override System Volume. These devices will not always override the system volume when the phone is on silent or vibrate mode.
{% endhint %}

**Important:**

We have tested this feature on most of the iOS and Android devices in the market today. The below tables indicate the behaviour observed:

| iOS            | Normal | DND | Low Volume | Vibrate | Silent |
| -------------- | ------ | --- | ---------- | ------- | ------ |
| Any iOS device | ✓      | ✓   | ✓          | ✓       | ✕      |

| Android | Override DND + Ring | Override DND + Vibrate | Override DND + Silent |
| ------- | ------------------- | ---------------------- | --------------------- |
| Oneplus | ✓                   | ✕                      | ✕                     |
| MIUI    | ✓                   | ✓                      | ✓                     |
| Realme  | ✓                   | ✓                      | ✓                     |
| Pixel   | ✓                   | ✓                      | ✓                     |
| Samsung | ✓                   | ✓                      | ✓                     |

We intend to make this feature work as effectively as possible, as and when the OS will allow us to do so.

### Phone Calls and SMS Support <a href="#phone-calls-and-sms-support" id="phone-calls-and-sms-support"></a>

We use third-party providers to send out SMS and Phone call incident notifications. SMS and Phone call notifications are supported for all the countries across the world except for:

* Cuba
* North Korea

{% hint style="warning" %}
**Important:**

**(1)** **SMS and Phone Notifications to Iran:** While we do send SMS and Phone call incident notifications to users in **Iran**, we cannot assure its 100% deliverability.

**(2)** **SMSs to China:** Incident notification SMSs sent to users of Squadcast in China will contain only the `Incident Title`. Incident URL is not included due to government policies against the presence of any URLs in SMSs. However, users can quickly view and take actions on an incident by using the Squadcast mobile app.
{% endhint %}
