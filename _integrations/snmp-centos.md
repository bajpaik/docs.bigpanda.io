---
layout: integration
title: "SNMP (CentOS)"
draft: false
type: System Monitoring
---

#### Install the BigPanda Agent on CentOS

1. Connect to the host where your SNMP trap server is installed, and install the BigPanda agent package.

        $ sudo wget http://repos.bigpanda.io/config/bigpanda.repo -O /etc/yum.repos.d/bigpanda.repo
        $ sudo yum install bigpanda-agent

    **Note**: If you run **CentOS 5**, you will need to install the EPEL repository. Please consult the FAQ for instructions.

2. Install the BigPanda SNMP daemon:

        $ sudo yum install bigpanda-snmpd

<!-- section-separator -->

#### Configure the BigPanda Agent

1. Configure the agent to work with the Raw Alerts Transfer plugin by running the following commands:

        $ bigpanda-config --init --token $TOKEN
        $ bigpanda-config --add rawalertstransfer --app-key $STREAM_ID

<!-- section-separator -->

#### Configure the BigPanda SNMP Agent

1. If any MIBs are not included by default, they need to be compiled and added manually:

        $ cd /etc/bigpanda/snmpd/mib_compiler
        $ ./compile_mib.sh --input-directory <path to MIBs> --output-directory /etc/bigpanda/snmpd/conf/

2. Modify Config Files

    For MIBs that are to be monitored, their respective Event Configuration files must be added to the bigpanda-snmpd configuration file:

    Edit `/etc/bigpanda/snmpd/snmp-daemon.json`, and add the paths to the event_config files to the `processing.event-configs` array.

    For example:

        $ vi /etc/bigpanda/snmpd/snmp-daemon.json
    
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

    * For RHEL 5 and 7:
   
            $ sudo service bigpanda start
            $ sudo service bigpanda-snmpd start

    * For RHEL 6:

            $ sudo initctl start bigpanda
            $ sudo initctl start bigpanda-snmpd
    