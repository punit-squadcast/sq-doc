# Squadcast Search

Use the global search bar to look for incidents, documentation or other entities for your Team within the platform

### Basic commands <a href="#basic-commands" id="basic-commands"></a>

Search requires some basic commands to work with.

* Once in search, autocompletes can be provided with `Tab`
* Use `CTRL + SPACE` to view autocomplete
* Access search helps within search by typing in `?:`
* To execute a command use `CMD + ENTER` for Mac and `CTRL + ENTER` for Windows

### goto <a href="#goto" id="goto"></a>

`goto` enables _instant navigation_ when used along with `profile`.

* Activate the global search bar using `CMD/CTRL + SHIFT + K`
* Type in `goto` and enter
* Type in `profile` and then search for users by their email address
* `CMD/CTRL + Return/Enter` to navigate to the user’s profile

### Help <a href="#help" id="help"></a>

Now you can navigate to alert source integration documents directly through the search. Type in `help:` and then the keyword or name of the documentation you want to search for.

### Search through Incidents <a href="#search-through-incidents" id="search-through-incidents"></a>

Search incidents with queries. We support a set of tokens to fine-tune the results. Supported tokens can be viewed in the search help by typing `?:`

### Search through Postmortems <a href="#search-through-postmortems" id="search-through-postmortems"></a>

Search postmortems with queries from the **Global Search Bar**

We support a set of tokens to fine-tune the results. Supported tokens can be viewed in the search help by typing `?:`

You can search for **Postmortems** through **Incident Message** and **Description**, **Impacted Service**, **Created After**, **Created Before** and **Postmortem Content**.

Example Use Case:

I want to look for a postmortem that contains the string `jira` in its Incident Message.

* Type in `?:` if you want to look up the query token
* Type in `in: postmortems message "jira"`
* Hit `Command + Enter`

Your search results that match this query will be populated as shown below

Search also provides history of queries. Search history is specific to a user with respect to the Organization.
