---
layout: integration 
title: "Airbrake"
draft: false
type: System Monitoring
---

#### Define the Airbrake Webhook  

For each project in Airbrake:

* Click the small menu icon on the upper left corner, then navigate to `Project Settings`.
* From the left menu, select `Integrations`.
* Select `WebHooks` integration and enter the `Url`:  
  ```$WEB_API_BASE_URL/data/integrations/airbrake?$URL_PARAMS```
* Keep the `Active` check box selected.
* Click `Save`.

After configuring the first project, test the integration by clicking `Test Integration` near the Webhook integration title.

*Tip: You can access the other projects in your Airbrake account through the left menu pane.*

<!-- section-separator -->

#### Success
You should see an Airbrake test incident in BigPanda. Feel free to resolve the incident. 
