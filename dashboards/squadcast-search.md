---
description: >-
  Use the global search bar to look for incidents, documentation or other
  entities for your Team within the platform
---

# Squadcast Search

### Basic commands <a href="#basic-commands" id="basic-commands"></a>

Search requires some basic commands to work with.

* Once in search, autocompletes can be provided with <mark style="color:red;">`Tab`</mark>
* Use <mark style="color:red;">`CTRL + SPACE`</mark> to view autocomplete
* Access search helps within search by typing in <mark style="color:red;">`?:`</mark>
* To execute a command use <mark style="color:red;">`CMD + ENTER`</mark> for Mac and <mark style="color:red;">`CTRL + ENTER`</mark> for Windows

![](../.gitbook/assets/search\_1.png)

### goto <a href="#goto" id="goto"></a>

<mark style="color:red;">`goto`</mark> enables _instant navigation_ when used along with <mark style="color:red;">`profile`</mark>.

* Activate the global search bar using <mark style="color:red;">`CMD/CTRL + SHIFT + K`</mark>
* Type in <mark style="color:red;">`goto`</mark> and enter
* Type in <mark style="color:red;">`profile`</mark> and then search for users by their email address
* <mark style="color:orange;">`CMD/CTRL + Return/Enter`</mark> to navigate to the user’s profile

![](../.gitbook/assets/search\_2.png) ![](../.gitbook/assets/search\_3.png)



### Help <a href="#help" id="help"></a>

Now you can navigate to alert source integration documents directly through the search. Type in <mark style="color:red;">`help:`</mark> and then the keyword or name of the documentation you want to search for.

![](../.gitbook/assets/search\_4.png)

### Search through Incidents <a href="#search-through-incidents" id="search-through-incidents"></a>

Search incidents with queries. We support a set of tokens to fine-tune the results. Supported tokens can be viewed in the search help by typing <mark style="color:red;">`?:`</mark>

![](../.gitbook/assets/search\_5.png)

### Search through Postmortems <a href="#search-through-postmortems" id="search-through-postmortems"></a>

Search postmortems with queries from the **Global Search Bar**

We support a set of tokens to fine-tune the results. Supported tokens can be viewed in the search help by typing <mark style="color:orange;">`?:`</mark>

![](../.gitbook/assets/search\_6.png)

You can search for **Postmortems** through **Incident Message** and **Description**, **Impacted Service**, **Created After**, **Created Before** and **Postmortem Content**.

{% hint style="info" %}
**Note: The **<mark style="color:red;">**`message`**</mark>** query**

The <mark style="color:red;">`message`</mark> query looks for a string match in the Incident Title and the Postmortem Content.
{% endhint %}

Example Use Case:

I want to look for a postmortem that contains the string <mark style="color:red;">`JIRA`</mark> in its Incident Message.

* Type in <mark style="color:red;">`?:`</mark> if you want to look up the query token
* Type <mark style="color:red;">`in: postmortems message "jira"`</mark>
* Hit <mark style="color:red;">`Command + Enter`</mark>

Your search results that match this query will be populated as shown below

![](../.gitbook/assets/search\_7.png)

Search also provides history of queries. Search history is specific to a user with respect to the Organization.
