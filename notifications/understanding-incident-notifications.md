# Understanding Incident Notifications

Understanding the available incident notification channels in Squadcast

Incident notifications represent alert information that is sent to users via the various available channels, which are Push, Email, SMS and Phone calls.

Notifications are sent out only for the incidents created in Squadcast and they cannot be manually created.

You can also choose to be notified for incidents in Squadcast via [Slack](https://support.squadcast.com/docs/slack) and [Google Hangouts](https://support.squadcast.com/docs/hangouts).

### Notification Phone Numbers <a href="#notification-phone-numbers" id="notification-phone-numbers"></a>

Squadcast uses the following numbers to notify you for incidents.

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

Each incident notification can be traced to a source. You can access the Notification Logs for a perticular incident by navigating to the [Incident Details](https://support.squadcast.com/docs/incident-details) page and clicking on **Notification Logs** in the **Responders** section.

The Notification Logs for an incident will include:

**(1)** The **user name** of the user

**(2)** The **notification channel** depicted by an icon followed by the **destination**

The destination for:

* Email notification is the **email address** of the user
* Phone and SMS notification is the **phone number** of the user
* Push notifications on the mobile app is **push**

**(3)** The **status** of the notification

An incident notification can have one of the following statuses:

**(a)** `scheduled`: When the notification is scheduled to be sent out from Squadcast

**(b)** `dispatched`: When the notification is dispatched from Squadcast and has been accepted by our providers for further delivery

**(c)** `sent`: When the notification is dispatched from the providers’ platform to the user

**(d)** `delivered`: When the notification has been delivered successfully to the user

**(e)** `failed`: When Squadcast is unable to send out the notification

**(f)** `canceled`: When an incident has been acknowledged or resolved, the rest of the scheduled notifications will not be dispatched. The notification status of these notifications will be set to `canceled`

You can get the **time of dispatch** for notifications that are in status `sent` or `delivered` by hovering over them.

**(4)** The **time** at which the notification was sent (or is yet to be sent)

**(5)** You can click on the refresh icon for the latest data

### Bypass Do Not Disturb (DND) for SMS and Phone Call Notifications <a href="#bypass-do-not-disturb-dnd-for-sms-and-phone-call-notifications" id="bypass-do-not-disturb-dnd-for-sms-and-phone-call-notifications"></a>

Bypassing Do Not Disturb is a powerful feature to receive Push, SMS, and Phone call notifciations for incidents even when your phone has the Do Not Disturb mode turned on.

Download the Squadcast vCard to create a contact for Squadcast, then follow the instructions below for mobile devices running on either Android or iOS.

#### Android <a href="#android" id="android"></a>

Once the vCard is downloaded, a contact for Squadcast is created like below.

**Star this contact** before proceeding further.

**(1)** Head over to **Settings** and navigate to the section that lets you configure **Apps & Notifications** or **Sounds** (each device has this configuration differently)

**(2)** On the device we are using as an example, we navigated to the **Do Not Disturb** section

**(3)** Here, navigate to **Exceptions** and configure the starred **Squadcast** contact to be allowed to notify even when the Do Not Disturb mode is enabled

Even if your Android mobile device is on Do Not Disturb mode, you will now continue to receive SMS and Phone call incident notifications.

#### iOS <a href="#ios" id="ios"></a>

Once the vCard is downloaded, a contact for Squadcast is created like below.

**(1)** Launch the Contacts app, find the Squadcast contact, and tap **Edit**

**(2)** Scroll down until you see entries for **Ringtone** and **Text Tone**. **Emergency Bypass** can be set for each. Tap either **Ringtone** or **Text Tone**

**(3)** At the top of the menu, there is an option for **Emergency Bypass**. Toggle it on for each of the desired methods for this contact

Even if your iOS mobile device is on Do Not Disturb mode, you will now continue to receive SMS and Phone call incident notifications.

### Bypass Do Not Disturb (DND) for Squadcast Mobile App <a href="#bypass-do-not-disturb-dnd-for-squadcast-mobile-app" id="bypass-do-not-disturb-dnd-for-squadcast-mobile-app"></a>

Users can choose to override the DND settings on their mobile phones and receive critical incident notifications from Squadcast via Push. To do so, in the Squadcast mobile app:

**(1)** Head over to **My Profile**

**(2)** Enable the **Allow Critical Notifications** toggle

On an Android device, follow the steps as indicated below:

**(1)** Tap on **Allow Critical Notifications**

**(2)** You will be redirected to app settings page

**(3)** Tap on **Manage Notifications** > **Tap on Incidents**

**(4)** Toggle **Allow notifications when Do not Disturb** on

**Note:**

If in case you have declined critical alerts from the pop-up dialog in the Squadcast iOS app, then you can simply navigate to the settings for the Squadcast app on your mobile device and toggle critical alerts on from there.

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

We use third party providers to send out SMS and Phone call incident notifications. SMS and Phone call notifications are supported for all the countries across the world except for:

* Cuba
* North Korea
