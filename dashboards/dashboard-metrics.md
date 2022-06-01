# Dashboard Metrics

What do these metrics mean and how are the dashboard metrics calculated?

Squadcast dashboard is the first screen that your Web App and Mobile App open into. This document will guide you through how these metrics are calculated and what they mean.

First, select a Team using the team picker on the top.

Incident states metrics gives you a single view calculation of the number or volume of incidents in each of the respective states on Squadcast.

#### Triggered <a href="#triggered" id="triggered"></a>

An incident is considered to be in the **triggered** state before any user responds to the incident notification. Once an incident is triggered it will notify the on-call user(s) based on their notification rules. This also means that the incident is in the **open** state.

#### Acknowledged <a href="#acknowledged" id="acknowledged"></a>

An incident is considered to be in the **acknowledged** state when a user has acknowledged an incident and is working on resolving it.

#### Resolved <a href="#resolved" id="resolved"></a>

An incident considered **resolved** when the user has fixed the issue and they want the incident to be closed. Once an incident is resolved, no additional notifications will be sent and the incident cannot be opened again. This is one of the two final incident states in Squadcast.

#### Suppressed <a href="#suppressed" id="suppressed"></a>

All incidents that evaluate to be true for any of the Supression Rules configured for a Service (or incidents that come in for the Service when it is under maintenance) will automatically go into the **suppressed** state. This, and **resolved** are the two final states in Squadcast.

### Response Metrics <a href="#response-metrics" id="response-metrics"></a>

Response metrics indicate the time taken to acknowledge and resolve a triggered incident. Typically, response metrics are used as a baseline to improve your incident response processes.

#### MTTA <a href="#mtta" id="mtta"></a>

Mean Time To Acknowledge is the average time taken to acknowledge incidents. When the dashboard is toggled to **Yours**, the incident metrics summary shows your MTTA and when it is toggled to **All**, the MTTA for the whole Team is shown.

Note: The MTTA is calculated as a separate metric for every Team that you are a part of in Squadcast.

#### MTTR <a href="#mttr" id="mttr"></a>

Mean Time To Resolve is the average time taken to resolve incidents. When the dashboard is toggled to **Yours**, the incident metrics summary shows your MTTR and when it is toggled to **All**, the MTTR for the whole Team is shown.

Note: The MTTR is calculated as a separate metric for every Team that you are a part of in Squadcast.

### Percentage calculation for each metric <a href="#percentage-calculation-for-each-metric" id="percentage-calculation-for-each-metric"></a>

You will notice a percentage calculation under each of these metrics with an arrow that denotes if there is an increase or decrease in volume/performance.

This percentage indicates a comparative calculation of the performance/volume of the metric in the selected time period versus the performance/volume of the metric for the same time duration in the past.

That is, if you have chosen the `Last Week` dashboard view, the percentages shown will be calculated this way:

* Incident States Percentages = (Total number of incidents in each state this week / Total number of incidents from last week that are still in the respective states) \* 100
* Response Metrics Percentages = (MTTR/MTTA recorded for this week / MTTR/MTTA recorded for last week) \* 100
