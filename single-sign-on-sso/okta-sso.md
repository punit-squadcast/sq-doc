---
description: Enable Okta Single Sign On (SSO) for your Squadcast organisation
---

# Okta SSO

Squadcast supports SAML 2.0-based Okta Single Sign-On (SSO) login and you can set it for your organisation by following this integration guide.

### Pre-requisites <a href="#pre-requisites" id="pre-requisites"></a>

1. Valid Okta SSO account & subscription
2. Account Owner / Administrator account in Squadcast
3. A valid Squadcast subscription ([Enterprise](https://www.squadcast.com/pricing))

{% hint style="info" %}
**Points to Note:**

1\. Only an Administrator / Account owner can enable and configure Okta SSO for an organisation in Squadcast.\
\
2\. Once enabled, only the Account owner can use email-password-based login by default although it can be configured to enable email-based login for Administrators as well.
{% endhint %}

{% hint style="warning" %}
**Note for Mobile App Users:**

Check out this [documentation](../mobile-app/using-the-mobile-app.md) to log in to your Squadcast Mobile application.
{% endhint %}

### Setting up Okta SSO <a href="#setting-up-okta-sso" id="setting-up-okta-sso"></a>

1. Login to <mark style="color:red;">`app.squadcast.com`</mark> and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

![](<../.gitbook/assets/sso\_new\_button (2) (1).png>)

2\. In the opened modal, select the **Okta** tab and click **Show configuration guide for Okta**.

![](../.gitbook/assets/okta\_sso\_new\_1.png)

3\. Copy the ID highlighted in the instructions.

![](../.gitbook/assets/okta\_sso\_new\_2.png)

4\. Move to your Okta Dashboard and navigate to **Applications**

![](../.gitbook/assets/okta\_4.png)

5\. Search for the **Squadcast** application and click **Add** to add it to your Okta account.

![](../.gitbook/assets/okta\_5.png)

6\. Under the <mark style="color:red;">`Sign-On`</mark> tab, navigate to the <mark style="color:red;">`Advanced Sign-On Settings`</mark> and paste the Customer ID that was copied in Step 3 in the <mark style="color:red;">`Customer ID`</mark> field.

![](../.gitbook/assets/okta\_5\_1.png)

7\. Now click on <mark style="color:red;">`View Setup Instructions`</mark> to view the SAML 2.0 Endpoint and X.509 Certificate.

![](../.gitbook/assets/okta\_6.png)

8\. Paste the SAML 2.0 Endpoint and X.509 Certificates in the respective fields in Squadcast

{% hint style="info" %}
**Note:**

Make sure to add the **Domain Name** of your Organization, for SSO login to work
{% endhint %}

![](../.gitbook/assets/okta\_7\_new.png)

![](../.gitbook/assets/okta\_sso\_new\_3.png)

9\. In Squadcast, enable the toggle above within the modal and click on <mark style="color:red;">`Save`</mark> to enable Okta SSO for your Squadcast Account.

![](../.gitbook/assets/okta\_sso\_new\_4.png)

{% hint style="info" %}
**Note**

You can turn On / Off Okta SSO by toggling the button at the top. Configure other options like the default User role and click Save.
{% endhint %}

{% hint style="warning" %}
**Important**

Members trying to log into Squadcast through SSO who aren't already added to the Squadcast platform will be added to the platform by default as **Users**.
{% endhint %}

10\. The Okta-Squadcast integration also supports user provisioning. To enable that, you can navigate to the <mark style="color:red;">`Assignments`</mark> tab, and assign this to <mark style="color:red;">`people`</mark> or <mark style="color:red;">`groups`</mark> (based on your requirement) to enable access to Squadcast.

![](../.gitbook/assets/okta\_10.png)

In this example, we have chosen <mark style="color:red;">`Assign to People`</mark> and added a user as shown below.

![](../.gitbook/assets/okta\_11.png)

11\. By default, the SSO provider will send Firstname, Lastname and Email ID to Squadcast. If you can send an optional custom key called <mark style="color:red;">`role`</mark> with one of these values <mark style="color:red;">`Admin`</mark>, <mark style="color:red;">`User`</mark> and <mark style="color:red;">`Stakeholder`</mark>, the user will be created with these roles instead of the default user role configured in the SSO modal in Squadcast.

Your Okta SSO Integration is good to go and anyone in your organisation can now use Okta SSO to login into Squadcast.

### Logging into Squadcast via Okta <a href="#logging-into-squadcast-via-okta" id="logging-into-squadcast-via-okta"></a>

1. You can log in to Squadcast by navigating to <mark style="color:red;">`My Apps`</mark> in your Okta Dashboard.

![](../.gitbook/assets/okta\_12.png)

2\. Find <mark style="color:red;">`Squadcast`</mark> in this list of saved applications and just click on the <mark style="color:red;">`Squadcast`</mark> card and you will be automatically directed to your Squadcast account.

![](../.gitbook/assets/okta\_13.png)
