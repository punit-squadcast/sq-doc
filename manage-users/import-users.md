---
description: Import users into Squadcast using a .csv file
---

# Import Users

You can import multiple users to your Organization without having to add them manually, one-by-one.

### Steps to Import Users <a href="#steps-to-import-users" id="steps-to-import-users"></a>

1. Click on **Settings** in the sidebar

![](<../.gitbook/assets/add\_and\_delete\_users\_1 (1) (1) (1) (2).png>)

2\. Click on **Users** from the secondary navigation menu

![](<../.gitbook/assets/add\_and\_delete\_users\_2 (1) (3).png>)

3\. Click on **Add Users** on the top right corner

![](<../.gitbook/assets/add\_and\_delete\_users\_3 (1).png>)

* Now, simply import multiple users’ details into the fields using a <mark style="color:red;">`.csv`</mark> file
* To import your <mark style="color:red;">`.csv`</mark> file, you can either drag and drop it on the page or click on the <mark style="color:red;">`select a file from your computer`</mark> on the top of the page

![](../.gitbook/assets/add\_and\_delete\_users\_7.png)

{% hint style="warning" %}
**Important:**

Your `.csv` file should be of the following format:

```csv
first_name,last_name,email,user_type
Todd,Chavez,todd@squadcast.com,stakeholder
Diane,Nguyen,diane@squadcast.com,user
Princess,Carolyn,carolyn@squadcast.com,user
```
{% endhint %}

{% hint style="info" %}
**Note:**

You can skip the `user_type` field if you wish to fill that field later, post the import. By default, the `user_type` chosen will be `User`.
{% endhint %}

### Things to Remember <a href="#things-to-remember" id="things-to-remember"></a>

1. If you have already filled some fields and then choose to merge the <mark style="color:red;">`.csv`</mark> file data with the existing rows, click on the **Continue** button in the modal for confirmation of the same. Once the import is successful, you will see all the user details populated in the list. Click on the **Send Invites** button, on the bottom left, to invite these newly added users to your Organization.
2. The invited user will receive an email for verification. Until the user has been successfully verified, you will notice an icon indicating that <mark style="color:red;">`Verification Is Pending`</mark> against that User.
3. You can choose to resend the verification email by clicking on the <mark style="color:red;">`Verification Is Pending`</mark> icon should that be necessary. Please ensure that you check not only your _Inbox_, but also _Spam_ or _Promotions_ folders to ensure the verification email ended up landing there.
4. You cannot change or transfer the Account Ownership using this _Add Users_ flow. This needs to be done after the users have been imported.
5. If an invalid **User Type** is detected, Squadcast automatically assigns the **User Type** as <mark style="color:red;">`User`</mark> for that particular user.
6. Ensure that there are **no spaces before or after the data in any of the cells, especially for the Email addresses of the users**.
