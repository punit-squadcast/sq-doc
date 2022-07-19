---
description: Enable Single Sign-On (SSO) for your Organization with AWS SSO
---

# AWS SSO

Users can use their AWS SSO credentials to sign in to Squadcast via Single Sign-On (SSO).

This page describes how to add Squadcast to AWS SSO Dashboard and configure SSO with SAML 2.0.

{% hint style="info" %}
**Points to Note:**

1\. Only an Account Owner/Administrator can enable and configure SSO for an Organisation in Squadcast.\
\
2\. Once SSO is enabled, only the **Account Owners can use email-password-based login by default**, although it can be configured to allow **Administrators to use enable email-password-based login** as well.
{% endhint %}

### Setup Instructions <a href="#setup-instructions" id="setup-instructions"></a>

**(1)** Login to <mark style="color:red;">`app.squadcast.com`</mark> and navigate to **Settings** > **Extensions**. Click the **Configure** button under SSO.

![](../.gitbook/assets/sso\_new\_button.png)

**(2)** Select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**

![](../.gitbook/assets/aws\_sso\_new\_1.png)

Here, copy the **ACS URL** to use it in your AWS SSO configuration next

![](../.gitbook/assets/aws\_sso\_new\_2.png)

**(3)** In your AWS account, navigate to **AWS Single Sign-On**

From the sidebar, select **Applications**

![](../.gitbook/assets/aws\_sso\_3.png)

**(4)** Click on **Add a new application**

![](../.gitbook/assets/aws\_sso\_4.png)

**(5)** Search for **Squadcast**, select it and click on **Add application**

![](../.gitbook/assets/aws\_sso\_5.png)

**(6)** Next:

* In the _Application Details_ section, provide a suitable **Name** and an optional **Description**

![](../.gitbook/assets/aws\_sso\_6\_a.png)

* In the _Application Metadata_ section, click on **If you do not have a metadata file, you can manually type your metadata values**

![](../.gitbook/assets/aws\_sso\_6\_b\_1.png)

Here, in the placeholders for both **Application ACS URL** and **Application SAML audience**, paste the previously copied ACS URL from Squadcast

![](../.gitbook/assets/aws\_sso\_6\_b\_2.png)

* In the _AWS SSO metadata_ section, copy the **AWS SSO sign-in URL** and download the **AWS SSO certificate**

![](../.gitbook/assets/aws\_sso\_6\_c.png)

* Click on **Save changes**

![](../.gitbook/assets/aws\_sso\_6\_d.png)

**(7)** Back in Squadcast, in the previously opened modal:

* Paste the copied **AWS SSO sign-in URL** under **SAML 2.0 Endpoint**
* Copy the contents of the downloaded **AWS SSO certificate** and paste it under **X.509 Certificate**
* Enter the domain name of your Organization

{% hint style="info" %}
**Note:**&#x20;

Make sure to add the **Domain Name** of your Organization, for SSO login to work
{% endhint %}

* Pick the **Default New User Role** that a newly provisioned user in Squadcast should be assigned by default. This could be either <mark style="color:red;">`User`</mark>, <mark style="color:red;">`Admin`</mark> or <mark style="color:red;">`Stakeholder`</mark>

{% hint style="info" %}
**Note:** If required, the <mark style="color:red;">`User Role`</mark> attribute can be modified manually for users later on from the **Users** page in Squadcast
{% endhint %}

* If you want the Account Owner and/or Admins to be able to login to Squadcast using email-password aside from SSO, enable the checkboxes accordingly
* Click on **Save**

![](../.gitbook/assets/aws\_sso\_new\_3.png)

**(8)** Enable the _toggle_ to activate the SSO integration

![](../.gitbook/assets/aws\_sso\_new\_4.png)

**(9)** Finally, in AWS SSO:

* On the **Applications** page, click on **Squadcast**

![](../.gitbook/assets/aws\_sso\_9\_a.png)

*   Switch to the **Attribute mappings** tab and create mappings as shown in the screenshot below and click on **Save changes**

    If you can send a custom key, <mark style="color:red;">`role`</mark> from here, with one of these values <mark style="color:red;">`Admin`</mark>, <mark style="color:red;">`User`</mark> or <mark style="color:red;">`Stakeholder`</mark>, the new user will be added with these roles instead of the default <mark style="color:red;">`User Role`</mark> configured in Squadcast

![](../.gitbook/assets/aws\_sso\_9\_b.png)

* Switch to **Assigned users** and add your _users_ here

![](../.gitbook/assets/aws\_sso\_9\_c.png)

{% hint style="info" %}
**Note:**

Members trying to login to Squadcast through AWS SSO and are not already added as users of Squadcast, will be added to Squadcast by default with `User Role: User`.n
{% endhint %}

{% hint style="info" %}
**Note:**

By **default**, all new users added to Squadcast via AWS SSO will be added with **`User Role: User`** anyway. You can add an **Attribute Mapping** to provision **all new users** as `Admins` or `Stakeholders` if you wish to do that. In addition to the previous Attribute Mappings, you can add `User Role` as an Attribute Mapping here, in the same manner, and **Save changes**.

* User attribute in the application: role
* Maps to this string value or user attribute in AWS SSO: either `Admin` or `Stakeholder`
* Format: basic

![](../.gitbook/assets/aws\_sso\_11.png)
{% endhint %}

**(10)** From the sidebar, now navigate to **Dashboard**. Here, you will be able to see your **User portal URL** that you can use to login into Squadcast

![](../.gitbook/assets/aws\_sso\_10.png)

That is it, your AWS SSO configuration with Squadcast is now complete!
