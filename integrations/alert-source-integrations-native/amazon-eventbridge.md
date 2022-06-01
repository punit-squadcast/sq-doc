# Amazon EventBridge

Send alerts to Squadcast from Amazon EventBridge

[Amazon EventBridge](https://aws.amazon.com/eventbridge/) is a serverless event bus that makes it easier to build event-driven applications at scale using events generated from your applications, integrated Software-as-a-Service (SaaS) applications, and AWS services.

Route detailed alerts from Amazon EventBridge to the right users in Squadcast.

### Using Amazon EventBridge as an Alert Source <a href="#using-amazon-eventbridge-as-an-alert-source" id="using-amazon-eventbridge-as-an-alert-source"></a>

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

**(2)** Search for **Amazon EventBridge** from the Alert Source drop-down and copy the Webhook URL

### Create a Squadcast Webhook Connection in Amazon EventBridge <a href="#create-a-squadcast-webhook-connection-in-amazon-eventbridge" id="create-a-squadcast-webhook-connection-in-amazon-eventbridge"></a>

**(1)** Login to your Amazon EventBridge dashboard. Head over to the **API destinations** tab and click on **Connections**. Then click on **Create connection**

**(2)** Fill in the **Connection name**, select **API Key** as Authorization type. Enter **Squadcast** as **API key name** and **true** as **Value**. Then click on **Create**

**(3)** Switch the **API destinations** and click on **Create API destination**

**(4)** Fill in the **Name** and paste the previously copied Squadcast Webhook URL in the placeholder for **API destination endpoint**. Select **POST** as **HTTP method** and under Connection, choose the previously created connection. Then click on **Create**

You can now mention your newly created **API destination** as target under **Rules**.

That’s it, you are good to go! Your Amazon EventBridge integration is now complete. Whenever Amazon EventBridge fires an alert, an incident will be created in Squadcast for it.
