---
layout: integration
title: "Nagios (Ubuntu)"
draft: false
type: System Monitoring

---

<!-- docs-include _integrations/agent-common/install/local-installation.md:::SOURCE_SYSTEM_NAME=Nagios:::PLATFORM_NAME=Ubuntu:::PLATFORM_LOWER=ubuntu -->

<!-- section-separator -->

<!-- docs-include _integrations/agent-common/configure-agent-actions/generic.md:::PLATFORM=ubuntu:::SERVICE_NAME=nagios -->

3. Start the BigPanda agent service by running the following command:

<!-- docs-include _integrations/agent-common/configure-agent-actions/start-ubuntu.md:::SERVICENAME=Bigpanda:::SERVICE_LOWER=bigpanda:::ACTION=start -->

<!-- section-separator -->

<!-- docs-include _integrations/agent-common/configure-agent/nagios_notifications.md:::SOURCE_SYSTEM_NAME=Nagios:::SOURCE_SYSTEM_UPPER=NAGIOS:::SOURCE_SYSTEM_LOWER=nagios:::SOURCE_SYSTEM_FOLDER=nagios3:::LOGFILE=nagios -->

4. Restart the Nagios service.

<!-- docs-include _integrations/agent-common/configure-agent-actions/start-ubuntu.md:::SERVICENAME=Nagios:::SERVICE_LOWER=nagios:::ACTION=restart -->

<!-- section-separator -->

<!-- docs-include _integrations/agent-common/start-and-summary/test-and-success.md:::SOURCE_SYSTEM_NAME=Nagios:::PLATFORM=ubuntu -->
