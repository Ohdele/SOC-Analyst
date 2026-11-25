# 06 · SOC Job Requirements Map

This project was built by reverse-engineering entry-level SOC Analyst job descriptions; this page maps recurring job requirements to the evidence demonstrated in this repository.

| Job requirement | Where it's demonstrated |
|---|---|
| "Monitor security alerts across SIEM and endpoint security platforms" | [SOC Architecture & Telemetry Flow](03-soc-architecture-and-telemetry-flow.md) and investigation records |
| "Triage alerts and investigate suspicious activity" | [Alert Triage & Investigation Methodology](02-alert-triage-and-investigation-methodology.md) and [Investigation Register](../investigations/investigation-register.md) |
| "Analyse Windows and Linux security logs" | [SIEM](../investigations/investigation-register.md#i-10--siem-investigation) and [Authentication](../investigations/investigation-register.md#i-11--authentication-investigation) |
| “Correlate security events and identify indicators of compromise” | Investigate escalated alerts using [SIEM](../investigations/investigation-register.md#i-10--siem-investigation), [EDR](../investigations/investigation-register.md#i-08--edr-detection-and-automated-response), [Network Flow & Packet](../investigations/investigation-register.md#i-09--network-flow-and-packet-analysis), [Firewall](../investigations/investigation-register.md#i-12--firewall-and-network-security-monitoring), [Authentication](../investigations/investigation-register.md#i-11--authentication-investigation), proxy and host data |
| "Perform incident containment and remediation" | [Incident Response & Remediation](04-incident-response-and-remediation.md) and [EDR](../investigations/investigation-register.md#i-08--edr-detection-and-automated-response) |
| "Use threat intelligence and MITRE ATT&CK to investigate threats" | Investigation records and detection analysis |
| "Document incidents and preserve investigation evidence" | [Investigation Register](../investigations/investigation-register.md) and [Screenshots](../Screenshots/) |
| "Monitor and improve security detection capabilities" | Detection rules, SIEM configurations and investigation findings |
| "Automate security operations and response workflows" | [EDR](../investigations/investigation-register.md#i-08--edr-detection-and-automated-response) and Splunk, n8n and Tines implementation evidence |
| "Communicate security findings and incident status" | [SOC Executive Summary](05-soc-executive-summary.md) |
| "Maintain clear technical documentation" | This repository and its supporting documentation |





