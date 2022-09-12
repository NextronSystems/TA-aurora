# TA-aurora

![aurora-logo](static/appIcon_2x.png)

## Overview

### About the Nextron Systems Aurora EDR Add-on for Splunk

|                       |                                                                 |
|-----------------------|-----------------------------------------------------------------|
| Version               | 0.2.0                                                           |
| Vendor Products       | Nextron Systems Aurora EDR Agent                                |
| Visible in Splunk Web | No.                                                             |

This add-on helps parse and configure the necessary inputs to neatly consume Aurora Sigma-Based EDR Agent Alerts into Splunk.
It also provides basic mapping to the Splunk Common Information Model (CIM) for use in Splunk Enterprise Security (and others).

The **Nextron Systems Aurora EDR Add-on for Splunk** provides search-time and CIM normalization for EDR events in the following formats:

| Source Type                | Description                                             | CIM Data Models                 |
|----------------------------|---------------------------------------------------------|---------------------------------|
| nextron:aurora:edr         | Aurora EDR events (JSON)                                | Endpoint, Intrusion Detection   |

- Has index-time configurations: false

### Change Log

> Version 0.2.0

- Renamed sourcetype from `aurora-edr` to `nextron:aurora:edr` as per Splunk best practice
- Reworked sourcetype configuration to extract file hash (SHA256 only at the moment - adapt if required) and use search time field extractions (as opposed to index-time) for flexibility
- Added CIM compliance/mapping to the `Endpoint.Processes` and `Intrusion Detection` data models for use in [Splunk Enterprise Security](https://www.splunk.com/en_us/products/enterprise-security.html)

## Installation/Configuration

1. Visit [https://www.nextron-systems.com/aurora/](https://www.nextron-systems.com/aurora/) and request an Aurora Lite package by submitting the download form
2. Follow the quick start guide for the Aurora EDR Agent [here](https://aurora-agent-manual.nextron-systems.com/en/latest/usage/installation.html#quick-start) and copy the `*.lic` file in your aurora directory.
3. Install Aurora with the following flags to make it log to a file in json format: `.\aurora-agent-64.exe --install -c agent-config-standard.yml --json --logfile aurora_alerts.json.log`  
4. Copy inputs.conf to local/inputs.conf, adapt as required (for example, set a destination index).
5. Copy the TA on the Search Head(s), Heavy Forwarder, and Universal Forwarder to $SPLUNK_HOME/etc/apps/ directory.

## Authors

- [Jose Hernandez](https://github.com/d1vious/)
- [Florian Roth](https://twitter.com/cyb3rops)

## Contributor(s)

- [Christian Cloutier](https://github.com/ccl0utier)