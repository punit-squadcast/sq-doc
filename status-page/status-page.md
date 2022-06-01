# Status Page

Let your customers know how your Services are doing, without them having to ask you about it

### What is a Status Page? <a href="#what-is-a-status-page" id="what-is-a-status-page"></a>

One of the core principles of SRE is _Transparency_ and Status Pages help you communicate the status of your Services to your customers at all times, as opposed to you getting to know the status of your Services through support tickets logged by your customers.

Squadcast’s Status Page can be used to configure and display Services and dependent Services along with their real-time statuses updated directly, all from within the platform.

### Working of a Status Page <a href="#working-of-a-status-page" id="working-of-a-status-page"></a>

Whenever the displayed Service has an open incident (an incident in the `Triggered` or `Acknowledged` state), its status automatically changes to the status equivalent of _Degraded (Bad)_. When the incident gets resolved, the status of the displayed Service goes back to being _Operational (Good)_ or its equivalent status. When Services undergo maintenance, the status of those Services are changed to _Under Maintenance_.

For an incident, you can choose to post updates of its status directly from its [Incident Details](https://support.squadcast.com/docs/incident-details) page using the [Update Status Page](broken-reference) option.

You can also display dependent Services in the Status Page. First, configure the [dependencies between your Services](https://support.squadcast.com/docs/service-dependency-based-deduplication#adding-a-service-dependency) and then, add them to the Status Page.

You can configure the [visual themes](broken-reference) and the [terminologies](broken-reference) for Operational (Good) and Degraded (Bad).

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have the necessary permissions to create and manage Status Pages
* Services must be created prior to configuring a Status Page

### Creating a Status Page <a href="#creating-a-status-page" id="creating-a-status-page"></a>

Ensure that the right Team is selected from the team picker at the top of the screen.

**(1)** Navigate to **Status Page** from the sidebar

**(2)** Click on the **Add Status Page** button

**(3 a)** **Page Configuration**

* Give your Status Page a **Name**
* Enter the **Page Hostname** (eg: status.yourcompany.com or www.yourcompanystatus.com) where you want to host the Status Page
* Copy the `CNAME` information
* Click on **Save & Next** button

**(3 b)** **Service Configuration**

* Select the Services which you want to display in your Status Page and provide a suitable _Alias_ for them
* You can also enable the checkbox **Select all services** to display your entire list of Services in your Team on the Status Page
* Click on **Save & Create** to create the Status Page

**Note:** If the selected Service is dependent on other Services, then its dependent Services will also automatically be displayed in the Status Page.

### Setting CNAME record <a href="#setting-cname-record" id="setting-cname-record"></a>

When you try to view your Status Page by clicking on the Status Page or by visiting the `Page Hostname`, it will not be visible.

You would have to first add a CNAME record in your DNS Provider for the Page Hostname and point it to `status.squadcast.io`.

**Note**: This step is necessary for you to complete irrespective of whether you are looking to have a [Public Status Page or a Private Status Page](broken-reference).

Once, the CNAME record has been added successfully, you can view the Status Page by clicking on its name from the **Status Page** tab.

You will be able to view your Status Page like shown in the image below.

### Customizing your Status Page <a href="#customizing-your-status-page" id="customizing-your-status-page"></a>

You can upload a _Logo_ and change the default _System Status_ texts by clicking on **Edit** and selecting **Header**.

Here, you can upload a logo for your Status Page and provide custom text for your Status Page. When all your displayed Services are healthy - Good Status (eg: Operational, All good!, etc.) and for when even one of your displayed Services have an incident - Bad Status (eg: Degraded, Oops.., Something is wrong, etc). There is another status, indicating when a Service is under maintenance - Under Maintenance Status.

This _status_ will update the Status Page’s overall _status_ in the _header_ section accordingly.

#### Configuring Service Status <a href="#configuring-service-status" id="configuring-service-status"></a>

You can also configure the Service Status _text_ and the _representation colours_ by clicking on **Edit** and selecting **Service Status**.

Here, you can customize the _text to be displayed for the `Service Status`_ on the right, and you can edit the _representation colours_ on the left by clicking on the `colour` option. You can also enter your own choice of colour by providing the HEX value for that colour.

**Note**: You can see the changes reflecting in your screen by refreshing the screen.

#### Changing the colour theme <a href="#changing-the-colour-theme" id="changing-the-colour-theme"></a>

You can edit the _colour theme_ of your Status Page by clicking on **Edit** and selecting **Theme**.

Then you can pick the colour of your choice from the visual colour picker or provide the colour values in either `HEX`, `RGBA` or `HSLA` formats, and then click the **Save** button.

You can see the changes reflecting as shown below.

### Types of Status Page <a href="#types-of-status-page" id="types-of-status-page"></a>

#### Public Status Page <a href="#public-status-page" id="public-status-page"></a>

Now that you are done with all the customizations, it’s time to make the Status Page `public`, so all your customers/stakeholders/members of other Teams in your Organization/end users can view it.

To make a Status Page `public`, go to **Edit** and check the **Make Public** check box as shown below.

Now, anyone can publicly view the status page using the Public URL (Hostname URL), in this case, https://status.poniesareaweso.me.

#### Private Status Page <a href="#private-status-page" id="private-status-page"></a>

If you do not check the **Make Public** box in the **Edit** dropdown, your Status Page will be `Private` to the **members of your Team only**.

**Note:**

* To access a Private Status Page, you can either click on the **Name** of the Status Page or click on the **Hostname URL** for the Status Page and view the Status Page.
* You can also share the Squadcast URL (indicated by the green box) of the Private Status Page with members of your Team to easily access the Status Page (with an added user login step, if they are not already logged in to Squadcast)

Whenever there is an incident for a displayed Service, that status of the Service will be marked as Degraded/Bad. You can post updates to the Status Page for the incident with **different statuses**.

For a first update, you can add a status such as `Acknowledged`, `Investigating` and add relevant information in the **Description**.

### Posting Incident Updates to your Status Page <a href="#posting-incident-updates-to-your-status-page" id="posting-incident-updates-to-your-status-page"></a>

Whenever there is an incident for a displayed Service, that status of the Service will be marked as Degraded/Bad. You can post updates to the Status Page for the incident with **different statuses**.

For a first update, you can add a status such as `Acknowledged`, `Investigating` and add relevant information in the **Description**.

As the incident state progresses, you can continue to post updates for its status like `Identified`, `Fix deployed`, `Resolved`, etc., and accompany it with relevant **Description**.

In order to do this, go to the [Incident Details page](https://support.squadcast.com/docs/incident-details) for the incident. Click on the three dots on the top right of the incident and click on **Update Status Page**.

In the **Update Status Page** modal, enter the **Custom Status** and **Custom Description**, select the Status Page to which you want to post the update and click on the **Update** button.

These updates will be reflected in the selected Status Page under **Incident History**.

#### Adding Attachments <a href="#adding-attachments" id="adding-attachments"></a>

You can add a variety of file types as an attachment to the Status Page update for an incident.

To attach a file, drag and drop the file to the markdown editor. You can also copy-paste the file directly in the markdown editor.

The maximum size for a single single file is 10 MB (for upload). You can upload a maximum of 5 files at a time.

The storage limit for an organization depends on the plan:

* For Free plan - the limit is 50 MB
* For Pro and Enterprise plans - the limit is unlimited

File uploads won’t work if the plan limit has been reached. File once uploaded cannot be deleted.

The supported file types are:

* Images (.png, .jpg, .jpeg)
* Word Processors (.doc, .docx, .odt, pages)
* Spreadsheets (.xls, .xlsx, numbers)
* PDFs (.pdf)
* Presentations (.ppt, .pptx. .odp)
* Miscellaneous (.log, .txt, .odv, .csv, key, json, log)

#### Edit Status Page Messages <a href="#edit-status-page-messages" id="edit-status-page-messages"></a>

You can edit the message updates posted on the Status Page.

**(1)** Navigate to the **Status Page** from the sidebar

**(2)** Click on the **Status Page** you want to update

You will find the icons to edit or delete a message to the right of the message posted.

**(3)** Click on the **Edit** icon to edit the update. Make the necessary changes and click on the **Save** button

The edited message will be reflected under the Incident History.

#### Delete Status Page Message <a href="#delete-status-page-message" id="delete-status-page-message"></a>

You can delete the message updates previously posted on the Status Page.

**(1)** Click on the **Delete** icon to delete the message

**(2)** Click on the **Delete** button again to confirm

These updates will be reflected under the Incident History. The deleted message will be displayed as _‘This update was deleted’_.

Here is how the updated status messages look in the public Status Page.

### Enable Subscriptions to your Status Page <a href="#enable-subscriptions-to-your-status-page" id="enable-subscriptions-to-your-status-page"></a>

To enable subscriptions to your Status Page, go to **Edit**, click on **Subscriptions** and check the **Enable Subscriptions** checkbox. **Subscribe** option will now show up on your public Status Page. You can have your end users **subscribe** for incident update notifications from the Status Page.

You can select the **modes of subscription** you want to enable for your Status Page. You can select either or both the available options. Additionally, you can select the type of notifications that get sent to your subscribers, **Incident Updates**, **Maintenance**, or both.

The available modes are:

**1. Email:**

You can add a suitable text on the sender’s email address text box from which all the subscribed users will receive Status Page incident update notifications. In this case, all the subscribed users will get mails from ‘\[email protected]’.

On the Status Page itself, you will now notice a placeholder to enter Email addresses like shown below. A _confirmation/verification_ Email is sent to the added Email address. Post the confirmation/verification completion, incident update notifications will be sent out.

**2. Webhook:**

You can subscribe to receive incident update notifications via Webhooks as well. You can also enter an email address which gets notified when the endpoint fails.

The payload format of the Webhook is as follows:

```
{
  "metadata": {
    "unsubscribe_link": "<link_to_unsubscribe_from_webhook_alerts>"
  },
  "page_configuration": {
    "status_page_url": "<url_of_status_page_to_which_you've_subscribed>",
    "status": "<the_current_status>",
    "message": "<more_details_on_the_status>",
    "updated_at": "<time_at_which_status_updated>"
  },
  "updates": [{
    "status": "<status_of_corresponding_update>",
    "message": "<message_corresponding_update>",
    "updated_at": "<time_of_corresponding_update>"
  }]
}
```

### FAQs <a href="#faqs" id="faqs"></a>

#### Please refer to the Frequently Asked Questions below that might help you fix any issues/answer your queries. <a href="#please-refer-to-the-frequently-asked-questions-below-that-might-help-you-fix-any-issuesanswer-your-q" id="please-refer-to-the-frequently-asked-questions-below-that-might-help-you-fix-any-issuesanswer-your-q"></a>

**1. I am looking to have a public Status Page, I have most likely configured everything, yet when I access the Hostname URL, the Status Page does not load. Am I missing anything?**

Please ensure that you have made your Status Page `Public`. Without [enabling this checkbox](broken-reference), your Status Page would be private and hence, not accessible via the Hostname URL.

**2. I have confirmed that my Status Page is made Public and have added the CNAME record which is pointing to status.squadcast.io, yet I am unable to access the Status Page at the said Page Hostname**

There could be various reasons for the same.

* There could be a DNS propagation delay. You might be able to access the Status Page from machines in certain regions of the world, while it would fail in the rest. In this case, it is recommended to wait for 48 hours from the time the last DNS changes were made.
* There could be a DNS caching issue at your end (For example, your router, your system’s local resolver cache, etc.). In this case, it is recommended to wait for sometime, generally a few hours, from the time the last changes were made.

If neither is applicable to you, kindly reach out to us for further assistance.

**3. Even after making our Status Page public, when we try accessing the Hostname URL, we are redirected to Squadcast. What can we do to fix this?**

If your Public Status Page is being redirected to your Squadcast account even after making it `Public`, please clear your application cache and try again. You may also additionally want to try accessing the Hostname URL from a private browsing window or another browser as well. Should this also not work, do reach out to us for further assistance.

**4. I have added a CNAME record, configured the DNS settings as per Squadcast’s steps. Yet, I receive the error “Too many redirects” while accessing the Status Page. What could be possibly causing this?**

This is possibly to do with the DNS changes (addition of CNAME record) that you recently made at your DNS Provider’s end (GoDaddy, CloudFlare, DigitalOcean, etc.). Please allow sometime (this might take upto 48 hours in extreme cases) for the DNS changes to fully propagate and take effect before you can access your public Status Page via the Hostname URL. Should this also not work, do reach out to us for further assistance.

**5. Accessing a Private Status Page versus a Public Status Page**

**Private Status Page URL** A Private Status Page’s URL can be shared with the team members who have access to Squadcast (added as users of the Squadcast account). Please note that it is not the custom URL (depicted in the red box) that is entered in the page configuration. It is the URL of the page in the app itself (depicted in the green box). The custom URL is valid only for public viewers of the Status Page, that is if you choose to make the Status Page public.

**6. I have certain production Services running and I want to control the status of the Service displayed on my Status Page. Everytime the production Service has an incident, I do not want the status of that Service on my Status Page to be degraded. Is there a way for me to achieve this?**

Absolutely, we understand that you may have certain non-critical incidents also affecting your Services that need not necessarily mean that your entire Service is degraded. To go about this, please follow the steps below:

* For each such Service of yours, create a duplicate Service to be displayed on the Status Page. This Service’s sole purpose is to appear on the Status Page, so you need not have to integrate this Service with your monitoring tools or route any alerts to it.
* Choose to display this duplicate Service on your Status Page instead of your original production Service. Give it an Alias.
* Every time your production Service has a severe incident/outage, you can create an incident manually for the duplicate Service and post incident updates to your Status Page for _this_ incident.
* What this also means is, when you create the incident for this duplicate Service, its status on the Status Page will be degraded, representing the actual state at your end.
* Once your outage/incident for the production Service is `resolved`, you can go ahead and resolve the incident that you previously created and post the incident update to your Status Page for the same.

**7. Can I receive notifications for Status Page Updates in Slack or Microsoft Teams?**

* [Enable Subscriptions](broken-reference) for your Status Page
* Obtain the **Email address** of the [Slack](https://slack.com/intl/en-in/help/articles/206819278-Send-emails-to-Slack#create-a-channel-email) or [MS Teams](https://support.microsoft.com/en-us/office/send-an-email-to-a-channel-in-teams-d91db004-d9d7-4a47-82e6-fb1b16dfd51e#bkmk\_send) channel where you would like to receive the notifications for Status Page updates
* Add all such Email addresses under **Subscriptions** -> **Email** and click on **Subscribe**
* If there is an option to do so, ensure that you have added the SMTP Endpoint for Squadcast - `incidents.squadcast.com`

With this, every time there is an update posted to the Status Page for an incident, a notification for the same would appear in the Slack or MS Teams channel as well.

**8. Does Squadcast provide APIs for creating and updating Status Page?**

We currently do not have Public APIs for creating, managing subscriptions or updating the Status Page.

**9. I have enabled Webhook subscriptions only for my Status Page. When I click on the Subscribe on my Status Page, I am asked to enter an Email address in addition to a Webhook endpoint. Why is that so?**

The Email placeholder you see here is for Webhook usage confirmation/verification, not to receive incident update notifications via Email subscriptions. This Email address needs to be accessible and one must be able to verify the Email sent to this Email address in order to receive incident update notifications via the Webhook.

**10. I have added a Webhook under Subscribe option and when I click on Subscribe, it throws an error - “Webhook URL returned: 400”. Why is this happening?**

We send out the [payloads in a particular format](broken-reference) to the added Webhook, and most likely, the payload format we send is not being accepted by the 3rd party platform. This is why you see a `Webhook URL returned: 400` error appear on the screen. In such cases, please check to see if the 3rd party platform can receive incident update notifications in the form of an Email or if you can modify the accepted payload format on their platform.

Yes, it is recommended that you use an image with dimensions _1300x250_ for best results.

**12. Will the status of my displayed dependent Services be updated independently of the status of the parent Service?**

Yes, that is correct. Only the Services that have an open incident (incident in `Triggered` or `Acknowledged` states) will be depicted as `Degraded` or its equivalent.

**13. What is the Incident History retention/data display period by default?**

You will be able to view incident updates posted to your Status Page in the **last 14 days (2 weeks)**.

**14. Can I edit the previously posted incident updates on my Status Page?**

Yes, you can edit previously posted incident updates to the Status Page.

**15. I want to display more information for my incident, for example, time according to my local timezone or the Incident Details. Is this possible?**

Yes, absolutely! You can add any information you want to provide maximum context of the ongoing issue to your end users within the **Custom Description** placeholder that supports `Markdown` formatting as well.

**16. How many Status Pages can I add in my current plan? Can I add both Private and Public Status Pages?**

The number of **Public Status Pages** that can be added depend on the [Pricing Plan](https://www.squadcast.com/pricing) that your account is currently on.

* **Free Plan**: 1
* **Pro Plan**: 5
* **Enterprise Plan**: Unlimited

**Private Status Pages** can be added **only** in the **Pro and Enterprise Plans**, **not** in the **Free Plan**.

**17. Is there a limit on the number of subscribers to the Status Page? Can I view the list of subscribers to my Status Page?**

No, there is **no limit on the number of subscribers** to your Status Page. You are also **not charged for subscriptions** to your Status Page.

However, you will **not be able to view the list of subscribers** that have subscribed to your Status Page.

**18. Will the users get notified of the edited or deleted changes in the Status Page?**

No, the users will not be notified of the changes. They will have to navigate to the Status Page to view any updates.

**19. Will the time stamp change when a message is edited or deleted?**

No, it will show the timestamp of the original message that was posted.

**20. In a scenario where there is a Service with an open incident (Status - Degraded), and a Service Under Maintenance, what will the Status Page Header read?**

In such a scenario, the Degraded Status will always take precendence over Under Maintenance Status. The Status Page Header will read - Degraded.

**21. Will the subscriber receive an email notification when a Service Maintenance is scheduled?**

Yes, the subscriber will be sent an email notifying them when a Service Maintenance is scheduled.

**22. Will the subscriber receive an email notification when a Service Maintenance window commences?**

No, the subscriber will not be sent an email notifying them of the Service Maintenance commencement.

**23. Will the subscriber receive an email notification when a Service Maintenance window is edited?**

No, the subscriber will not be sent an email notifying them of any edits in the the Service Maintenance window.
