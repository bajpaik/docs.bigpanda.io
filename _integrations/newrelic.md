---
layout: integration 
title: "New Relic"
draft: false
type: Application Monitoring

---

#### Locate Alerts Settings
In the New Relic dashboard, navigate to **Notification channels**.

For more information, see the [legacy alerting system documentation](https://docs.newrelic.com/docs/alerts/new-relic-alerts/getting-started/alerting-new-relic).

<!-- section-separator -->

#### Create Channel for BigPanda
1\. Under **Channels**, click **Create a notification channel** and select **Webhook** as the channel type.

2\. Fill in the form:

* **Channel Name**: `BigPanda`
* **Base URL**: `$WEB_API_BASE_URL/data/integrations/newrelic?$URL_PARAMS`

3\. Click **Add Custom Payload**, scroll to the bottom and ensure that **JSON** is selected as the payload type.

4\. At the bottom of the screen, click **Create channel > Integrate with Webhooks**.

<!-- section-separator -->

#### Test the Channel

1\. Under **Alerts > Notification channels**, choose the **BigPanda channel** you just created, scroll down and click **Send a test notification**.

2\. In BigPanda, click **Incidents** in the top menu and confirm that the test message was received.

**Note:** Since it is a test message, it won't be resolved automatically. Click **Resolve incident** to manually resolve it.

<!-- section-separator -->

#### Add BigPanda Notification to a New Alert Policy

1\. In the New Relic dashboard, navigate to **Alerts policy > Add alert policy**.

2\. Under **Alerts policy**, choose your policy and add all of your conditions by using **Add new condition**.

3\. Under **Notification channels > Add notification channels**, choose **Webhook > BigPanda** channel, and click **Update policy**.

<!-- section-separator -->

#### Add BigPanda Notification to an Existing Alert Policy

1\. Under **Alerts policy**, choose your policy and click **Notification channel > Add notification channels**.

2\. Choose **Webhook > BigPanda**, and click **Update policy**.

**Note:** You must set the incident preference of each policy to **By condition and entity**.

For each alert policy, select the policy, and then set the incident preference. ![media/NewRelicIncidentPreference.png](/media/NewRelicIncidentPreference.png)