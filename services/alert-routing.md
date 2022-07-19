# Alert Routing

Route alerts to the right responder(s) based on the tags they carry

Alert Routing allows you to configure _Routing Rules_ to ensure that alerts are routed to the right responder with the help of <mark style="color:red;">`event tags`</mark> attached to them.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Routing Rules).
* Ensure you have <mark style="color:red;">`Tags`</mark> [defined](https://support.squadcast.com/docs/event-tagging) for the Service.

### Configuring Routing Rules <a href="#configuring-routing-rules" id="configuring-routing-rules"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

**(1)** Click on **Services** in the primary navigation

**(2)** For the Service of your choice, click on the **More options** icon and select **Routing Rules**

![](../.gitbook/assets/alert\_routing\_1.png)

#### UI-based Rule Builder (Beginner-friendly) <a href="#ui-based-rule-builder-beginner-friendly" id="ui-based-rule-builder-beginner-friendly"></a>

**(a)** This box displays all the <mark style="color:red;">`[event tags]`</mark>(https://support.squadcast.com/docs/event-tagging) defined for this Service, which can be used to define Routing Rules

**(b)** Select **Add new rule**

![](../.gitbook/assets/alert\_routing\_3.png)

**(c)** Pick the **event tag** <mark style="color:red;">`key`</mark> and <mark style="color:red;">`value`</mark> pair that you are checking for in an incident using the drop-downs

![](../.gitbook/assets/alert\_routing\_4.png)

**(d)** **Add Conditions** to make your rules more granular

**(e)** You can route the incident containing the specific <mark style="color:red;">`event tags`</mark> to either a <mark style="color:red;">`User`</mark>, <mark style="color:red;">`Squad`</mark> or an <mark style="color:red;">`Escalation Policy`</mark>. Pick the same from the drop-down

**(f)** Click on **Save**

![](../.gitbook/assets/alert\_routing\_5.png)

{% hint style="info" %}
**Default Service Escalation Policy Override**

The Alert Routing Rules will take precedence (override) over the default Escalation Policy for the Service if any of the rules match (evaluate to True) an incoming incident.
{% endhint %}

#### Raw String Method <a href="#raw-string-method" id="raw-string-method"></a>

{% hint style="info" %}
**Note**

Once you opt for the Raw String method, you cannot revert to the UI-based Rule Builder method for that rule.
{% endhint %}

**(a)** This box displays all the <mark style="color:red;">`event tags`</mark> [defined](https://support.squadcast.com/docs/event-tagging) for this Service

**(b)** Select **Add new rule**

![](<../.gitbook/assets/alert\_routing\_3 (1).png>)

**(c)** Click on **Edit** to enable **the** Raw String method

![](../.gitbook/assets/alert\_routing\_7.png)

**(d)** Write your custom Tagging Rule expression and select **Route To** accordingly

**(e)** Click on **Save**

![](../.gitbook/assets/alert\_routing\_6.png)

#### Supported Rules <a href="#supported-rules" id="supported-rules"></a>

The rule engine supports expressions with parameters, arithmetic, logical, and string operations.

**Basic Expressions**

<mark style="color:red;">`10 > 0`</mark>, <mark style="color:red;">`1+2`</mark>, <mark style="color:red;">`100/3`</mark>

**Parameterized Expressions**

<mark style="color:red;">`tags.severity == "high"`</mark>

The available parameters are <mark style="color:red;">`tags`</mark>

* <mark style="color:red;">`tags`</mark>: This parameter contains all the configured tags for a given Service.

**Regular Expressions**

<mark style="color:red;">`re(tags.severity, "high.*")`</mark>

This can be used to check if a particular tag field matches a regular expression.

**Example**

Below is the set of <mark style="color:red;">`event tags`</mark> defined for a Service (as shown in the right panel of the configuration space)

```
{
	"tags": [
		{
			"severity": "critical"
		},
		{
			"severity": "high"
		},
		{
			"severity": "low"
		}
	]
}
```

**Use-case for Routing Rules**

When:

* <mark style="color:red;">`severity`</mark> is <mark style="color:red;">`critical`</mark> : Route to a **Squad**
* <mark style="color:red;">`severity`</mark> is <mark style="color:red;">`high`</mark> : Route to an **Escalation Policy**
* <mark style="color:red;">`severity`</mark> is <mark style="color:red;">`low`</mark> : Route to a **User**

**Routing Rules are as follows:**

* <mark style="color:red;">`tags.severity == "critical"`</mark> _route_ to a <mark style="color:red;">`squad`</mark>
* <mark style="color:red;">`tags.severity == "high"`</mark> _route_ to an <mark style="color:red;">`escalation policy`</mark>
* <mark style="color:red;">`tags.severity == "low"`</mark> _route_ to a <mark style="color:red;">`user`</mark>

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** How do I know if an incident gets routed due to a Routing Rule?

In the Incident’s Activity Timeline the reason for routing, and to which entity it gets routed to, is displayed.

![](../.gitbook/assets/routing\_reason.png)

**(2)** What kind of regex can be used to write custom rules?

The rule engine supports expressions with parameters, arithmetic, logical, and string operations. You can also check [this](https://regex101.com/) out to get an idea of all the expression types accepted in Squadcast. Please do your regex [here](https://regex101.com/) against <mark style="color:red;">`Golang`</mark> flavour as shown in the screenshot below and then, set them up in Squadcast:

![](<../.gitbook/assets/de-duplication\_9 (1).png>)

**(3)** Can I create OR rules?

Yes, you can. The evaluation between different Routing Rules is <mark style="color:red;">`OR`</mark>. Add multiple Routing Rules to enable <mark style="color:red;">`OR`</mark> evaluation.

**(4)** While adding a Routing Rule, is the _search string_ in the rule case sensitive?

Yes, that is correct. For example, if your **search** string is “ALERT” and your payload does not contain “ALERT” but contains “Alert”, this will not be matched. Your search string should be “Alert”.

**(5)** Do Routing Rules have priority?

Yes, you can specify Execution Rule Priority for the rules defined by moving them <mark style="color:red;">`Up`</mark> or <mark style="color:red;">`Down`</mark> the list of rules.

![](<../.gitbook/assets/status-based-deduplication\_5 (1).png>)

**(6)** I have configured multiple rules for a particular Service. Can I search through the configured rules to find the rule I am looking for?

Yes, that is doable. You will notice a **Search** option on the left-top of the rules modal. You can type in a word you recall from the rule. Any matching results will yield the narrowed-down set of rules.

![](<../.gitbook/assets/automation-rules-search-1 (1).png>)
