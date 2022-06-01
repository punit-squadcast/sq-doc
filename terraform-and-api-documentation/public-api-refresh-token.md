# Public API - Refresh Token

Generate Refresh token to access Squadcast API

This document will walk you through generating an API Refresh token which you can use to call the Squadcast Public API.

The [Squadcast Public API](https://apidocs.squadcast.com/) provides you the ability to access certain Squadcast features within your account, allowing you to configure users, services, grouping incidents and more to help further reduce noise and speed up response times

In order to use the Squadcast API, you will need to first generate a Refresh token from the Squadcast Web App by following the steps below.

### From Your Profile Page <a href="#from-your-profile-page" id="from-your-profile-page"></a>

1.Move over to the `My Profile` page from the top right corner of your screen.

2.In the next window, click on the `Generate New Token` button from the `API Refresh Token` section.

3.A Refresh token will be generated and displayed. You can use this to generate the Refresh Token and use it to access our public APIs as given in the [Squadcast API documentation](https://apidocs.squadcast.com/).

You can also Revoke the Refresh token and the associated Access Tokens will also get revoked.

🔒Please keep your Refresh Token as safe as your Password.

For more details regarding how to use the Squadcast Public APIs, please refer the [Squadcast API Documentation](https://apidocs.squadcast.com/).

### Account Owner Controls <a href="#account-owner-controls" id="account-owner-controls"></a>

As an Account Owner of a Squadcast organization, you can invoke or revoke refresh tokens for admins and users in your organization.

1.Move over to `Settings` from the left side navigation panel.

2.Click on `API Tokens` to view the active API tokens and to create or revoke existing tokens.

Click on `Assign Token To User` to invoke an API Token for any User or Admin in your organization.

3.Pick the User or Admin from the dropdown menu for whom you want to assign an API Token. You can add more by simple clicking on the `Assign Token To User` and following the same process.

The assigned token will also be visible to the Users/ Admins on their respective `My Profile` pages.

🔒 Please keep your Refresh Token as safe as your Password

Check out the list of available APIs in [Squadcast API Documentation](https://apidocs.squadcast.com/)
