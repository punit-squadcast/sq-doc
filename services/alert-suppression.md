# Alert Suppression

Avoid alert fatigue by setting up Suppression Rules

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

**(6)** Suppression Rules can be added in two different ways:

#### (A) UI-based Rule Builder (Beginner-friendly) <a href="#a-ui-based-rule-builder-beginner-friendly" id="a-ui-based-rule-builder-beginner-friendly"></a>

(a) On the right, you can view the _payload of the **latest** alert_ for the chosen Alert Source

(b) The drop-downs in the Rule Builder contain values from the payload on the right. You can use them to easily create your Suppression Rules. As you build the expression from these drop-downs, you can also see the corresponding _raw string_ being auto-populated for the same under **String Expression**.

(c) You can add more than 1 condition for a rule by selecting **Add Condition** (a logical AND is performed between all the conditions -> the entire Suppression Rule will evaluate to `True` only if all the conditions evaluate to `True`)

#### (B) Raw String Method <a href="#b-raw-string-method" id="b-raw-string-method"></a>

(a) On the right, you can view the payload of the latest alert for the chosen Alert Source

(b) Click on **Edit** to enable Raw String method

(c) Write your custom Suppression Rule expression

#### Supported Rules <a href="#supported-rules" id="supported-rules"></a>

The rule engine supports expressions with parameters, arithmetic, logical, and string operations. You can also check out this [link](https://regex101.com/) to get an idea of all the expression types accepted in Squadcast.

**Basic Expressions**

`10 > 0`, `1+2`, `100/3`

**Parameterized Expressions**

`payload.metric == "disk"` The available parameters are `payload` `payload` : This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source `payload` : This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source `payload` : This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source `incident_details`: This contains the content of `message` and `description` of the incoming event `source`: This denotes the associated alert source for the current/incoming event

**Regular Expressions**

`re(payload.metric, "disk.*")`

**Parse JSON content within the payload using `jsonPath` to add a tag**

**General Format** `jsonPath(<the JSON string that should be parsed for JSON content>, <"the parameter that needs to be picked from the parsed JSON object">)`

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

This will pick out the value `AlarmName` from the Message object in the payload based on which, you can suppress the incident.

**Example**

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

* The alert message contains: `[Bug]`
* The alert source is `grafana`

**Suppression Rule:**

```
re(payload.incident_details.message, "[Bug]") && source == "grafana";
```

### Discarding suppressed incidents <a href="#discarding-suppressed-incidents" id="discarding-suppressed-incidents"></a>

To discard incoming alerts and stop them from being triggered as incidents in Squadcast, use the `discard()` function in conjunction with Suppression Rules.

#### Example <a href="#example-1" id="example-1"></a>

Suppression Rule:

```
source == "grafana" && re(payload["message"], "Notification Message");
```

Supression Rule with `discard()`:

```
source == grafana &&
	re(payload["message"], "Notification Message") &&
	discard();
```

### Viewing Suppressed Incidents <a href="#viewing-suppressed-incidents" id="viewing-suppressed-incidents"></a>

You can view `suppressed` incidents in the [Incidents](https://support.squadcast.com/docs/incident-list-table-view) page by clicking on **All Incidents** and choosing **Suppressed** as highlighted in the screenshot below.

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** What kind of regex can be used to write custom rules?

The rule engine supports expressions with parameters, arithmetic, logical, and string operations. You can also check [this](https://regex101.com/) out to get an idea of all the expression types accepted in Squadcast. Please do your regex [here](https://regex101.com/) against `Golang` flavour as shown in the screenshot below and then, set them up in Squadcast:

**(2)** Can I create OR rules?

Yes, you can. The evaluation between different Suppression Rules is `OR`. Add multiple Suppression Rules to enable `OR` evaluation.

**(3)** While adding a Suppression Rule, is the _search string_ in the rule case sensitive?

Yes, that is correct. For example, if your seach string is “ALERT” and your payload does not contain “ALERT” but contains “Alert”, this will not be matched. Your search string should be “Alert”.

**(4)** How do I know if an incident gets suppressed due to a Suppression Rule?

In the Incident’s Activity Timeline the reason for suppression is displayed.

**(5)** I have configured multiple rules for a particular Service. Can I search through the configured rules to find the rule I am looking for?

Yes, that is doable. You will notice a **Search** option on the left-top of the rules modal. You can type in a word you recall from the rule description or the rule itself. Any matching results will yield the narrowed down set of rules.
