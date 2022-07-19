---
description: >-
  Users can use their G Suite credentials to sign in to Squadcast via Single
  Sign-On (SSO).
---

# Google SSO

This page describes how to add Squadcast to G Suite and configure SSO support with SAML 2.0.

### Connecting Squadcast to G Suite <a href="#connecting-squadcast-to-g-suite" id="connecting-squadcast-to-g-suite"></a>

1. Log in to your <mark style="color:red;">`admin.google.com`</mark> account with your G Suite account
2. Select **Apps** on the main page

![](../.gitbook/assets/google\_1.png)

3\. Select **SAML apps**

![](../.gitbook/assets/google\_2.png)

4\. Create a new application by clicking the “**+**” button and then select **SETUP MY OWN CUSTOM APP**

![](../.gitbook/assets/google\_3.png)

5\. **Download** Certificate, copy **SSO URL** and keep them safe and click **NEXT**

![](../.gitbook/assets/google\_4.png)

6\. Enter the application name as **Squadcast** and optionally provide a description and upload the logo and click **NEXT**

![](../.gitbook/assets/google\_5.png)

7\. Log in to <mark style="color:red;">`app.squadcast.com`</mark> and navigate to its **Settings** > **Extensions**. Click the **Configure** button under SSO and select the Google tab

![](<../.gitbook/assets/google\_sso\_new\_1 (1).png>) ![](<../.gitbook/assets/sso\_new\_button (1) (2).png>)

8\. Click **Show configuration guide for Google** and copy the ACS URL displayed

![](../.gitbook/assets/google\_sso\_new\_2.png)

9\. Go back to the Google custom app and in the Service Provider Details page and paste the copied **ACS URL** in both the **ACS URL** and **Entity ID** fields. Also select **Name ID** as **Basic Information** and **Primary Email** and **Name ID Format** as **EMAIL** and click **Next**

![](../.gitbook/assets/google\_9.png)

10\. In the Attribute Mapping page, click the **ADD NEW MAPPING** button and add the following attributes and click **Finish** and **OK** in the next pop-up

```
Required

first_name |  Basic Information  | First Name
last_name  |  Basic Information  | Last Name
email      |  Basic Information  | Primary Email

Optional - For overwriting the default configured role (choose 1)

role | Custom Attribute | Admin
role | Custom Attribute | User
role | Custom Attribute | Stakeholder
```

By default Squadcast lets you create a user via SSO with a configured default Role ( Admin / User / Stakeholder) in the SSO screen as shown below but it can be overwritten by sending an optional custom field <mark style="color:red;">`role`</mark> and its value along with the above attribute.

{% hint style="info" %}
**Note:**

**Members** trying to log into Squadcast through SSO who aren't already added to the Squadcast platform will be added to the platform by default as **Users**.
{% endhint %}

![](../.gitbook/assets/google\_10.png) ![](../.gitbook/assets/google\_11.png)

11\. Enable the Squadcast application for all users

![](../.gitbook/assets/google\_12.png)

12\. Back in Squadcast, in the previously opened modal:

* Paste the SSO URL we have obtained from Step 5 above in the **SAML 2.0 Endpoint** text box
* Copy the certificate details in the **X.509 Certificate** field
* Enter the domain name of your Organization

{% hint style="info" %}
Make sure to add the **Domain Name** of your Organization, for SSO login to work
{% endhint %}

Configure other options like the default User role and click **Save**

![](../.gitbook/assets/google\_sso\_new\_3.png)

13\. You can allow Account Owners and Admins to also log in using their email credentials in addition to SSO. This can be done by checking the box as shown in the screenshot below

![](../.gitbook/assets/google\_sso\_new\_5.png)

14\. You can enable the toggle button on the top to Enable Google SSO for Squadcast and you are good to go your users will be able to use Google SSO to log in to Squadcast without needing a password\*\*.\*\*

15\. Your users can access SSO from the Google Board

![](../.gitbook/assets/google\_15.png)

{% hint style="info" %}
**Note:**

1. After enabling SSO (step 14), if you are facing **any** issues login using SSO, we advise you to do the following: on the webpage (depending on the browser that is being used), navigate to Inspect -> Application -> Storage -> click **Clear site data**
2. After enabling SSO (step 14), if you see the error `403: no_saml_app` on the browser, we advise you to do the following: on the webpage (depending on the browser that is being used), navigate to Inspect -> Application -> Storage -> click **Clear site data**
{% endhint %}
