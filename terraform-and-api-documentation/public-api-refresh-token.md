---
description: Generate Refresh token to access Squadcast API
---

# Public API - Refresh Token

This document will walk you through generating an API Refresh token which you can use to call the Squadcast Public API.

The [Squadcast Public API](https://apidocs.squadcast.com/) provides you with the ability to access certain Squadcast features within your account, allowing you to configure users, services, grouping incidents and more to help further reduce noise and speed up response times.

{% hint style="info" %}
**Note:**

We have recently changed the flow of generating a refresh token to access the Squadcast API.
{% endhint %}

In order to use the Squadcast API, you will need to first generate a Refresh token from the Squadcast Web App by following the steps below.

### From Your Profile Page <a href="#from-your-profile-page" id="from-your-profile-page"></a>

1. Move over to the <mark style="color:red;">`My Profile`</mark> page from the top right corner of your screen.
2. In the next window, click on the <mark style="color:red;">`Generate New Token`</mark> button from the <mark style="color:red;">`API Refresh`</mark>` ```` `<mark style="color:red;">`Token`</mark> section.
3. A Refresh token will be generated and displayed. You can use this to generate the Refresh Token and use it to access our public APIs as given in the [Squadcast API documentation](https://apidocs.squadcast.com/).

![](../.gitbook/assets/squadcast\_api\_3.png)

{% hint style="info" %}
You can also Revoke the Refresh token and the associated Access Tokens will also get revoked.
{% endhint %}

{% hint style="warning" %}
Please keep your Refresh Token as safe as your Password.
{% endhint %}

For more details regarding how to use the Squadcast Public APIs, please refer to the [Squadcast API Documentation](https://apidocs.squadcast.com/).

### Account Owner Controls <a href="#account-owner-controls" id="account-owner-controls"></a>

As an Account Owner of a Squadcast organization, you can invoke or revoke refresh tokens for admins and users in your organization.

1. Move over to `Settings` from the left side navigation panel.

{% hint style="info" %}
**Note:** The API Refresh token is role restricted, that is, an API Refresh token created for a <mark style="color:red;">`User`</mark> will only allow User specific controls.\
\
The API Refresh token was created for an <mark style="color:red;">`Admin`</mark> will only provide Admin-specific controls.
{% endhint %}

2\. Click on <mark style="color:red;">`API Tokens`</mark> to view the active API tokens and to create or revoke existing tokens.&#x20;

Click on <mark style="color:red;">`Assign Token To User`</mark> to invoke an API Token for any User or Admin in your organization.

![](../.gitbook/assets/squadcast\_api\_5.png)

3\. Pick the User or Admin from the dropdown menu for whom you want to assign an API Token. You can add more by simply clicking on the <mark style="color:red;">`Assign Token To User`</mark> and following the same process.

![](../.gitbook/assets/squadcast\_api\_6.png)

The assigned token will also be visible to the Users/ Admins on their respective <mark style="color:red;">`My Profile`</mark> pages.

![](../.gitbook/assets/squadcast\_api\_7.png)

{% hint style="warning" %}
Please keep your Refresh Token as safe as your Password
{% endhint %}

Check out the list of available APIs in [Squadcast API Documentation](https://apidocs.squadcast.com/)
