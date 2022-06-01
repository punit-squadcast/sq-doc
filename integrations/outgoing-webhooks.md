# Outgoing Webhooks

Use outbound webhooks to send incident information from Squadcast into other systems

Webhooks allow you to connect a platform that you manage (either an API that you create by yourself, or a third party service) to a stream of future _events_.

Setting up a webhook on Squadcast enables you to receive information (referred to as _events_) from Squadcast as they happen. This can help you avoid continuously polling Squadcast’s REST APIs or manually checking the Squadcast web/mobile application for desired information.

The rest of this document will explain how you can set up these webhooks, as well as list the events that can be sent to your webhook destinations.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

Only the **Account Owner** and **Users** with the `Manage Webhook` permission will be able to _enable_, _disable_ and _manage_ webhooks in Squadcast.

If you do not have access to this feature, please contact your administrator to give you the right permissions for it.

Navigate to **Settings** > **Permissions** and enable the checkbox under **Webhooks** for the desired users.

### Setup a Webhook <a href="#setup-a-webhook" id="setup-a-webhook"></a>

**(1)** Navigate to **Settings > Webhooks**. Click on the **+** icon

**(2)** Enter a suitable name and click on **Create**

You can now proceed to configuring the newly created webhook.

### Supported Events <a href="#supported-events" id="supported-events"></a>

The webhook that you have configured can be triggered for certain events occurring in Squadcast. At the moment, the following incident-related events are supported:

* [Incident `triggered`](broken-reference)
* [Incident `reassigned`](broken-reference)
* [Incident `acknowledged`](broken-reference)
* [Incident `resolved`](broken-reference)

You can choose multiple triggers for a webhook. Information is sent to the provided URLs if any of the triggers match.

If your use-case requires more Squadcast events to be supported, please reach out to our Support team with details of the same.

### Communication Protocol for Webhooks <a href="#communication-protocol-for-webhooks" id="communication-protocol-for-webhooks"></a>

A webhook is called whenever the configured events occur in Squadcast.

A webhook call is made using the `HTTP POST` method to the URL(s) that were added when the webhook was configured, with a body that is encoded using `JSON`.

Squadcast expects that the server that responds to the webhook to return a `2xx` response code upon success. If a non-2xx response is received, **Squadcast will retry the request for a maximum of 3 times**.

### URLs and Headers <a href="#urls-and-headers" id="urls-and-headers"></a>

We support the addition of multiple URL endpoints, with `POST`, `PUT` and `PATCH` methods. Incident payloads will be sent to all the URL endpoints that are added. You can also configure _additional headers_. These headers will get attached to all the webhook calls that will be made based on this configuration.

### Filters <a href="#filters" id="filters"></a>

You can filter on top of events from the **Services** and **Alert Sources** drop-downs, either by having an individual expression or a combination of expressions/expression groups.

### Logs <a href="#logs" id="logs"></a>

Once the webhook call has been made, you can view the logs for it in the **Logs** tab.

Click on the expand icon on any of the individual logs to view the payload that has been sent across.

### Additional Settings <a href="#additional-settings" id="additional-settings"></a>

Configure the **Name**, **Description** and **Failure Notification email** in the **Settings** tab. This is particularly helpful when you (or an administrator) would want to be notified for webhook-related failures.

### Use-cases for Webhooks <a href="#use-cases-for-webhooks" id="use-cases-for-webhooks"></a>

Webhooks can be leveraged in various scenarios. We have put together some common use-cases.

They are:

* Building internal custom dashboards to visualize or analyze incidents
* Sending data to ticketing tools, such as Zendesk, Freshdesk, Shortcut, Asana, etc.
* Sending events to communication apps, such as Slack, MS Teams, etc.
* Alerting when a workflow is disrupted- then use the API to re-run the workflow
* Triggering internal notification systems to alert people when incidents are created/resolved
* Building your own automation plug-ins and tools

### Sample Webhook Payloads <a href="#sample-webhook-payloads" id="sample-webhook-payloads"></a>

#### Incident Triggered <a href="#incident-triggered" id="incident-triggered"></a>

```
{
  "id": "61c075f78589dca75fdb2f44",
  "event_type": "incident_triggered",
  "organization": {
    "id": "609b8e9978d2770008db8638",
    "name": "My Org"
  },
  "service": {
    "id": "61518af788792704697f3da0",
    "name": "email trigger",
    "slug": "email-trigger"
  },
  "alert_source": {
    "id": "5fae6d03ef87d3896aa92ad1",
    "type": "Squadcast UI",
    "short_name": "squadcastui"
  },
  "message": "CPU Throttling: Over 90% of cpu is being utilized",
  "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
  "status": "triggered",
  "created_at": "2021-12-20T12:24:23.11Z",
  "assigned_to": {
    "id": "609b8e9e78d2770008db8639",
    "name": "SRE and Devops Escalation Policy",
    "type": "escalationpolicy"
  },
  "tags": {
    "severity": {
      "value": "critical",
      "color": "#FF0A49"
    }
  },
  "timeline": [
    {
      "action": "triggered",
      "assigned_to": "escalationpolicy",
      "name": "SRE and Devops Escalation Policy",
      "time": "2021-12-20T12:24:23.077Z"
    }
  ],
  "analytics": {},
  "event_count": 1,
  "event_payload": {
    "assignee": {
      "id": "609b8e9e78d2770008db8639",
      "type": "escalationpolicy"
    },
    "created_by": "603360ce3aeae4de2b6edec1",
    "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
    "message": "CPU Throttling: Over 90% of cpu is being utilized",
    "tags": {
      "severity": {
        "color": "#FF0A49",
        "value": "critical"
      }
    }
  },
  "owner": {
    "id": "6129ac09518568defa927536",
    "name": "Default Team",
    "type": "team",
    "is_default_team": true,
    "team_description": "Default team"
  },
  "manually_created_by": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "David Brent",
    "email": "[email protected]"
  }
}
```

#### Incident Reassigned <a href="#incident-reassigned" id="incident-reassigned"></a>

```
{
  "id": "61c075f78589dca75fdb2f44",
  "event_type": "incident_reassigned",
  "organization": {
    "id": "609b8e9978d2770008db8638",
    "name": "My Org"
  },
  "service": {
    "id": "61518af788792704697f3da0",
    "name": "email trigger",
    "slug": "email-trigger"
  },
  "alert_source": {
    "id": "5fae6d03ef87d3896aa92ad1",
    "type": "Squadcast UI",
    "short_name": "squadcastui"
  },
  "message": "CPU Throttling: Over 90% of cpu is being utilized",
  "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
  "status": "triggered",
  "created_at": "2021-12-20T12:24:23.11Z",
  "assigned_to": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "Micheal Scott",
    "type": "user"
  },
  "tags": {
    "severity": {
      "value": "critical",
      "color": "#FF0A49"
    }
  },
  "timeline": [
    {
      "action": "triggered",
      "assigned_to": "escalationpolicy",
      "name": "SRE and Devops Escalation Policy",
      "time": "2021-12-20T12:24:23.077Z"
    },
    {
      "action": "reassigned",
      "assigned_to": "user",
      "name": "Micheal Scott",
      "time": "2021-12-21T04:59:18.173Z"
    }
  ],
  "analytics": {
    "tta": {
      "time": 11475,
      "user_id": "603360ce3aeae4de2b6edec1",
      "escalation_policy_id": "609b8e9e78d2770008db8639"
    }
  },
  "event_count": 1,
  "event_payload": {
    "assignee": {
      "id": "609b8e9e78d2770008db8639",
      "type": "escalationpolicy"
    },
    "created_by": "603360ce3aeae4de2b6edec1",
    "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
    "message": "CPU Throttling: Over 90% of cpu is being utilized",
    "tags": {
      "severity": {
        "color": "#FF0A49",
        "value": "critical"
      }
    }
  },
  "owner": {
    "id": "6129ac09518568defa927536",
    "name": "Default Team",
    "type": "team",
    "is_default_team": true,
    "team_description": "Default team"
  },
  "manually_created_by": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "David Brent",
    "email": "[email protected]"
  }
}
```

#### Incident Acknowledged <a href="#incident-acknowledged" id="incident-acknowledged"></a>

```
{
  "id": "61c075f78589dca75fdb2f44",
  "event_type": "incident_acknowledged",
  "organization": {
    "id": "609b8e9978d2770008db8638",
    "name": "My Org"
  },
  "service": {
    "id": "61518af788792704697f3da0",
    "name": "email trigger",
    "slug": "email-trigger"
  },
  "alert_source": {
    "id": "5fae6d03ef87d3896aa92ad1",
    "type": "Squadcast UI",
    "short_name": "squadcastui"
  },
  "message": "CPU Throttling: Over 90% of cpu is being utilized",
  "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
  "status": "acknowledged",
  "created_at": "2021-12-20T12:24:23.11Z",
  "assigned_to": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "Micheal Scott",
    "type": "user"
  },
  "tags": {
    "severity": {
      "value": "critical",
      "color": "#FF0A49"
    }
  },
  "timeline": [
    {
      "action": "triggered",
      "assigned_to": "escalationpolicy",
      "name": "SRE and Devops Escalation Policy",
      "time": "2021-12-20T12:24:23.077Z"
    },
    {
      "action": "reassigned",
      "assigned_to": "user",
      "name": "Micheal Scott",
      "time": "2021-12-21T04:59:18.173Z"
    },
    {
      "action": "acknowledged",
      "assigned_to": "user",
      "name": "Micheal Scott",
      "time": "2021-12-21T05:05:23.129Z"
    }
  ],
  "analytics": {
    "tta": {
      "time": 11475,
      "user_id": "603360ce3aeae4de2b6edec1",
      "escalation_policy_id": "609b8e9e78d2770008db8639"
    }
  },
  "event_count": 1,
  "event_payload": {
    "assignee": {
      "id": "609b8e9e78d2770008db8639",
      "type": "escalationpolicy"
    },
    "created_by": "603360ce3aeae4de2b6edec1",
    "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
    "message": "CPU Throttling: Over 90% of cpu is being utilized",
    "tags": {
      "severity": {
        "color": "#FF0A49",
        "value": "critical"
      }
    }
  },
  "owner": {
    "id": "6129ac09518568defa927536",
    "name": "Default Team",
    "type": "team",
    "is_default_team": true,
    "team_description": "Default team"
  },
  "manually_created_by": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "David Brent",
    "email": "[email protected]"
  }
}
```

#### Incident Resolved <a href="#incident-resolved" id="incident-resolved"></a>

```
{
  "id": "61c075f78589dca75fdb2f44",
  "event_type": "incident_resolved",
  "organization": {
    "id": "609b8e9978d2770008db8638",
    "name": "My Org"
  },
  "service": {
    "id": "61518af788792704697f3da0",
    "name": "email trigger",
    "slug": "email-trigger"
  },
  "alert_source": {
    "id": "5fae6d03ef87d3896aa92ad1",
    "type": "Squadcast UI",
    "short_name": "squadcastui"
  },
  "message": "CPU Throttling: Over 90% of cpu is being utilized",
  "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
  "status": "resolved",
  "created_at": "2021-12-20T12:24:23.11Z",
  "assigned_to": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "Micheal Scott",
    "type": "user"
  },
  "tags": {
    "severity": {
      "value": "critical",
      "color": "#FF0A49"
    }
  },
  "timeline": [
    {
      "action": "triggered",
      "assigned_to": "escalationpolicy",
      "name": "SRE and Devops Escalation Policy",
      "time": "2021-12-20T12:24:23.077Z"
    },
    {
      "action": "reassigned",
      "assigned_to": "user",
      "name": "Micheal Scott",
      "time": "2021-12-21T04:59:18.173Z"
    },
    {
      "action": "acknowledged",
      "assigned_to": "user",
      "name": "Micheal Scott",
      "time": "2021-12-21T05:05:23.129Z"
    },
    {
      "action": "resolved",
      "assigned_to": "user",
      "name": "Micheal Scott",
      "time": "2021-12-21T05:11:34.219Z"
    }
  ],
  "analytics": {
    "tta": {
      "time": 11475,
      "user_id": "603360ce3aeae4de2b6edec1",
      "escalation_policy_id": "609b8e9e78d2770008db8639"
    },
    "ttr": {
      "time": 60431142,
      "user_id": "603360ce3aeae4de2b6edec1",
      "escalation_policy_id": "609b8e9e78d2770008db8639"
    }
  },
  "event_count": 1,
  "event_payload": {
    "assignee": {
      "id": "609b8e9e78d2770008db8639",
      "type": "escalationpolicy"
    },
    "created_by": "603360ce3aeae4de2b6edec1",
    "description": "Over 90% of cpu is being utilized from past 2 hours which is a drastic increase from before. Please checkout the metrics.",
    "message": "CPU Throttling: Over 90% of cpu is being utilized",
    "tags": {
      "severity": {
        "color": "#FF0A49",
        "value": "critical"
      }
    }
  },
  "owner": {
    "id": "6129ac09518568defa927536",
    "name": "Default Team",
    "type": "team",
    "is_default_team": true,
    "team_description": "Default team"
  },
  "manually_created_by": {
    "id": "603360ce3aeae4de2b6edec1",
    "name": "David Brent",
    "email": "[email protected]"
  }
}
```
