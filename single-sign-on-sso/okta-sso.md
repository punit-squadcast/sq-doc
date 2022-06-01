# Okta SSO

Enable Okta Single Sign On (SSO) for your Squadcast organisation

Squadcast supports SAML 2.0 based Okta Single Sign On (SSO) login and you can set it for your organisation by following this integration guide.

### Pre-requisites <a href="#pre-requisites" id="pre-requisites"></a>

1. Valid Okta SSO account & subscription
2. Account Owner / Administrator account in Squadcast
3. A valid Squadcast subscription ([Enterprise](https://www.squadcast.com/pricing))

### Setting up Okta SSO <a href="#setting-up-okta-sso" id="setting-up-okta-sso"></a>

**(1)** Login to `app.squadcast.com` and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

**(2)** In the opened modal, select the **Okta** tab and click **Show configuration guide for Okta**.

**(3)** Copy the ID highlighted in the instructions.

**(4)** Move to your Okta Dashboard and navigate to **Applications**

**(5)** Search for **Squadcast** application and click **Add** to add it to your Okta account.

**(6)** Under the `Sign-On` tab, navigate to the `Advanced Sign-On Settings` and paste the Customer ID that was copied in Step 3 in the `Customer ID` field.

**(7)** Now click on `View Setup Instructions` to view the SAML 2.0 Endpoint and X.509 Certificate.

**(8)** Paste the SAML 2.0 Endpoint and X.509 Certificates in the respective fields in Squadcast

**(9)** In Squadcast, enable the toggle above within the modal and click on `Save` to enable Okta SSO for your Squadcast Account.

**(10)** The Okta-Squadcast integration also supports user provisioning. To enable that, you can navigate to the `Assignments` tab, assign this to `people` or `groups` (based on your requirement) to enable access to Squadcast.

In this example, we have chosen `Assign to People` and added a user as shown below.

**(11)** By default, the SSO provider will send Firstname, Lastname and Email ID to Squadcast. If you can send an optional custom key called `role` with one of these values `Admin`, `User` and `Stakeholder`, the user will be created with these roles instead of the default user role configured in the SSO modal in Squadcast.

Your Okta SSO Integration is good to go and anyone in your organisation can now use Okta SSO to login into Squadcast.

### Logging into Squadcast via Okta <a href="#logging-into-squadcast-via-okta" id="logging-into-squadcast-via-okta"></a>

**(1)** You can login to Squadcast by navigating to `My Apps` in your Okta Dashboard.

**(2)** Find `Squadcast` in this list of saved applications and just click on the `Squadcast` card and you will be automatically directed into your Squadcast account.
