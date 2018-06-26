---
layout: integration
title: "SNMP(Debian)"
draft: false
type: System Monitoring
---

#### Install the BigPanda Agent on Debian

1. Connect to the host where your SNMP trap server is installed, and install the BigPanda agent package.

        $ echo deb http://repos.bigpanda.io/deb `lsb_release -c -s` main | sudo tee /etc/apt/sources.list.d/bigpanda.list
        $ curl https://repos.bigpanda.io/config/bigpanda.pub | sudo apt-key add -
        $ sudo apt-get update
        $ sudo apt-get install bigpanda-agent

2. Install the BigPanda SNMP daemon:

        $ sudo apt-get install bigpanda-snmpd

<!-- section-separator -->

#### Configure the BigPanda Agent

1. Configure the agent to work with the Raw Alerts Transfer plugin by running the following commands:

        $ sudo bigpanda-config --init --token $TOKEN
        $ sudo bigpanda-config --add rawalertstransfer --app-key $STREAM_ID

<!-- section-separator -->

#### Configure the BigPanda SNMP Agent

1. If any MIBs are not included by default, they need to be compiled and added manually:

        $ cd /etc/bigpanda/snmpd/mib_compiler
        $ sudo ./compile_mib.sh --input-directory <path to MIBs> --output-directory /etc/bigpanda/snmpd/conf/

2. Modify Config Files

    For MIBs that are to be monitored, their respective Event Configuration files must be added to the bigpanda-snmpd configuration file:

    Edit `/etc/bigpanda/snmpd/snmp-daemon.json`, and add the paths to the event_config files to the `processing.event-configs` array.

    For example:

        $ sudo vi /etc/bigpanda/snmpd/snmp-daemon.json
    
        ...
    
        {
          <snip>
          "processing": {
            "mibs-dir": "/etc/bigpanda/snmpd/mibs",
            "event-configs": [
              event_configs/example.json,
              <ADD EVENT CONFIGS HERE>
            ],
            "target-dir": "/var/lib/bigpanda/queue",
            "stress_test": false
          }
          </snip>
        }

<!-- section-separator -->

#### Start the Services

1. Start the BigPanda agent and snmpd services by running the following commands:

        $ sudo service bigpanda start
        $ sudo service bigpanda-snmpd start

<!-- section-separator -->

#### Test the Integration

1. Install SNMP Utils:

        $ sudo apt-get install snmp

2. Send the test SNMP trap:

        $ sudo snmptrap -v 2c -c public 127.0.0.1:5000 1 1.3.6.1.2.1.1 1.3.6.1.2.1.1.5 s "production-switch-1" 1.3.6.1.2.1.1.1 s "SNMP trap test"
    
    **Note**: Since it is a test message, it won't be resolved automatically. Click **Resolve incident** in the BigPanda UI to manually resolve it.
