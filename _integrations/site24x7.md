---
layout: integration
title: "Site24x7"
draft: false
type: Application Monitoring

---

#### Create an Action for BigPanda

1\. In Site24x7, go to [Admin > IT Automation](https://www.site24x7.com/app/client#/admin/it-automation).

  ![Sample Add Automation Screenshot](/media/site24x7-1.png)
  

2\. Click **Add Automation**, and add a new action by filling in the fields:

* **Display Name**: `BigPanda`
* **URL**: `$WEB_API_BASE_URL/data/integrations/site24x7?$URL_PARAMS`
* **TimeOut**: `30 secs`
* **HTTP Method**: select **POST**
* **Send Incident Parameters** and **Post as JSON**: select the check boxes


![Sample Configuration Profiles Screenshot](/media/site24x7-2.png)


3\. Click **Save**.

<!-- section-separator -->

#### Connect the Action to Site24x7 Monitors

1\. Go to [Admin > Inventory > Monitors](https://www.site24x7.com/app/client#/admin/inventory/monitors).

2\. For each monitor you would like to connect with BigPanda:

  1. Open the monitor in edit mode.

  2. Under **Configuration Profiles > IT Automation**, select **BigPanda** and **Execute on any status change**. Then, click **Add**.
    
      ![Sample Configuration Profiles Screenshot](/media/site24x7-3.png)

  3. Click **Save**.
  
      ![Sample Configuration Profiles Screenshot](/media/site24x7-4.png)


<!-- section-separator -->

#### Success!

The next time Site24x7 generates an alert, you will see it in the Incident Dashboard.
