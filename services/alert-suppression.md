---
description: Avoid alert fatigue by setting up Suppression Rules
---

# Alert Suppression

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=rBkqbqObCS8" %}

Alert suppression can help you avoid alert fatigue by suppressing notifications for non-actionable alerts.

Squadcast will suppress the incidents that match any of the Suppression Rules you create for your Services. These incidents will go into the `Suppressed` state and you will not get any notifications for them.

These are useful in situations where you would like to _view_ your all your informational alerts in Squadcast but do not want to get notified for them.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Suppression Rules).
* Integrate with an Alert Source and ensure that the Alert Source has started sending alerts to Squadcast before setting up Suppression Rules.

### Creating Suppression Rules <a href="#creating-suppression-rules" id="creating-suppression-rules"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

**(1)** Click on **Services** in the primary navigation

**(2)** Select a **Service** and click on the **More options** icon

**(3)** Click on **Suppression Rules**

![](../.gitbook/assets/alert\_suppression\_1\_new.png)

**(4)** Select an **Alert Source** from the drop-down

**(5)** Click on **Add new rule**

![](../.gitbook/assets/alert\_suppression\_2\_new.png)

**(6)** Suppression Rules can be added in two different ways:

#### (A) UI-based Rule Builder (Beginner-friendly) <a href="#a-ui-based-rule-builder-beginner-friendly" id="a-ui-based-rule-builder-beginner-friendly"></a>

(a) On the right, you can view the _payload of the **latest** alert_ for the chosen Alert Source

(b) The drop-downs in the Rule Builder contain values from the payload on the right. You can use them to easily create your Suppression Rules. As you build the expression from these drop-downs, you can also see the corresponding _raw string_ being auto-populated for the same under **String Expression**.

![](../.gitbook/assets/alert\_suppression\_3\_new.png)

(c) You can add more than 1 condition for a rule by selecting **Add Condition** (a logical AND is performed between all the conditions -> the entire Suppression Rule will evaluate to <mark style="color:red;">`True`</mark> only if all the conditions evaluate to <mark style="color:red;">`True`</mark>)

![](../.gitbook/assets/alert\_suppression\_4\_new.png)

{% hint style="info" %}
**Note:**

The drop-down blocks only support the logical <mark style="color:red;">`AND`</mark> operator between 2 expressions. If you want to have a logical <mark style="color:red;">`OR`</mark> operation between 2 expressions, then you would have to create a new Suppression Rule.
{% endhint %}

{% hint style="info" %}
**Comparison Operators within Suppression Rules**

You can also leverage comparison operators such as <mark style="color:red;">`==, <, <=, >, >=`</mark> within your rules using the drop-down blocks, when the parameter you are evaluating against, is a **numerical value from the payload** to reduce alert noise.

![](../.gitbook/assets/alert\_suppression\_7\_new.png)
{% endhint %}

#### (B) Raw String Method <a href="#b-raw-string-method" id="b-raw-string-method"></a>

{% hint style="warning" %}
**Important**

Once you opt for the Raw String method, you cannot revert to the UI-based Rule Builder method.
{% endhint %}

(a) On the right, you can view the payload of the latest alert for the chosen Alert Source

(b) Click on **Edit** to enable **the** Raw String method

![](../.gitbook/assets/alert\_suppression\_5\_new.png)

(c) Write your custom Suppression Rule expression

#### Supported Rules <a href="#supported-rules" id="supported-rules"></a>

The rule engine supports expressions with parameters, arithmetic, logical, and string operations. You can also check out this [link](https://regex101.com/) to get an idea of all the expression types accepted in Squadcast.

**Basic Expressions**

<mark style="color:red;">`10 > 0`</mark>, <mark style="color:red;">`1+2`</mark>, <mark style="color:red;">`100/3`</mark>

**Parameterized Expressions**

<mark style="color:red;">`payload.metric == "disk"`</mark> The available parameters are <mark style="color:red;">`payload`</mark>: This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source <mark style="color:red;">`payload`</mark>: This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source <mark style="color:red;">`payload`</mark>: This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source <mark style="color:red;">`incident_details`</mark>: This contains the content of the <mark style="color:red;">`message`</mark> and <mark style="color:red;">`description`</mark> of the incoming event <mark style="color:red;">`source`</mark>: This denotes the associated alert source for the current/incoming event

**Regular Expressions**

<mark style="color:red;">`re(payload.metric, "disk.*")`</mark>

**Parse JSON content within the payload using **<mark style="color:red;">**`jsonPath`**</mark>** to add a tag**

**General Format** <mark style="color:red;">`jsonPath(<the JSON string that should be parsed for JSON content>, <"the parameter that needs to be picked from the parsed JSON object">)`</mark>

**Example**

Below is an example payload:

```
{
	"payload": {
   "payload": {
	"payload": {
		"Type": "Notification",
		"MessageId": "5966c484-5b37-58df",
		"TopicArn": "arn:aws:sns:us-east-1:51:Test",
		"Message": "{\"AlarmName\":\"Squadcast Testing - Ignore\",\"AlarmDescription\":\"Created from EC2 Console\"}"
	}
}
```

```
jsonPath(payload.Message, "AlarmName");
```

This will pick out the value <mark style="color:red;">`AlarmName`</mark> from the Message object in the payload based on which, you can suppress the incident.

**Example**

{% hint style="info" %}
**Multiple Alert Sources**

We can see alert payloads of past events from different alert sources for the service by selecting the respective alert source from the dropdown in the right-half side.

Since the payload format is fixed for a given alert source, it is usually preferrable to have suppression rules on a per-alert source basis. This can be done by making use of the `source` field which lets you know the alert source that triggered the incoming event.

For example, if you want to have a suppression rule for a service, only for alerts coming for **`grafana`** alert source, then the corresponding rule would look something like:



```
source == 'grafana' && (<your_suppression_rule>)
```
{% endhint %}

Below is an example payload for demonstration:

```
{
	"payload": {
		"issue_description": "bug - 2",
		"issue_id": "10029",
		"issue_key": "HYD-30",
		"issue_labels": [],
		"issue_link": "http://13.233.254.18:8080/browse/HYD/issues/HYD-30",
		"issue_priority": "Medium",
		"issue_summary": "bug - 2",
		"issue_type": "Bug",
		"project_id": "10000",
		"project_key": "HYD",
		"project_name": "hydra"
	},
	"incident_details": {
		"message": "[Bug] bug - 2",
		"description": "+ Project: HYDRA \n+Issue Type: Bug ..."
	},
	"source": "grafana"
}
```

To suppress any incoming alert when:

* The alert message contains: <mark style="color:red;">`[Bug]`</mark>
* The alert source is <mark style="color:red;">`grafana`</mark>

**Suppression Rule:**

```
re(payload.incident_details.message, "[Bug]") && source == "grafana";
```

### Discarding suppressed incidents <a href="#discarding-suppressed-incidents" id="discarding-suppressed-incidents"></a>

To discard incoming alerts and stop them from being triggered as incidents in Squadcast, use the <mark style="color:red;">`discard()`</mark> function in conjunction with Suppression Rules.

#### Example <a href="#example-1" id="example-1"></a>

Suppression Rule:

```
source == "grafana" && re(payload["message"], "Notification Message");
```

Suppression Rule with <mark style="color:red;">`discard()`</mark>:

```
source == grafana &&
	re(payload["message"], "Notification Message") &&
	discard();
```

{% hint style="info" %}
**Avoid hitting Rate Limits**

The `discard()` function can be used to avoid hitting the [**Incident Rate Limits**](https://support.squadcast.com/docs/incident-rate-limiting) as **Suppressed events that are discarded** don’t get counted against the allowed rate limits.
{% endhint %}

### Viewing Suppressed Incidents <a href="#viewing-suppressed-incidents" id="viewing-suppressed-incidents"></a>

You can view <mark style="color:red;">`suppressed`</mark> incidents in the[ Incidents](../incident-list/incident-list-view.md) page by clicking on **All Incidents** and choosing **Suppressed** as highlighted in the screenshot below.

![](../.gitbook/assets/alert\_suppression\_6\_new.png)

{% hint style="info" %}
**Note**

* **`Suppressed`** and **`Resolved`** are the final states for incidents in Squadcast. You will not be able to take any action on incidents that are in these states.
* Incident information will be available on the Squadcast platform even if they are suppressed.
{% endhint %}

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** What kind of regex can be used to write custom rules?

The rule engine supports expressions with parameters, arithmetic, logical, and string operations. You can also check [this](https://regex101.com/) out to get an idea of all the expression types accepted in Squadcast. Please do your regex [here](https://regex101.com/) against <mark style="color:red;">`Golang`</mark> flavour as shown in the screenshot below and then, set them up in Squadcast:

![](<../.gitbook/assets/de-duplication\_9 (3).png>)

**(2)** Can I create OR rules?

Yes, you can. The evaluation between different Suppression Rules is <mark style="color:red;">`OR`</mark>. Add multiple Suppression Rules to enable <mark style="color:red;">`OR`</mark> evaluation.

**(3)** While adding a Suppression Rule, is the _search string_ in the rule case sensitive?

Yes, that is correct. For example, if your search string is “ALERT” and your payload does not contain “ALERT” but contains “Alert”, this will not be matched. Your search string should be “Alert”.

**(4)** How do I know if an incident gets suppressed due to a Suppression Rule?

In the Incident’s Activity Timeline the reason for suppression is displayed.

![](../.gitbook/assets/suppression\_reason.png)

**(5)** I have configured multiple rules for a particular Service. Can I search through the configured rules to find the rule I am looking for?

Yes, that is doable. You will notice a **Search** option on the left-top of the rules modal. You can type in a word you recall from the rule description or the rule itself. Any matching results will yield the narrowed-down set of rules.

![](<../.gitbook/assets/automation-rules-search-1 (3).png>)
