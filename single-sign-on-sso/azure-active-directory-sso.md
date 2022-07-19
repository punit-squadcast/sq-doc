---
description: >-
  Enable Azure Active Directory Single Sign-On (SSO) for your Squadcast
  Organisation
---

# Azure Active Directory SSO

Squadcast supports SAML 2.0-based Single Sign-On (SSO) login for Azure Active Directory users. You can integrate your Squadcast Organization with your Azure Active Directory SSO by following this integration guide.

#### Pre-requisites <a href="#pre-requisites" id="pre-requisites"></a>

1. Account Owner / Administrator account in Squadcast
2. A valid Squadcast subscription in either ([Pro or Enterprise plans](https://www.squadcast.com/pricing))

{% hint style="info" %}
**Point to Note:**

1\. Only an Administrator / Account owner can enable and configure Azure Active Directory SSO for an Organisation in Squadcast.\
\
2\. Once enabled, only the Account Owner can use email-password-based login **by default** although, it can be configured to enable email-password-based login for Administrators as well.
{% endhint %}

#### Setup Guide <a href="#setup-guide" id="setup-guide"></a>

**(1)** Login to <mark style="color:red;">`app.squadcast.com`</mark> and navigate to **Settings** > **Extensions**. Click the **Configure** button under SSO.

![](<../.gitbook/assets/sso\_new\_button (2).png>)

**(2)** In the opened modal, select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**

![](../.gitbook/assets/azure\_sso\_new\_1.png)

As given in the displayed guide, copy the **ACS URL** being shown in point 1

![](../.gitbook/assets/azure\_sso\_new\_2.png)

**(3)** Then, go to your Azure Active Directory dashboard and click on **Enterprise applications** from the left navigation

![](../.gitbook/assets/azure\_squadcast\_4.png)

**(4)** Click on **New Application** to create an application for Squadcast

![](../.gitbook/assets/azure\_squadcast\_5.png)

**(5)** Select **Non-gallery Application**, give a name for the application (such as, _Squadcast_) and click on **Add**

![](../.gitbook/assets/azure\_squadcast\_6.png)

**(6)** For the newly created app, in the left pane under **Manage**, select **Users and groups**

![](../.gitbook/assets/azure\_squadcast\_7.png)

Now, click on **Add User**

![](../.gitbook/assets/azure\_squadcast\_8.png)

**(7)** Find and add the users you want to, along with the appropriate **Role**

![](../.gitbook/assets/azure\_squadcast\_9.png)

**(8)** In the left pane under **Manage**, click **Single sign-on** and select **SAML**

![](../.gitbook/assets/azure\_squadcast\_10.png)

**(9)** Edit the **Basic SAML Configuration** section

In both, the **Identifier (Entity ID)** and **Reply URL (Assertion Consumer Service URL)** placeholders, paste the **ACS URL** you copied previously from Squadcast in here

![](../.gitbook/assets/azure\_squadcast\_11.png)

**(10)** Next, edit the **User and Attributes Claims** section

![](../.gitbook/assets/azure\_squadcast\_12.png)

Remove the _namespace_ and use:

* <mark style="color:red;">`first_name`</mark> for source attribute <mark style="color:red;">`user.givenname`</mark>
* <mark style="color:red;">`email`</mark> for <mark style="color:red;">`user.mail`</mark>
* <mark style="color:red;">`last_name`</mark> for <mark style="color:red;">`user.surname`</mark>

![](../.gitbook/assets/azure\_squadcast\_13.png) ![](../.gitbook/assets/azure\_squadcast\_14.png) ![](../.gitbook/assets/azure\_squadcast\_15.png)

**(11)** Click on the **Edit** icon in the **SAML Signing Certificate** section

![](../.gitbook/assets/azure\_squadcast\_20.png)

Here, **download the PEM certificate**

![](../.gitbook/assets/azure\_squadcast\_16.png)

**(12)** From under the **Set up Squadcast** section, copy the **Login URL**

![](../.gitbook/assets/azure\_squadcast\_17.png)

**(13)** Back in Squadcast, in the previously opened modal:

* Paste the copied **Login URL** in the placeholder for **SAML 2.0 Endpoint**
* Copy the contents of the **PEM Certificate** in the placeholder for **X.509 Certificate**
* Enter the domain name of your Organization

{% hint style="info" %}
**Note:**&#x20;

Make sure to add the **Domain Name** of your Organization, for SSO login to work
{% endhint %}

* Provisioning new users can default to a particular <mark style="color:red;">`User Role`</mark> from the drop-down
* You can allow <mark style="color:red;">`Account Owners`</mark> and <mark style="color:red;">`Admins`</mark> to also log in using their email credentials in addition to SSO. This can be done by checking the boxes for those options
* You can simply _provision new users on their first log in_ by enabling the checkbox for the same

Once all of this has been configured based on your requirements, click on **Save**

****

**(14)** That’s it, your configuration is now complete!

For testing this SSO integration and if it's working as expected, go back to the Azure Active Directory SSO portal, and click on **Test**

Then, click **Sign in as a current user** to verify your login to Squadcast!

![](../.gitbook/assets/azure\_squadcast\_19.png)

**(15)** Activate this SSO integration by _enabling the toggle_

![](../.gitbook/assets/azure\_sso\_new\_4.png)

**(16)** To login to Squadcast via Azure Active Directory SSO from here on, **within your Office 365 account, click on App Launcher, click on All Apps and you will be able to see Squadcast** there. Unless you have enabled email-password based login for your User Role, you will not be able to login to Squadcast using email-password from our [webapp login page](https://app.squadcast.com/).

{% hint style="info" %}
**Logging in from the Squadcast mobile app when Azure AD SSO is enabled:**

The user needs to first access and login to [myapplications.microsoft.com](https://support.squadcast.com/docs/myapplications.microsoft.com) in the mobile browser. Here, they will be able to see the configured SSO (for Squadcast, as shown in the screenshot below). They can simply click on the icon to _log in_.

![](../.gitbook/assets/azure\_squadcast\_22.png)
{% endhint %}

{% hint style="warning" %}
**Important:**

**(1)** We do not support provisioning and syncing of **Groups** from Azure AD SSO into Squadcast. We support this only for **Users**.

**(2)** To login to the Squadcast web app when Azure AD SSO is enabled, users can use **My Apps Secure Sign-in Extension** for an easy login.
{% endhint %}
