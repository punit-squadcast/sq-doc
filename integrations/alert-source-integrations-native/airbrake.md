# Airbrake

Send alerts to Squadcast from Airbrake

[Airbrake](https://airbrake.io/) is a monitoring tool used to easily monitor errors and performance insights for your entire app stack.

Route detailed alerts from Airbrake to the right users in Squadcast.

### Using Airbrake as an Alert Source <a href="#using-airbrake-as-an-alert-source" id="using-airbrake-as-an-alert-source"></a>

**(1)** From the navigation bar on the left, select **Services**. Pick the applicable **Team** from the Team-picker on the top. Next, click on **Alert Sources** for the applicable Service

**(2)** Search for **Airbrake** from the Alert Source drop-down and copy the Webhook URL

### Create a Squadcast Webhook Integration in Airbrake <a href="#create-a-squadcast-webhook-integration-in-airbrake" id="create-a-squadcast-webhook-integration-in-airbrake"></a>

**(1)** Login to your **Airbrake** dashboard and select the **Project** of your choice

**(2)** Navigate to the **Integrations** tab. Under **Other** integrations section, click on **Webhook**

**(3)** Paste the previously copied Squadcast Webhook URL in the placeholder for **URL**. Check the **Enabled** checkbox and click on **Save**

You can also click on **Test integration** to test the alert. This will create a test incident in Squadcast.

That’s it, you are good to go! Your Airbrake integration is now complete. Whenever Airbrake fires an alert, an incident will be created in Squadcast for it.
