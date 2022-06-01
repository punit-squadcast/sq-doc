# Create Postmortems

Postmortems are a way to summarize the resolution for an incident once it is resolved

Postmortems are a way to summarize the resolution for an incident once it is resolved. It is also a way for you to create a knowledge-base of failures and fixes that can be shared across your team to help build a culture of shared learning and learning from failures.

In this documentation, we’ll be going through how to create Postmortems.

#### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Ensure that the users of the Team have the right Roles (with the right permissions associated with the Postmortem entity) to be able to create and manage Postmortems
* The Postmortem feature is enabled for an incident only after it has been **resolved**. Hence, an incident first needs to be **resolved**

#### Creating a Postmortem <a href="#creating-a-postmortem" id="creating-a-postmortem"></a>

To create a Postmortem for a **resolved incident**:

**(1)** Navigate to the **Incident Details** page for the incident and click on **Start Postmortem**

**(2)** You can select one of the **Postmortem Templates** from the drop-down

The **Postmortem Title** is auto-populated with your Incident Name as default. You can edit it, and start documenting the Postmortem.

**Note**: The `incident-variables` will get auto-populated as per the data available for that particular incident. Remaining details need to be manually filled by the user by **Editing** the Postmortem.

**(3)** Apart from the Markdown body in a Postmortem, you can also create a **check-list of follow-ups** that can be used to keep track of further actions that need to be done for that incident

**(4)** Click on **Create** to save the Postmortem

**(5)** Once a Postmortem is created, any member of the Team with the right permissions can view and manage the Postmortem

**Note:** Once the Postmortem is created (and updated), it can be downloaded offline in either `Markdown (MD)` or `PDF` format.

#### Adding Attachments <a href="#adding-attachments" id="adding-attachments"></a>

You can add a variety of file types as an attachment in the Postmortem of an incident.

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

#### Updating a Postmortem <a href="#updating-a-postmortem" id="updating-a-postmortem"></a>

We understand that conducting Postmortems and documenting it is an iterative process in some cases. In Squadcast, once a Postmortem is created, users with the right permissions can update the Postmortems as well.

There are 2 ways to do this:

**(1)** For an incident, head over to its **Incident Details** page and click on **Update Postmortem**. Switch to the **Edit** mode. Then, make the necessary modifications and click on **Update**

**(2)** Head over to **Postmortems** from the navigation on the left, scroll to the applicable Postmortem in the list. Click on the **Edit** icon, make the necessary changes and click on **Update**
