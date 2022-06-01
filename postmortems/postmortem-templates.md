# Postmortem Templates

Postmortem Templates for the Postmortems that you conduct for incidents

#### Postmortem Templates <a href="#postmortem-templates" id="postmortem-templates"></a>

Each Organization has a few predefined **Postmortem Templates** availabe from **Squadcast** by default. You can choose to create new templates or modify the existing ones, based on how you do postmortems within your Organization.

#### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the **Account Owner** or **Users** with the **Manage Postmortem Templates** permission will have the access to modify Postmortem Templates and/or create new Postmortemm Templates for the Organization

#### Managing Postmortem Templates <a href="#managing-postmortem-templates" id="managing-postmortem-templates"></a>

You can follow the steps below to create a new Template or modify an existing Template:

**(1)** Click on **Settings** in the primary navigation and then select **Postmortem** from the secondary navigation

Here you’ll find the list of pre-defined templates.

You can either make use of the existing templates or add new templates for the rest of your Organization to use.

**(2)** There is a set of `incident-variables`, which can be used while creating **Postmortem Templates**. These `incident-variables` will dynamically get populated with the incident’s data for which the Postmortem is being created. You can see all the available `incident-variables` on the right-half while creating templates. The variables need to be specified using [MustacheJS syntax](https://github.com/janl/mustache.js/)

Refer to any of the pre-defined templates for the templating syntax.

**(3)** A template can be marked **Default**. While filling a Postmortem report for an incident, the default template would pop up automatically when a user **Starts a Postmortem** for it

Click on **Add** to save the new template or **Update** to save the changes in an existing template

#### Adding Attachments <a href="#adding-attachments" id="adding-attachments"></a>

You can add a variety of file types as an attachment in the Postmortem Template.

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

#### How-to-video: Creating a Postmortem Template <a href="#how-to-video-creating-a-postmortem-template" id="how-to-video-creating-a-postmortem-template"></a>

#### FAQs <a href="#faqs" id="faqs"></a>

**Q:** Can Stakeholders create Postmortem Templates?

**A:** No, **Stakeholders** cannot create Postmortem Templates.

**Q:** Are Postmortem Templates limited to a particular Team?

**A:** No, Postmortem Templates are an Organization-wide entity. Any Team in the Organization can make use of the Postmortem Templates added.

**Q:** I am in a Team and the Team has all the necessary Roles (Create, Read, Update, Delete) for Postmortems, yet I am unable to add a Postmortem Template that my Team could use. What am I missing?

**A:** The Roles associated with a Team for Postmortems are different from the Permission required to create a Postmortem Template. The Permission required to create/modify a Postmortem Template is an Organization-level Permission. Head over to Settings -> Postmortem -> and ensure that you have been given the same (the checkbox must be enabled for **Manage Postmortem Templates** Permission).
