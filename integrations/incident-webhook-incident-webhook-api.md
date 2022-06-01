# Incident Webhook (Incident Webhook/API)

Send events to create incidents in Squadcast using Incident Webhook (generic incoming Webhook)

This document will help you configure Incident Webhook to route alerts from monitoring tools or your internal (bespoke) systems into Squadcast. Incident Webhook can do both, trigger and resolve incidents in Squadcast, through HTTP POST requests.

Route detailed monitoring alerts coming in via Incident Webhook to the right users in Squadcast.

### How to configure Incident Webhook <a href="#how-to-configure-incident-webhook" id="how-to-configure-incident-webhook"></a>

#### In Squadcast: Using Incident Webhook as an Alert Source <a href="#in-squadcast-using-incident-webhook-as-an-alert-source" id="in-squadcast-using-incident-webhook-as-an-alert-source"></a>

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

**(2)** Search for **Incident Webhook** from the Alert Source drop-down and copy the Webhook URL. Use this Webhook URL endpoint to send `HTTP POST` requests

The body of the POST request should contain the details of your incident in the following format:

```
{
  "message": "This will be the incident message",
  "description": "This will be the incident description",
  "tags" : {
    "tagname1":"Tag value#1",
     "tagname2":"Tag value#2",
     "tagname3": {
       "color": "Valid HTML HEX Colour Notation goes here",
       "value":"Tag value#3"
     }
  },
  "status": "trigger",
  "event_id": "6"
}
```

### Event Identification and Resolution <a href="#event-identification-and-resolution" id="event-identification-and-resolution"></a>

This section will give you an understanding of how one can associate alerts with Squadcast incidents and resolve them with an API call.

#### Typical Incident JSON <a href="#typical-incident-json" id="typical-incident-json"></a>

```
{
  "message": "This will be the incident message",
  "description": "This will be the incident description",
  "status": "trigger",
  "event_id": "6"
}
```

This triggers an incident and associates the incident with the `event_id` value as specified. This `event_id` can be used to resolve the above created incident with an API call.

To resolve an incident, a JSON with the format as shown below should be sent.

```
{
  "status": "resolve",
  "event_id": "6"
}
```

* The `status` field should be set to value `"resolve"`
* The associated `event_id` should also be sent along with this

### Add a Tag From directly Incident JSON <a href="#add-a-tag-from-directly-incident-json" id="add-a-tag-from-directly-incident-json"></a>

This section will give you an understanding of how you can add tags to an incident straight from the Incident JSON using the Incident Webhook.

#### Typical Incident JSON: <a href="#typical-incident-json-1" id="typical-incident-json-1"></a>

```
{
   "message":"This will be the incident message",
   "description": "This will be the incident description",
   "tags": {
     "tagname1":"Tag value#1",
     "tagname2":"Tag value#2",
     "tagname3": {
       "color": "Valid HTML HEX Colour Notation goes here",
       "value":"Tag value#3"
     }
   }
}
```

#### Example 1: Using `tags` to set _Severity_ for the incident <a href="#example-1-using-tags-to-set-severity-for-the-incident" id="example-1-using-tags-to-set-severity-for-the-incident"></a>

```
{
  	"message": "Error rates higher than usual",
    "description": "HTTP Error rates for srv_90 is above 90 counts/hour",
    "tags": {
    	"severity": "high"
    }
}
```

To specify a colour explicitly for `tags`:

```
{
	"message": "Error rates higher than usual",
  "description": "HTTP Error rates for srv_90 is above 90 counts/hour",
	"severity": {
  	"colour": "#FF0000",
  	"value":"backend"
  }
}
```

#### Example 2: Adding different tags to an incident <a href="#example-2-adding-different-tags-to-an-incident" id="example-2-adding-different-tags-to-an-incident"></a>

```
{
	"message": "Error rates higher than usual",
  "description": "HTTP Error rates for srv_90 is above 90 counts/hour",
	"tags" : {
   	"priority": "P1",
	  "impact_level": 5,
   	"classification": {
    	"color":"#FF0000",
     	"value":"backend"
     }
 	}
 }
```
