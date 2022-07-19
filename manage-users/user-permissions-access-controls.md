---
description: Organization-level Access Controls within your Account
---

# User Permissions - Access Controls

Once you have onboarded users into your Organization, you can customize their accesses to the account by adding additional permissions. These are an additional level of permissions, on top of the _User Type_ that they have been added as.

### Organization-level Permissions <a href="#organization-level-permissions" id="organization-level-permissions"></a>

The below Organization-level entities can be managed by enabling the checkboxes against the users:

1. Users
2. Teams
3. API Tokens
4. Extensions
5. Postmortem Templates
6. Billing

![](../.gitbook/assets/user\_permissions\_access\_controls\_1.png)

### Understanding Organization Level Permissions <a href="#understanding-organization-level-permissions" id="understanding-organization-level-permissions"></a>

These Organization Level specific entity permissions can be assigned only to <mark style="color:red;">`Account Owners`</mark> and <mark style="color:red;">`Users`</mark>.

| Permission Type             | What it means                                             | User Types who can be assigned these |
| --------------------------- | --------------------------------------------------------- | ------------------------------------ |
| Manage Users                | Add, Delete users                                         | Account Owner, User                  |
| Manage Teams                | Create Teams                                              | Account Owner, User                  |
| Manage API Tokens           | Create, Revoke API Tokens for all users                   | Account Owner, User                  |
| Manage Extensions           | Enable, Disable Extensions                                | Account Owner, User                  |
| Manage Postmortem Templates | Create & Modify Templates, set Default Template           | Account Owner, User                  |
| Access and manage Billing   | Access, Manage Billing and Card Details in Billing Portal | Account Owner, User                  |

{% hint style="warning" %}
**Important:**

* `Account Owners` have all of these permissions by default.
* You cannot assign any permissions to a `Stakeholder` type of user by default.
{% endhint %}
