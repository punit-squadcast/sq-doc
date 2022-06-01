# AWS SSO

Enable Single Sign-On (SSO) for your Organization with AWS SSO

Users can use their AWS SSO credentials to sign in to Squadcast via Single Sign-On (SSO).

This page describes how to add Squadcast in AWS SSO Dashboard and configure SSO with SAML 2.0.

### Setup Instructions <a href="#setup-instructions" id="setup-instructions"></a>

**(1)** Login to `app.squadcast.com` and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

**(2)** Select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**

Here, copy the **ACS URL** to use it in your AWS SSO configuration next

**(3)** In your AWS account, navigate to **AWS Single Sign-On**

From the sidebar, select **Applications**

**(4)** Click on **Add a new application**

**(5)** Search for **Squadcast**, select it and click on **Add application**

**(6)** Next:

* In the _Application Details_ section, provide a suitable **Name** and an optional **Description**
* In the _Application Metadata_ section, click on **If you do not have a metadata file, you can manually type your metadata values**

Here, in the placeholders for both **Application ACS URL** and **Application SAML audience**, paste the previously copied ACS URL from Squadcast

* In the _AWS SSO metadata_ section, copy the **AWS SSO sign-in URL** and download the **AWS SSO certificate**
* Click on **Save changes**

**(7)** Back in Squadcast, in the previously opened modal:

* Paste the copied **AWS SSO sign-in URL** under **SAML 2.0 Endpoint**
* Copy the contents of the downloaded **AWS SSO certificate** and paste it under **X.509 Certificate**
*   Pick the **Default New User Role** that a newly provisioned user in Squadcast should be assigned as by default. This could be either `User`, `Admin` or `Stakeholder`

    **Note:** If required, the `User Role` attribute can be modified manually for users later on from the **Users** page in Squadcast
* If you want the Account Owner and/or Admins to be able to login to Squadcast using email-password aside from SSO, enable the checkboxes accordingly
* Click on **Save**

**(8)** Enable the _toggle_ to activate the SSO integration

**(9)** Finally, in AWS SSO:

* In the **Applications** page, click on **Squadcast**
*   Switch to **Attribute mappings** tab and create mappings as shown in the screenshot below and click on **Save changes**

    If you can send a custom key, `role` from here, with one of these values `Admin`, `User` or `Stakeholder`, the new user will be added with these roles instead of the default `User Role` configured in Squadcast
* Switch to **Assigned users** and add your _users_ in here

**(10)** From the sidebar, now navigate to **Dashboard**. Here, you will be able to see your **User portal URL** that you can use to login to Squadcast

That is it, your AWS SSO configuration with Squadcast is now complete!
