# Configure and Monitor your SLOs

With Squadcast, you can define and monitor Service Level Objects for your services.

Before you begin to define your SLO, you should have an expectation of what percent of your SLI (availability, latency, etc.) is needed to pass the SLO. For example, you may want your service to be available 99.99% of the time to pass the SLO. In this case, 99.99% is the _Target SLO_ and “availability” is your _SLI_.

### Creating New SLO <a href="#creating-new-slo" id="creating-new-slo"></a>

Navigate to **SLO** from the left sidebar. To create a new SLO, click on **+Create New SLO** button on the top right.

#### Define SLO <a href="#define-slo" id="define-slo"></a>

You begin by defining your SLO.

1. Enter the SLO Name of your choice (this needs to be unique across SLOs)
2. Enter the SLO Description detailing out specifics of the SLO
3. Enter Tags (key-value pairs) specifying information such as the Owner, Environment and Type of SLO

You can additionally add your own tags by clicking the **+Add Tag** button.

\
Once done, click on **Next** to Configure SLO.

#### Configure SLO <a href="#configure-slo" id="configure-slo"></a>

1. Under the **Services Associated with this SLO** tab, you can select multiple Services to link it to the SLO. Only incidents from these linked Services can then be mapped to the SLO
2. Enter the **SLIs that affect the SLO**. There could be one or more SLIs - like availability, response time, etc - that map to this SLO
3. Enter the percentage or ratio under **Target SLO in %**. This sets the target percentage to define compliance
4. **Error Budget** is auto-calculated based on the values entered for target SLO and duration. It is calculated in minutes and cannot be edited
5. Enter the **Duration** for this SLO, by choosing between **Rolling Period** or **Fixed Duration** (Calendar Duration)

* Under **Rolling**, you can select the period in days. This option is used when you want the SLO calculated continuously for a defined number of days (for example, continuously over a 7 day period). This can be a maximum of 90 days.
* Under **Fixed Duration**, you can select the start and end dates from the drop-down. This option is used when the SLO has to be calculated over a fixed duration - for example, over one quarter at a time. The fixed duration can be a maximum of one year.\
  Once done, click on **Next** to configure Error Budget Policy.

#### Error Budget Policy <a href="#error-budget-policy" id="error-budget-policy"></a>

The **Error Budget Policy** defines the conditions based on which to notify one or more Users or Squads or when incidents have to be created when a condition is breached.

Choose the conditions you want to be alerted for, out of the following options:

* Alert when there is a breach of allocated **Error Budget**
* Alert when there is an **Unhealthy Burn Rate**. An unhealthy burn rate is determined when the error budget is burning faster than what’s expected. For example, for an SLO of 99.99% over the course of a year, the error budget works out to be about 52 mins 35 seconds - or approximately about 4 mins 30 sec per month. If the error budget is being burnt faster than than, then its considered unhealthy
* Alert when the number of **False Positives** exceeds the set limit
* Alert when the **Error Budget** decreases below the set limit

Choose the mode of delivery of the alerts

* **Email** Alerts, wherein an email notification is sent to the Users or Squads you specify
* **Incident** Alerts, wherein an alert is created for the specified Service

\
Once done, click on **Create**, and your SLO is created!

Once created, you can access all your SLOs for the current Team from the SLO dashboard.

The SLO list view shows information for each SLO, including:

| Field                  | Description                                                                       |
| ---------------------- | --------------------------------------------------------------------------------- |
| Target SLO             | Shows the percentage or ratio to target, which is the target value for compliance |
| Current SLO            | Shows the current historical compliance with the SLO                              |
| Allocated Error Budget | Shows the allocated Error Budget for the SLO (in minuctes)                        |
| Remaining Error Budget | Shows the remaining Error Budget for the SLO (in minutes)                         |
| SLO Health             | Indicates the health of the SLO, either as Healthy or Needs Attention             |
| Status                 | Indicates whether the SLO is Active or Inactive                                   |
| Incidents Reported     | Indicates the # of incidents reported **+** the false positives for this SLO      |
| Tags                   | Indicates the tags associated with the SLO                                        |

### SLO Detail Page <a href="#slo-detail-page" id="slo-detail-page"></a>

To view the details of a particular SLO, select the SLO from the SLO list in the SLO dashboard.

### Marking an Incident as False Positive <a href="#marking-an-incident-as-false-positive" id="marking-an-incident-as-false-positive"></a>

This is useful if an incident was previously marked as one that affects an SLO and has been subsequently determined that it does not. This acts like an “undo” button.

You can mark an incident as False Positive in one of two ways:

Through the SLO Details page, checkmark the incident(s) -> Click on Mark as **False Positive** button

Alternatively, go to the incident’s Details page -> Click on **Mark as False Positive** in the **Incident Affects SLO** tab

### Deleting an SLO <a href="#deleting-an-slo" id="deleting-an-slo"></a>

To delete an SLO, click on the icon on the right of the SLO from the SLO list, and click on the **Delete** icon, as shown in the image below.

### FAQs <a href="#faqs" id="faqs"></a>

Please refer to the Frequently Asked Questions below that might help you fix any issues/answer your queries.

#### 1. Can I delete services associated with an SLO? <a href="#1-can-i-delete-services-associated-with-an-slo" id="1-can-i-delete-services-associated-with-an-slo"></a>

Yes, you can delete a service associated with an SLO, the SLO and its Incidents will still be intact.

#### 2. How is the Error Budget calculated? <a href="#2-how-is-the-error-budget-calculated" id="2-how-is-the-error-budget-calculated"></a>

An error budget is 1 minus the SLO of the service. A 99.9% SLO service has a 0.1% error budget. If our service receives 1,000,000 requests in four weeks, a 99.9% availability SLO gives us a budget of 1,000 errors over that period.

#### 3. How is the Burn Rate calculated? <a href="#3-how-is-the-burn-rate-calculated" id="3-how-is-the-burn-rate-calculated"></a>

* First we calculate error budget allocated for a day. (for eg: if slo is 99.99% for an year, you get 55.5min/365 error budget for a day)
* Then, we fetch total error budget spent till today’s date
* Subsequently, we see how many days its been since the slo started and later check if the user has consumed more error budget than they were suppoed to, to calculate the burn rate

#### 4. What determines a Healthy or Unhealthy SLO? <a href="#4-what-determines-a-healthy-or-unhealthy-slo" id="4-what-determines-a-healthy-or-unhealthy-slo"></a>

Healthy or unhealthy is based on how rapidly the error budget is getting depleted. Slo burn rate indicates how fast your error budget is getting consumed relative to your SLO’s target length.

For example, if have 99.9% target for a month, then you will get 43.12 min of downtime, Which means you can burn 1.43 Min(43.12/30) of error budget every day. If you burn a total of 30 min of error budget within the first 10 days of your SLO duration then it will turn to _Needs Attention_ (unhealthy).

So the SLO which is Healthy today is because it’s consumed less error budget than allocated for the days its been since the SLO started.

#### 5. Can I automatically associate incidents with an SLO? <a href="#5-can-i-automatically-associate-incidents-with-an-slo" id="5-can-i-automatically-associate-incidents-with-an-slo"></a>

We’re working on something that can help you do this in the near future.
