# Azure Active Directory SSO

Enable Azure Active Directory Single Sign-On (SSO) for your Squadcast Organisation

Squadcast supports SAML 2.0 based Single Sign-On (SSO) login for Azure Active Directory users. You can integrate your Squadcast Organization with your Azure Active Directory SSO by following this integration guide.

#### Pre-requisites <a href="#pre-requisites" id="pre-requisites"></a>

1. Account Owner / Administrator account in Squadcast
2. A valid Squadcast subscription in either ([Pro or Enterprise plans](https://www.squadcast.com/pricing))

#### Setup Guide <a href="#setup-guide" id="setup-guide"></a>

**(1)** Login to `app.squadcast.com` and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

**(2)** In the opened modal, select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**

As given in the displayed guide, copy the **ACS URL** being shown in point 1

**(3)** Then, go to your Azure Active Directory dashboard and click on **Enterprise applications** from the left navigation

**(4)** Click on **New Application** to create an application for Squadcast

**(5)** Select **Non-gallery Application**, give a name for the application (such as, _Squadcast_) and click on **Add**

**(6)** For the newly created app, in the left pane under **Manage**, select **Users and groups**

Now, click on **Add User**

**(7)** Find and add the users you want to, along with the appropriate **Role**

**(8)** In the left pane under **Manage**, click **Single sign-on** and select **SAML**

**(9)** Edit the **Basic SAML Configuration** section

In both, the **Identifier (Entity ID)** and **Reply URL (Assertion Consumer Service URL)** placeholders, paste the **ACS URL** you copied previously from Squadcast in here

**(10)** Next, edit the **User and Attributes Claims** section

Remove the _namespace_ and use:

* `first_name` for source attribute `user.givenname`
* `email` for `user.mail`
* `last_name` for `user.surname`

**(11)** Click on the **Edit** icon in the **SAML Signing Certificate** section

Here, **download the PEM certificate**

**(12)** From under the **Set up Squadcast** section, copy the **Login URL**

**(13)** Paste the copied **Login URL** in the placeholder for **SAML 2.0 Endpoint** and the contents of the **PEM Certificate** in the placeholder for **X.509 Certificate**

* Provisioning new users can be defaulted to a particular `User Role` from the drop-down
* You can allow `Account Owners` and `Admins` to also login using their email credentials in addition to SSO. This can be done by checking the boxes for those options
* You can simply _provision new users on their first login_ by enabling the checkbox for the same

Once all of this have been configured based on your requirements, click on **Save**

**(14)** That’s it, your configuration is now complete!

For testing this SSO integration and if its working as expected, go back to the Azure Active Directory SSO portal, and click on **Test**

Then, click **Sign in as current user** to verify your login to Squadcast!

**(15)** Activate this SSO integration by _enabling the toggle_

**(16)** To login to Squadcast via Azure Active Directory SSO from here on, **within your Office 365 account, click on App Launcher, click on All Apps and you will be able to see Squadcast** there. Unless you have enabled email-password based login for your User Role, you will not be able to login to Squadcast using email-password from our [webapp login page](https://app.squadcast.com/).
