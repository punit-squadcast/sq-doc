# SAML 2.0 based SSO

Enable Single Sign On (SSO) for your organization with any SAML 2.0 based SSO

Squadcast supports any SAML 2.0 based Single Sign On (SSO) and you can set it for your Organisation by following this integration guide.

#### Setup Instructions <a href="#setup-instructions" id="setup-instructions"></a>

**(1)** Login to `app.squadcast.com` and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

**(2)** Select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**

Now, copy the _ACS URL_ and paste it in your SSO provider system

**(3)** From your SSO provider’s dashboard, copy the _SAML 2.0 Endpoint_ and _X.509 Certificate_ and paste it in the relevant fields in the Squadcast set-up modal. Configure other options like the _default_ `User role`. You can _allow Account Owners and Admins_ to also login using their email credentials _in addition_ to SSO. This can be done by checking the box as shown in the screenshot below and make sure to click **Save**

**(4)** You can turn On/Off SSO by _toggling_ the button at the top

**(5)** By default, the SSO provider will send _Firstname_, _Lastname_ and _Email ID_ to Squadcast. If you can send a custom key called `role` with one of these values `Admin`, `User` and `Stakeholder`, the user will be created with these roles instead of the default user role configured in the SSO modal in Squadcast

Your SSO Integration is good to go and anyone in your Organisation can now use SSO to login into Squadcast.

The following SAML 2.0 based SSO logins were officially tested and found to be working either by our team or the SSO providers but it should work with all SAML 2.0 based SSO providers.

* [Okta](https://support.squadcast.com/docs/okta-sso-integration)
* [Google SSO](https://support.squadcast.com/docs/google-sso)
* [AWS SSO](https://docs.aws.amazon.com/singlesignon/latest/userguide/saasapps.html#saasapps-supported)
* [Citrix ADC SAML SSO](https://docs.citrix.com/en-us/citrix-adc/13/aaa-tm/saml-authentication/saml-sign-sign-on.html)

This is the officially tested list but any SAML 2.0 based SSO should work with Squadcast.
