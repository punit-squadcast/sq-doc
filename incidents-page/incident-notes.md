---
description: Share notes and collaborate with your team during incident resolution
---

# Incident Notes

**Incident Notes** enable you to add important notes for you and your team that can help mitigate an incident faster.

You can use this to:

* Collaborate with your team and resolve the incident
* Use it to store important pointers that will help with the mitigation
* Use it to store Notes that can be populated in the Postmortem report
* Share Team-wide information like resolution reasons, follow-up tasks, etc.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only verified users would be receiving any kind of notifications from Squadcast
* For receiving Push notifications, users should have the latest version of the [Squadcast mobile app](../mobile-app/using-the-mobile-app.md) installed

### To get started <a href="#to-get-started" id="to-get-started"></a>

First, select the **Team** from the team picker on the top.

**(1)** Click on either **Dashboard** or **Incidents** from the sidebar

![](../.gitbook/assets/incident\_1.png)

**(2)** Open an incident to view the **Incident Details**

![](../.gitbook/assets/incident\_notes\_1\_1.png)

#### Mentioning Users, Squads and Teams in Notes. <a href="#mentioning-users-squads-and-teams-in-notes" id="mentioning-users-squads-and-teams-in-notes"></a>

* Users can call out other users using the “@” symbol for important notes. This can also be used to inform users of a specific need, or information or as a means to notify your **Stakeholders** on information pertaining to the status of an ongoing incident
* Users can also notify all the members of a particular Squad or a Team by “@” mentioning the Squad or the Team name

![](../.gitbook/assets/incident\_notes\_2.png)

* Users who are currently on-call are indicated with a green dot against their name. In the above screenshot, you can see that **Diane Nyugen** is currently on-call
* The mentioned Users, Squad or Team members will get notified instantly via **Email** and **Push** notification on the Squadcast mobile app. However, the author of the note will not get notified even when they are self mentioned or belong to a mentioned Squad or Team

![](../.gitbook/assets/incident\_notes\_3.png)

![](../.gitbook/assets/incident\_notes\_4.png)

#### Adding Images <a href="#adding-images" id="adding-images"></a>

* Incident Notes support Markdown text format. Hence, images can be added as URLs or links

![](../.gitbook/assets/incident\_notes4\_1.png)

**Adding Images to a Note**

You can use the below syntax to add an image:

```
![image_name](image_url)
```

![](../.gitbook/assets/incident\_notes\_6.png)

#### Editing or Deleting a Note <a href="#editing-or-deleting-a-note" id="editing-or-deleting-a-note"></a>

* One can **Edit** or **Delete** existing notes as well by clicking on the **More** icon corresponding to a particular note which would appear on hovering over the note

![](../.gitbook/assets/incident\_notes\_7.png)

#### Starring and Un-starring Notes <a href="#starring-and-un-starring-notes" id="starring-and-un-starring-notes"></a>

* Star important notes by clicking on the **Star** icon as shown in the screenshot above beside the **More** option

![](../.gitbook/assets/incident\_notes\_8.png)

* When you have a bulk of Notes and want to simply take a look at all the important, Starred Notes, you can do so by clicking on **View Starred Notes**

![](../.gitbook/assets/incident\_notes\_9.png)

* To un-star, click on the **Star** icon for that note

![](../.gitbook/assets/incident\_notes\_10.png)

* Starred notes would be captured in the **Incident Activity Timeline**. Clicking on the starred note activity in the **Incident Activity Timeline** will take you to that specific note in the Incident Notes section

![](../.gitbook/assets/incident\_notes10\_1.png)

### Adding Attachments <a href="#adding-attachments" id="adding-attachments"></a>

You can add a variety of file types as an attachment in the Notes section for an incident.

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

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** What actions can be taken by the different User Types?

* **Note Creation**: Any user can add a note
* **Note Updation**: Only the author of the note can update it
* **Note Deletion**: Only the author of the note can delete it
* **Note Starring and Un-starring**: Any user can star/un-star any note

**(2)** Can I add and star notes from the Squadcast mobile app?

Yes, users can add, edit, delete, star and unstar notes for an incident from the Squadcast mobile app.

To do so:

* Login to your Organization on the Squadcast mobile app, choose your Team and open an incident

![](../.gitbook/assets/incident\_notes\_11.png)

* “@” mention a user and/or add notes

![](../.gitbook/assets/incident\_notes\_12.png)

* **A long press on a note authored by you will give you an option to \_star, un-star, edit and delete**_\*\* it. A long press on a note authored by others will give you an option to only \*\*_**star, un-star**\_\*\* it\*\*

![](../.gitbook/assets/incident\_notes\_13.png)

* View only starred notes by switching to **Starred Notes** tab

![](../.gitbook/assets/incident\_notes\_14.png)

**(3)** Can I call Stakeholders in the Notes section and notify them?

Yes, you can “@” mention Stakeholders and they would be notified of the note via **Email** and **Push**.
