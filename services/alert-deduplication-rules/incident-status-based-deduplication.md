# Incident Status Based Deduplication

Use Incident Status Based Deduplication to deduplicate all alerts to an existing open incident for a Service

Incident Status Based Deduplication works on the logic that all alerts that come in for a Service are related to the same issue. So, if there is an open incident for a Service - that is, incident is in the `Triggered` or `Acknowledged` state, **all** incidents that come in for this Service will get deduplicated against the existing, open incident within the specified time window.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Deduplication Rules).

### Enabling the Incident Status Based Deduplication <a href="#enabling-the-incident-status-based-deduplication" id="enabling-the-incident-status-based-deduplication"></a>

#### Enabling this while creating a new Service <a href="#enabling-this-while-creating-a-new-service" id="enabling-this-while-creating-a-new-service"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

**(1)** Click on **Services** in the primary navigation. Then, click on **Add Service** to create a new Service

Here, in addition to the required information, **enable the checkbox** with the information message and choose the appropriate time window for which you would like this Deduplication Rule to hold true. This can be enabled/modified even after the Service is created.

**Note:** The maximum time allowed for deduplication is **48 hours**.

Finally, click on **Save** to create the Service.

**(2)** After enabling the checkbox and creating the Service, if you click on the **More options** icon for the Service

Select **Deduplication Rules**, you will be able to see the Deduplication Rule added for the same.

#### Enabling this for an existing Service <a href="#enabling-this-for-an-existing-service" id="enabling-this-for-an-existing-service"></a>

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** I have added the Deduplication Rule `past_incident.is_suppressed == false` manually to an existing Service to deduplicate all alerts against any open incident for the Service. Nevertheless, I do not see Incident Status Based Deduplication taking place as expected. What am I missing?

Once the Deduplication Rule `past_incident.is_suppressed == false` is added manually to an existing Service, please move the rule `up` or `down` based on the Rule Execution Priority you wish to have. If you do not want any of your other Deduplication Rules to be executed for the Service, move the newly added Deduplication Rule to the top of the list of rules.
