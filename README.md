# TA-aurora

![aurora-logo](static/appIcon_2x.png)

Splunk Technology-AddOn for Aurora Sigma-Based EDR Agent. It helps parse and configure the necessary inputs to neatly consume Aurora EDR Agent Alerts into Splunk.

- Sourcetype: aurora-edr
- Has index-time ops: true

## Installation

1. Visit [https://www.nextron-systems.com/aurora/](https://www.nextron-systems.com/aurora/) and request an Aurora Lite package by submitting the download form
2. Follow the quick start guide for the Aurora EDR Agent [here](https://aurora-agent-manual.nextron-systems.com/en/latest/usage/installation.html#quick-start) and copy the `*.lic` file in your aurora directory.
3. Install Aurora with the following flags to make it log to a file in json format: `.\aurora-agent-64.exe --install -c agent-config-standard.yml --json --logfile aurora_alerts.json.log`  
4. Copy inputs.conf to local/inputs.conf
5. Copy the TA on the Search Head(s), Indexer(s), Heavy Forwarder, and Universal Forwarder to $SPLUNK_HOME/etc/apps/ directory.

## Authors

- [Jose Hernandez](https://github.com/d1vious/)
- [Florian Roth](https://twitter.com/cyb3rops)
