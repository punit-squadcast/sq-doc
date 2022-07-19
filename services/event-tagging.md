---
description: >-
  Auto-add relevant information like priority, severity or alert type to make
  incoming incidents context-rich
---

# Event Tagging

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=P21OQFioeYA" %}

Event Tagging is a rule-based, auto-tagging system with which you can define customised tags based on incident payloads, that get automatically assigned to incidents when they are triggered.

You can define tags as <mark style="color:red;">`key:value`</mark> pairs. For example, the <mark style="color:red;">`key`</mark> could be <mark style="color:red;">`severity`</mark> and the _possible values_ could be <mark style="color:red;">`SEV0`</mark>, <mark style="color:red;">`SEV1`</mark>, <mark style="color:red;">`SEV2`</mark>, etc., or the <mark style="color:red;">`key`</mark> could be <mark style="color:red;">`Team`</mark> and the _possible values_ could be <mark style="color:red;">`Backend`</mark>, <mark style="color:red;">`Frontend`</mark>, <mark style="color:red;">`Database`</mark>, etc.

Event Tagging can be achieved by defining Tagging Rules for each Service in Squadcast. When these rules evaluate _true_ for an incoming incident, the defined tag pairs are added to it.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

1\. The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Tagging Rules).

2\. Integrate with an Alert Source and ensure that the Alert Source has started sending alerts to Squadcast before setting up Tagging Rules.

### Creating Tagging Rules <a href="#creating-tagging-rules" id="creating-tagging-rules"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

1\. Click on **Services** in the primary navigation

2\. Select a **Service** and click on the **More options** icon

3\. Click on **Tagging Rules**

![](../.gitbook/assets/tagging\_1.png)

4\. Select an **Alert Source** from the drop-down

5\. Click on **Add new rule**

![](../.gitbook/assets/tagging\_2.png)

6\. Tagging Rules can be added in three ways:

#### **A.** UI-based Rule Builder (Beginner-friendly) <a href="#a-ui-based-rule-builder-beginner-friendly" id="a-ui-based-rule-builder-beginner-friendly"></a>

a. On the right, you can view the _payload of the **latest** alert_ for the chosen Alert Source

b. The drop-downs in the Rule Builder contain values from the payload on the right. You can use them to easily create your Tagging Rules

![](../.gitbook/assets/tagging\_3.png)

c. You can add more than 1 condition for a rule by selecting **Add Condition** (a logical AND is performed between all the conditions -> the entire Tagging Rule will evaluate to <mark style="color:red;">`True`</mark> only if all the conditions evaluate to <mark style="color:red;">`True`</mark>)

d. Map any <mark style="color:red;">`Key`</mark> and <mark style="color:red;">`Value`</mark> pair as a tag. Multiple tags can be defined for each rule. You can select different colours for each of your tags

![](../.gitbook/assets/tagging\_4.png)

{% hint style="warning" %}
**Important**

The key of the Tag label, "tag key" can only contain letters (both lowercase and uppercase) and numbers. Anything else will be ignored.
{% endhint %}

#### B. Raw String Method <a href="#b-raw-string-method" id="b-raw-string-method"></a>

{% hint style="warning" %}
**Important**

Once you opt for the Raw String method for a rule, you cannot revert to the UI-based Rule Builder method.
{% endhint %}

a. On the right, you can view the payload of the latest alert for the chosen Alert Source

b. Click on **Edit** to enable the Raw String method

![](../.gitbook/assets/tagging\_5.png)

c. Write your custom Tagging Rule expression. Below are some examples to help you get started:

#### Supported Rules <a href="#supported-rules" id="supported-rules"></a>

The rule engine supports expressions with parameters, arithmetic, logical, and string operations.

**Basic Expressions**

<mark style="color:red;">`10 > 0`</mark>, <mark style="color:red;">`1+2`</mark>, <mark style="color:red;">`100/3`</mark>

**Parameterized Expressions**

<mark style="color:red;">`payload.metric == "disk"`</mark> The available parameters are <mark style="color:red;">`payload`</mark>: This parameter contains the JSON payload of an incident which will be the same as the JSON payload format for the future events for a particular alert source

**Regular Expressions**

<mark style="color:red;">`re(payload.metric, "disk.*")`</mark>

{% hint style="warning" %}
**Important**

When there are multiple Tagging Rules created, every single Tagging Rule will be evaluated. All the tags of the matching rules will be attached to the incoming incident. If you have more than 1 rule with the same "key" value in "Tag Mapping", the "value" of the tag will be that of the last matching rule’s Tag Mapping.\
\
For example:\
If you have 2 Tagging Rules for a Service:\
\- Rule 1 with Tag Mapping Environment: QA\
\- Rule 2 with Tag Mapping Environment: QA-INTER\
Say, if your "match" condition string is “healthcheckstatus-QA-INTER-TESTING“, tag "Environment:QA-INTER" is created. If you interchange the order of Rule 1 and Rule 2, tag "Environment:QA" is created instead.\
\
Therefore, always ensure that you write your Tagging Rules in the correct order for desired behaviour or try and make them as specific as possible.
{% endhint %}

#### Available Predefined Commands <a href="#available-predefined-commands" id="available-predefined-commands"></a>

The below commands can be used to create Tagging Rules.

**Add tags to incidents directly from your payload**

* If you already have tags being carried within your incident payload, you can add them as tags to your incidents as well without having to define _Tag Mappings_ again
* You can simply specify the values that need to be picked from the payload and added as tags to the incident (picked dynamically) rather than having to statically define these values as _Tag Mappings_

A. <mark style="color:red;">`addTag`</mark> - Add one specific tag from the payload

**General Format**&#x20;

<mark style="color:red;">`addTag( "<tag key name>", <value that needs to be picked from payload for the key>, "#<hexadecimal equivalent colour for tag>")`</mark>

* tag key: The key of the Tag label. Only letters and numbers are allowed. Anything else will be ignored
* payload selector or string: You can choose to set a tag value from the payload or you can set any custom string as the tag value
* color: You can set color as a valid HEX code. This is optional. If this parameter is omitted, the default colour - #0F61DD will be used

**Example** Below is an example payload for demonstration:

```
{
   "payload": {
      “message”: “Error rates higher than usual”,
      “description”: “HTTP Error rates for srv_90 is above 90 counts/hour”,
      "severity": “critical”
   }
}
```

Add a tag with **key**: <mark style="color:red;">`severity`</mark> and its **value** picked dynamically from the <mark style="color:red;">`severity`</mark> parameter in the payload

```
addTag( "severity", payload.severity, "#037916")
```

This will add the tag <mark style="color:red;">`severity: critical`</mark> with color <mark style="color:red;">`#037916`</mark> to your incident.

{% hint style="info" %}
**Note**

The "addTag" function always returns a "true" value. So, this can be chained with other logical operators to set multiple tags from the payload.
{% endhint %}

B. <mark style="color:red;">`addTags`</mark> - Add multiple tags from the payload

**General Format**&#x20;

<mark style="color:red;">`addTags(<object containing key-value pairs that should be added as tags from the payload>)`</mark>

**Example** Below is an example payload for demonstration:

```
{
   "payload": {
	   “message”: “Error rates higher than usual”,
      “description”: “HTTP Error rates for srv_90 is above 90 counts/hour”,
	   “tags” : {
         “severity”: “high”,
         “impact_level”: "5",
         “classification”: {
            “color”: “#FF0000”,
            “value”: “backend”
         }
 	   }
   }
}
```

Add all the tags contained within <mark style="color:red;">`tags`</mark> object in the payload

This will add the tags <mark style="color:red;">`severity:high`</mark> with default color <mark style="color:red;">`#0F61DD`</mark>, <mark style="color:red;">`impact_level:5`</mark> with default color <mark style="color:red;">`#0F61DD`</mark>, <mark style="color:red;">`classification:backend`</mark> with the color <mark style="color:red;">`#FF0000`</mark> to your incident.

{% hint style="info" %}
**Note**

The "addTags" function will add all the tags with the default colour only - #0F61DD.
{% endhint %}

{% hint style="warning" %}
**Important**

The UI-based Rule Builder method does not support any function calls like "addTag" and "addTags". In order to use them, you would have to opt for constructing the tagging expression in the Raw String method.
{% endhint %}

**Parse JSON content within the payload using **<mark style="color:red;">**`jsonPath`**</mark>** to add a tag**

**General Format**&#x20;

<mark style="color:red;">`jsonPath(<the JSON string that should be parsed for JSON content>, <"the parameter that needs to be picked from the parsed JSON object">)`</mark>

**Example** Below is an example payload:

```
{
   "payload": {  
      "Type" : "Notification",
      "MessageId" : "5966c484-5b37-58df",
      "TopicArn" : "arn:aws:sns:us-east-1:51:Test",
      "Message" : "{\"AlarmName\":\"Squadcast Testing - Ignore\",\"AlarmDescription\":\"Created from EC2 Console\"}"
   }
}
```

```
jsonPath(payload.Message, "AlarmName")
```

This will pick out the value <mark style="color:red;">`AlarmName`</mark> from the Message object in the payload. To add this extracted value as a tag to an incident, use it [within regex or addTag commands](broken-reference/).

**Parse HTML content within the payload using **<mark style="color:red;">**`htmlUnescape`**</mark>** to add a tag**

**General Format**&#x20;

<mark style="color:red;">`htmlUnescape(<the string that is encoded with HTML escape sequences>)`</mark>

**Example**&#x20;

Below is an example payload:

```
{
   "payload": {
      "id": "Memory available alert",
      "message": "Memory available alert from Chronograf for Test Macbook Pro",
      "details": "{&#34;Name&#34;:&#34;mem&#34;,&#34;TaskName&#34;:&#34;chronograf-v1-07cb04d0-f1f5-4a3f-afce-68ebb2b05d44&#34;,&#34;Group&#34;:&#34;nil&#34;,&#34;Tags&#34;:{&#34;host&#34;:&#34;Test-Macbook-Pro.local&#34;},&#34;ServerInfo&#34;:{&#34;Hostname&#34;:&#34;localhost&#34;,&#34;ClusterID&#34;:&#34;5359c160-521e-4a16-615efb7460cb&#34;,&#34;ServerID&#34;:&#34;47f1c611-85cf-bc42702fd259&#34;},&#34;ID&#34;:&#34;Memory available alert&#34;,&#34;Fields&#34;:{&#34;value&#34;:23.566293716430664},&#34;Level&#34;:&#34;CRITICAL&#34;,&#34;Time&#34;:&#34;2020-12-22T12:22:20Z&#34;,&#34;Duration&#34;:20000000000,&#34;Message&#34;:&#34;&#34;}\n",
      "time": "2020-12-22T12:22:20Z"
   }
}
```

```
htmlUnescape(payload.details)
```

This will parse HTML content <mark style="color:red;">`details`</mark> object from the payload. See the following section to know how this can be incorporated within a Tagging Rule.

**Incorporating multiple commands in a single rule**

**Example 1**&#x20;

Below is an example payload:

```
{
   "payload": {
      "id": "Memory available alert",
      "message": "Memory available alert from Chronograf for Test Macbook Pro",
      "details": "{&#34;Name&#34;:&#34;mem&#34;,&#34;TaskName&#34;:&#34;chronograf-v1-07cb04d0&#34;,&#34;Group&#34;:&#34;nil&#34;,&#34;Tags&#34;:{&#34;host&#34;:&#34;Test-Macbook-Pro.local&#34;},&#34;ServerInfo&#34;:{&#34;Hostname&#34;:&#34;localhost&#34;,&#34;ClusterID&#34;:&#34;5359c160-521e-4a16-615efb7460cb&#34;,&#34;ServerID&#34;:&#34;47f1c611-85cf-bc42702fd259&#34;},&#34;ID&#34;:&#34;Memory available alert&#34;,&#34;Fields&#34;:{&#34;value&#34;:23.566293716430664},&#34;Level&#34;:&#34;CRITICAL&#34;,&#34;Time&#34;:&#34;2020-12-22T12:22:20Z&#34;,&#34;Duration&#34;:20000000000,&#34;Message&#34;:&#34;&#34;}\n",
      "time": "2020-12-22T12:22:20Z",
      "source": "kapacitor"
   }
}
```

To add <mark style="color:red;">`TaskName`</mark> as a tag from the payload coming in from <mark style="color:red;">`Kapacitor`</mark>:

```
source == "kapacitor" && addTag("taskName", jsonPath(htmlUnescape(payload.details), "TaskName"), "#272822")
```

**Example 2**&#x20;

Below is an example payload:

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
  "source": "jira-plugin"
}
```

Assuming a case where _disk usage events need to be prioritised_:

* When the disk usage is greater than 90% - <mark style="color:red;">`critical`</mark> and <mark style="color:red;">`state`</mark> tag is <mark style="color:red;">`alerting`</mark>
* When the disk usage is between 60 - 90% - <mark style="color:red;">`high`</mark>
* When the disk usage is less than 60% - <mark style="color:red;">`low`</mark>

Create _3 rules_ with the following configuration

**Rules**

1.  Critical:

    ```
    payload.value  > 90 && jsonPath(payload.tags, "state") == "alerting"
    ```
2.  High:

    ```
    payload.value > 60 && payload.value < 90
    ```
3.  Low:

    ```
    payload.value < 60
    ```

#### C. Manual Method <a href="#c-manual-method" id="c-manual-method"></a>

Associate a tag while creating an incident manually from the Incident Dashboard

![](../.gitbook/assets/tagging\_6.png)

### Deleting Tagging Rules <a href="#deleting-tagging-rules" id="deleting-tagging-rules"></a>

**(1)** Click on the Tagging Rule for a selected Service

**(2)** Click on the **bin** icon to delete that rule and click on **Save**

![](../.gitbook/assets/tagging\_7.png)

Use **+Update Tags** within an incident to update tags for a specific incident

![](../.gitbook/assets/tagging\_8.png)

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** Where can I see the tags associated with incidents?

You will be able to clearly view tags associated with incidents in the[ Incident List.](../incident-list/incident-list-view.md)

![](../.gitbook/assets/tagging\_9.png)

**(2)** Can I add tags from the payload automatically?

Yes, you can. Refer [here](broken-reference/) for more information and examples.

**(3)** Can I create OR rules?

Yes, you can. The evaluation between different Tagging Rules is OR. Add multiple Tagging Rules to enable OR evaluation.

**(4)** Can a Tagging Rule be created for a specific alert source?

By default, any rule added for a Service will be executed for all its active alert source integrations. You can choose to isolate Tagging Rules for specific alert sources based on the <mark style="color:red;">`source`</mark> field in the payload visible on the right panel.

Example:

```
source == "api" && (<your_tagging_rule>)
```

This will ensure that this Tagging Rule will only be active for incidents triggered via that alert source for the service. This rule will not function for any other alert source.

**(5)** While adding a Tagging Rule, is the _search string_ in the rule case sensitive?

Yes, that is correct. For example, if your seach string is “ALERT” and your payload does not contain “ALERT” but contains “Alert”, this will not be matched. Your search string should be “Alert”.

**(6)** What kind of regex can be used to write custom rules?

The rule engine supports expressions with parameters, arithmetic, logical, and string operations. You can also check [this](https://regex101.com/) out to get an idea of all the expression types accepted in Squadcast. Please do your regex [here](https://regex101.com/) against <mark style="color:red;">`Golang`</mark> flavour as shown in the screenshot below and then, set them up in Squadcast:

![](../.gitbook/assets/de-duplication\_9.png)

**(7)** I have configured multiple rules for a particular Service. Can I search through the configured rules to find the rule I am looking for?

Yes, that is doable. You will notice a **Search** option on the left-top of the rules modal. You can type in a word you recall from the rule itself or search by the mapped tags within the rules. Any matching results will yield the **narrowed-down** set of rules.

![](<../.gitbook/assets/automation-rules-search-1 (2).png>)
