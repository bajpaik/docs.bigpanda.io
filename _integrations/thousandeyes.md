---
layout: integration
title: "ThousandEyes"
draft: false
type: Application Monitoring
---

#### Configure BigPanda Webhook

1. In the ThousandEyes dashboard, in the left-hand nav under **SETTINGS**, click **Alerts > Alert Rules**.

2. Select a commonly used Alert Rule (e.g. **Default HTTP Alert Rule**), click to expand, and then select the **Notifications** tab.  Under the **WEBHOOKS** section, click **Configure Webhooks** or **Edit webhooks**.

    ![Sample Alert Rule Screenshot](/media/image1.png)

3. In the **Edit Webhooks** popup, click **Add New Webhook**.  Enter the following information, click **Test** to confirm connectivity, and then click **Add New Webhook**:

        Name: BigPanda
        URL: https://custom-api.bigpanda.io/thousandeyes/
        Auth Type: Token
        Bearer Token: $TOKEN

    ![Sample Webhook Screenshot](/media/image2.png)
<!-- section-separator -->

#### Add BigPanda Webhook to Alert Rules

1. Add the BigPanda webhook to all of the Alert Rules you would like BigPanda to process.

2. Verify alerts are received by BigPanda and show up in the Console.
