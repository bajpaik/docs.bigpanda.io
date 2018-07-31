---
layout: integration 
title: "Panopta"
draft: false
type: System Monitoring
---

#### Define the Panopta BigPanda Integration  

* From the top menu in Panopta, choose [Settings -> Integrations](https://my.panopta.com/integrations/#panel_1)
* In the **Incident Management System** section, click **Configure** in the BigPanda tile

  ![Sample Configuration Profiles Screenshot](/media/panopta_2.png)

* Fill out the form with the following details:
  * **Name:** `<choose any name, you can use the integration name from step 1>`
  * **Auth Token:** `$TOKEN`
  * **Application Key:** `$STREAM_ID`
* Click on **Create BigPanda Integration**

  ![Sample Configuration Profiles Screenshot](/media/panopta_4.png)

<!-- section-separator -->

#### Define BigPanda as a Notifications' Recipient

* Under Monitoring, choose [Alert Timelines](https://my.panopta.com/config/notification/ListNotificationSchedules)
* For each Alert Timeline in use, do the following:
  * Edit the alert timeline by select the 3-dot menu to the right and select Edit
  
  ![Sample Configuration Profiles Screenshot](/media/panopta_3.png)
  
  * Click on **New Event** or edit an existing event
  * Under **Integrations** choose the BigPanda integration that you just created
  * Click on **Create Action**
  
  ![Sample Configuration Profiles Screenshot](/media/panopta_5.png)
  
<!-- section-separator -->

#### Success
Next time you'll have Panopta alerts, you will be able to see them in BigPanda.
