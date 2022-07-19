---
description: >-
  Use Incident Status Based Deduplication to deduplicate all alerts to an
  existing open incident for a Service
---

# Incident Status Based Deduplication

Incident Status Based Deduplication works on the logic that all alerts that come in for a Service are related to the same issue. So, if there is an open incident for a Service - that is, the incident is in the <mark style="color:red;">`Triggered`</mark> or <mark style="color:red;">`Acknowledged`</mark> state, **all** incidents that come in for this Service will get deduplicated against the existing, open incident within the specified time window.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Deduplication Rules).

### Enabling the Incident Status-Based Deduplication <a href="#enabling-the-incident-status-based-deduplication" id="enabling-the-incident-status-based-deduplication"></a>

#### Enabling this while creating a new Service <a href="#enabling-this-while-creating-a-new-service" id="enabling-this-while-creating-a-new-service"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

1\. Click on **Services** in the primary navigation. Then, click on **Add Service** to create a new Service

Here, in addition to the required information, **enable the checkbox** with the information message and choose the appropriate time window for which you would like this Deduplication Rule to hold true. This can be enabled/modified even after the Service is created.

{% hint style="info" %}
The maximum time allowed for deduplication is **48 hours**.
{% endhint %}

Finally, click on **Save** to create the Service.

{% hint style="info" %}
**Note**

By default, Incident Status Based Deduplication checkbox in the Service creation modal will remain unchecked.
{% endhint %}

2\. After enabling the checkbox and creating the Service, if you click on the **More options** icon for the Service

![](<../../.gitbook/assets/status-based-deduplication\_3 (1).png>)

Select **Deduplication Rules**, and you will be able to see the Deduplication Rule added for the same.

![](../../.gitbook/assets/status-based-deduplication\_4.png)

#### Enabling this for an existing Service <a href="#enabling-this-for-an-existing-service" id="enabling-this-for-an-existing-service"></a>

{% hint style="info" %}
**Note**

If you leave the Incident Status Based Deduplication box unchecked at the time of Service creation and want to add this rule later, you can copy and paste the rule below and change the Rule Execution Priority accordingly.\
<mark style="color:red;">`past_incident.is_suppressed == false`</mark> with the appropriate deduplication time window.
{% endhint %}

### FAQs <a href="#faqs" id="faqs"></a>

1\. I have added the Deduplication Rule <mark style="color:red;">`past_incident.is_suppressed == false`</mark> manually to an existing Service to deduplicate all alerts against any open incident for the Service. Nevertheless, I do not see Incident Status Based Deduplication taking place as expected. What am I missing?

Once the Deduplication Rule <mark style="color:red;">`past_incident.is_suppressed == false`</mark> is added manually to an existing Service, please move the rule <mark style="color:red;">`up`</mark> or <mark style="color:red;">`down`</mark> based on the Rule Execution Priority you wish to have. If you do not want any of your other Deduplication Rules to be executed for the Service, move the newly added Deduplication Rule to the top of the list of rules.

![](../../.gitbook/assets/status-based-deduplication\_5.png)
