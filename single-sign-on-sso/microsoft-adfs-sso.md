---
description: Enable Microsoft ADFS Single Sign On (SSO) for your Squadcast organisation
---

# Microsoft ADFS SSO

Squadcast supports SAML 2.0-based Single **Sign-On** (SSO) login for Microsoft Active Directory users and you can set it for your organisation by following this integration guide.

### Pre-requisites <a href="#pre-requisites" id="pre-requisites"></a>

1. Account Owner / Administrator account in Squadcast
2. A valid Squadcast subscription ([Enterprise](https://www.squadcast.com/pricing))

{% hint style="info" %}
**Points to Note:**

1\. Only an Administrator / Account owner can enable and configure Microsoft ADFS SSO for an organisation in Squadcast.\
\
2\. Once enabled, only the Account owner can use email password-based login by default although it can be configured to enable email-based login for Administrators as well.
{% endhint %}

### Setup Instructions <a href="#setup-instructions" id="setup-instructions"></a>

1. Login to <mark style="color:red;">`app.squadcast.com`</mark> and navigate to the **Settings** > **Extensions**. Click the **Configure** button under SSO.

![](<../.gitbook/assets/sso\_new\_button (2) (1).png>)

2\. In the opened modal, select the **Custom SAML 2.0** tab and click **Show configuration guide for Custom SAML 2.0**.

![](../.gitbook/assets/microsoft\_sso\_new\_1.png)

3\. As given in the displayed guide, copy the **ACS** URL. Then log in to your server and go to <mark style="color:red;">`Server Manager`</mark>.

![](../.gitbook/assets/adfs\_3.png)

4\. Go to <mark style="color:red;">`Tools`</mark> -> <mark style="color:red;">`ADFS Management`</mark>

![](../.gitbook/assets/adfs\_4.png)

5\. Click on <mark style="color:red;">`Add Relying Party Trust`</mark>.

![](../.gitbook/assets/adfs\_5.png)

6\. Select <mark style="color:red;">`Claims Aware`</mark> and click <mark style="color:red;">`Start`</mark>.

7\. Select <mark style="color:red;">`Enter data about the relying party manually`</mark> and click <mark style="color:red;">`Next.`</mark>

![](../.gitbook/assets/adfs\_6.png)

8\. Enter the <mark style="color:red;">`Display name`</mark>. Click <mark style="color:red;">`Next`</mark>.

![](../.gitbook/assets/adfs\_7.png)

9\. Select <mark style="color:red;">`Configure Certificate`</mark> and click <mark style="color:red;">`Next`</mark>.

![](../.gitbook/assets/adfs\_8.png)

10\. Select <mark style="color:red;">`Enable Support for the SAML 2.0 Web SSO protocol`</mark>. Enter the **ACS** URL you copied from Squadcast. Click <mark style="color:red;">`Next`</mark>.

![](../.gitbook/assets/adfs\_9.png)

11\. Paste the **ACS** URL in <mark style="color:red;">`Relying on party trust identifier`</mark>. Click <mark style="color:red;">`Add`</mark>. Then click <mark style="color:red;">`Next`</mark>.

![](../.gitbook/assets/adfs\_11.png)

12\. Select <mark style="color:red;">`Access Control Policy`</mark>. Click <mark style="color:red;">`Next`</mark>.

![](../.gitbook/assets/adfs\_10.png)

13\. In <mark style="color:red;">`Ready to Add Trust`</mark>. Click <mark style="color:red;">`Next`</mark>. Then Click <mark style="color:red;">`Close`</mark>.

![](../.gitbook/assets/adfs\_12.png)

14\. Click <mark style="color:red;">`Edit Claim Insurance Policy`</mark>.

![](../.gitbook/assets/adfs\_13.png)

15\. Click <mark style="color:red;">`Add Rule`</mark>.

16\. Select <mark style="color:red;">`Send LDAP Attributes as Claims`</mark>. Click <mark style="color:red;">`Next`</mark>.

17\. Give a name. Select Attribute Store as <mark style="color:red;">`Active Directory`</mark>. And map **LDAP attributes** to **Outgoing Claim Type** as shown below. Map <mark style="color:red;">`E-Mail-Addresses`</mark> to <mark style="color:red;">`E-Mail Address`</mark>, <mark style="color:red;">`Given-Nam`</mark>`e` to <mark style="color:red;">`Given Name`</mark> and <mark style="color:red;">`Surname`</mark> to <mark style="color:red;">`Surname`</mark> Click <mark style="color:red;">`Ok`</mark>.

![](<../.gitbook/assets/adfs\_14 (1).png>)

18\. Then Click <mark style="color:red;">`Add Rule`</mark>. Select <mark style="color:red;">`Send Claims using Custom Rule`</mark>. Click <mark style="color:red;">`Next`</mark>.

19\. Give a <mark style="color:red;">`Claim rule name`</mark>. And enter the following <mark style="color:red;">`Custom rule`</mark>. Click <mark style="color:red;">`Ok`</mark>.

![](../.gitbook/assets/adfs\_15.png)

```
c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname"]
 => issue(Type = "last_name", Issuer = c.Issuer, OriginalIssuer = c.OriginalIssuer, Value = c.Value, ValueType = c.ValueType);
```

20\. Repeat the Above step and add two more custom rules. Following are the two rules.

![](<../.gitbook/assets/adfs\_16 (1).png>)

```
c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname"]
 => issue(Type = "first_name", Issuer = c.Issuer, OriginalIssuer = c.OriginalIssuer, Value = c.Value, ValueType = c.ValueType);
```

![](<../.gitbook/assets/adfs\_17 (1).png>)

```
c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress"]
 => issue(Type = "email", Issuer = c.Issuer, OriginalIssuer = c.OriginalIssuer, Value = c.Value, ValueType = c.ValueType);
```

{% hint style="info" %}
**Points to Note:**

Make Sure the user accounts to be used for SSO have the first name, last name and email configured.
{% endhint %}

21\. Click <mark style="color:red;">`Apply`</mark>.

22\. In your **ADFS** management dashboard. Go to <mark style="color:red;">`Services->Certificates`</mark>. Select <mark style="color:red;">`Token`</mark>` ```` `<mark style="color:red;">`Signing Certificate`</mark> and Click <mark style="color:red;">`View Certificate`</mark>. Go to <mark style="color:red;">`Details->Copy to Fil`</mark>`e` and export the Der encoded binary X.509 certificate.

![](<../.gitbook/assets/adfs\_18 (3).png>) ![](<../.gitbook/assets/adfs\_19 (3).png>) ![](<../.gitbook/assets/adfs\_20 (1).png>) ![](<../.gitbook/assets/adfs\_21 (3).png>) ![](<../.gitbook/assets/adfs\_22 (3).png>)

23\. Now convert the <mark style="color:red;">`.cer`</mark> file to a <mark style="color:red;">`.pem`</mark> file using the following command in Powershell.

```
openssl x509 -inform der -in certificatename.cer -out certificatename.pem
```

24\. Open the .pem file in a text editor. Copy the contents and paste them into Squadcast under <mark style="color:red;">`X.509 Certificate`</mark>. Then enter the <mark style="color:red;">`Saml 2.0`</mark> Endpoint as \*\*https:///adfs/ls\*\*

{% hint style="info" %}
**Note:**

Make sure to add the **Domain Name** of your Organization, for SSO login to work
{% endhint %}

![](<../.gitbook/assets/microsoft\_sso\_new\_2 (1).png>)

25\. Enable <mark style="color:red;">`SSO`</mark> and click <mark style="color:red;">`Save`</mark>.

26\. ADFS SSO is now configured. To test it you can go to \*\*https:///adfs/ls/idpinitiatedsignon\*\*. Select Your application and sign in with your user account. You will be logged in to Squadcast and a user will be created.

![](../.gitbook/assets/adfs\_24.png) ![](../.gitbook/assets/adfs\_25.png)
