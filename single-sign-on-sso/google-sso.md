# Google SSO

Use G Suite credentials to sign in to Squadcast via Single Sign-On (SSO).

Users can use their G Suite credentials to sign in to Squadcast via Single Sign-On (SSO).

This page describes how to add Squadcast to G Suite and configure SSO-support with SAML 2.0.

### Connecting Squadcast to G Suite <a href="#connecting-squadcast-to-g-suite" id="connecting-squadcast-to-g-suite"></a>

**(1)** Log in to your `admin.google.com` account with your G Suite account

**(2)** Select **Apps** on the main page

**(3)** Select **SAML apps**

**(4)** Create a new application by clicking the “**+**” button and then select **SETUP MY OWN CUSTOM APP**

**(5)** **Download** Certificate, copy **SSO URL** and keep them safe and click **NEXT**

**(6)** Enter the application name as **Squadcast** and optionally provide a description and upload the logo and click **NEXT**

**(7)** Login to `app.squadcast.com` and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO and select the Google tab

**(8)** Click **Show configuration guide for Google** and copy the ACS URL displayed

**(9)** Go back to the Google custom app and in the Service Provider Details page and paste the copied **ACS URL** in both the **ACS URL** and **Entity ID** fields. Also select **Name ID** as **Basic Information** and **Primary Email** and **Name ID Format** as **EMAIL** and click **Next**

**(10)** In the Attribute Mapping page, click the **ADD NEW MAPPING** button and add the following attributes and click **Finish** and **OK** in the next pop-up

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

By default Squadcast lets you create a user via SSO with a configured default Role ( Admin / User / Stakeholder) in the SSO screen as shown below but it can be overwritten by sending an optional custom field `role` and it’s value along with the above attribute.

**(11)** Enable Squadcast application for all users

**(12)** Go back to the Squadcast Google SSO page and paste the SSO URL we have obtained from Step 5 above in the **SAML 2.0 Endpoint** text box and the certificate details in the **X.509 Certificate** field. Configure other options like the default User role and click **Save**

**(13)** You can allow Account owners and Admins to also login using their email credentials in addition to SSO. This can be done by checking the box as shown in the screenshot below

**(14)** You can enable the toggle button on the top to Enable Google SSO for Squadcast and you are good to go and your users will be able to use Google SSO to log in to Squadcast without needing a password

**(15)** Your users can access SSO from the Google Board
