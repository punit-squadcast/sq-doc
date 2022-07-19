---
description: Enable Single Sign On (SSO) for your organization with any SAML 2.0 based SSO
---

# SAML 2.0 based SSO

Squadcast supports any SAML 2.0-based Single Sign-On (SSO) and you can set it for your Organisation by following this integration guide.

{% hint style="info" %}
**Points to Note:**

1\. Only an Administrator / Account Owner can enable and configure SAML SSO for an organisation in Squadcast.\
\
2\. Once enabled, only the Account Owner can use \_email-password based login\_ by default although it can be configured to enable email-based login for Administrators as well.
{% endhint %}

### Setup Instructions <a href="#setup-instructions" id="setup-instructions"></a>

1. Login to <mark style="color:red;">`app.squadcast.com`</mark> and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

![](<../.gitbook/assets/sso\_new\_button (4).png>)

2\. Select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**

![](<../.gitbook/assets/saml\_sso\_new\_1 (1).png>)

Now, copy the _ACS URL_ and paste it **into** your SSO provider system

![](../.gitbook/assets/saml\_sso\_new\_2.png)

3\. From your SSO provider’s dashboard, copy the _SAML 2.0 Endpoint_ and _X.509 Certificate_ and paste them into the relevant fields in the Squadcast set-up modal. Configure other options like the _default_ <mark style="color:red;">`User role`</mark>. You can _allow Account Owners and Admins_ to also log in using their email credentials _in addition_ to SSO. This can be done by checking the box as shown in the screenshot below and make sure to click **Save**

![](../.gitbook/assets/saml\_sso\_new\_3.png)

{% hint style="info" %}
**Note:**

Make sure to add the **Domain Name** of your Organization, for SSO login to work
{% endhint %}

4\. You can turn On/Off SSO by _toggling_ the button at the top

![](../.gitbook/assets/saml\_sso\_new\_4.png)

5\. By default, the SSO provider will send _Firstname_, _Lastname_ and _Email ID_ to Squadcast. If you can send a custom key called <mark style="color:red;">`role`</mark> with one of these values <mark style="color:red;">`Admin`</mark>, <mark style="color:red;">`User`</mark> and <mark style="color:red;">`Stakeholder`</mark>, the user will be created with these roles instead of the default user role configured in the SSO modal in Squadcast

Your SSO Integration is good to go and anyone in your Organisation can now use SSO to login into Squadcast.

The following SAML 2.0-based SSO logins were officially tested and found to be working either by our team or the SSO providers but they should work with all SAML 2.0-based SSO providers.

* [Okta](okta-sso.md)
* [Google SSO](google-sso.md)
* [AWS SSO](https://docs.aws.amazon.com/singlesignon/latest/userguide/saasapps.html#saasapps-supported)
* [Citrix ADC SAML SSO](https://docs.citrix.com/en-us/citrix-adc/13/aaa-tm/authentication-methods/saml-authentication/saml-sign-sign-on.html)

This is the officially tested list but any SAML **2.0-based** SSO should work with Squadcast.
