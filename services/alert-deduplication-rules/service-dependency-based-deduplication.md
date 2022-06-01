# Service Dependency Based Deduplication

Deduplicate incoming alerts for a Service against the latest open incident of its dependent Service(s)

Service Dependency Based Deduplication works on the logic that the incidents coming in for a Service and its dependencies have a related cause.

It is most likely the case where, when one Service has an incident, its dependent Service(s) may also have incidents and hence, you will be notified for the incident only once. _This helps control unnecessary alert noise and notification fatigue during critical outages_.

Defining dependencies between Services also helps Squadcast understand the relationship between your actual systems.

To understand this better, let us consider 3 Services: _Service A_, _Service B_ and _Service C_.

If _Service A_ is `dependent on` _Service B_ and _Service C_, then:

* **Dependent Service**: _Service A_
* **Dependency Service(s)**: _Service B_, _Service C_

Let’s say, _Service B_ has an open incident at _time x_ and _Service C_ has an open incident at _time x+1_. Now, _Service A_ receives an incident. This incident for _Service A_ gets deduplicated with the **latest** open incident of its depenedency Service(s) - i.e., with the open incident for _Service C_, in this case.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* The User Role associated with the user in the Team must have required permissions to manage Services (ability to manage Deduplication Rules).

### Adding a Service Dependency <a href="#adding-a-service-dependency" id="adding-a-service-dependency"></a>

Ensure that the right Team is chosen from the team picker on the top of the screen.

**(1)** Click on **Services** in the primary navigation

**(2)** To add a dependency where, _Service A_ `is dependent on` Service B, for _Service A_, click on **More options** icon and select **Dependencies**

**(3)** Search for _Service B_, select it and click on **Save**

In this example, we have considered `Backend Prometheus Service` and `Translations` Services as dependencies of the `Payment Portal` Service.

This means that the `Payment Portal` Service is dependent on `Backend Prometheus Service` and `Translations`.

Once you have defined the Service Dependencies, you can set a Service Dependency Based Deduplication rule which would deduplicate all incoming alerts for the chosen Service against the latest open incident of its Service Dependencies.

To do so:

**(1)** For the Service that has its dependencies defined, click on **More** and select **Deduplication Rules**

**(2)** For the Deduplication Rule that you want checked and applied for Service Dependency Based Deduplication, simply enable the checkbox **If this service and a service it depends on both have an incident, alert only once**.

**Note:** This checkbox for every Deduplication Rule is disabled by default.

### Enabling Service Dependency Based Deduplication for a Specific Service Dependency <a href="#enabling-service-dependency-based-deduplication-for-a-specific-service-dependency" id="enabling-service-dependency-based-deduplication-for-a-specific-service-dependency"></a>

In cases where you would like Squadcast to consider just one of the many dependencies for a Service for Service Dependency Based Deduplication, you can follow the method below.

Along with enabling the Service Dependency checkbox as shown above, you will need to add the below condition to the rule:

`past_incident.service == <slug_of_the_particular_dependency_service>`

### FAQs <a href="#faqs" id="faqs"></a>

**(1)** Where can one find the `slug` of a Service?

The `slug` of a Service is displayed on the Service card as shown below.

**(2)** Can I set up dependencies between Services that are in 2 different Teams?

No, you can set up dependencies only within Services for a given Team and not across Teams.
