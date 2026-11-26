# 02 · Alert Triage & Investigation Methodology

This methodology defines a consistent process for reviewing security alerts, investigating suspicious activity, determining appropriate response actions and documenting verified outcomes across the SOC environment.

## Process

1. **Review Alerts:** Examine incoming SIEM alerts and identify activity requiring investigation.
2. **Validate Detections:** Determine whether reported activity is suspicious, malicious or benign.
3. **Establish Scope:** Identify affected systems, accounts, network activity and relevant indicators.
4. **Collect & Correlate Evidence:** Examine available telemetry and supporting evidence to reconstruct events and establish what happened.
5. **Assess & Respond:** Evaluate severity and impact, then select appropriate actions such as monitoring, containment, remediation, recovery or escalation.
6. **Verify & Document:** Confirm response outcomes and classify findings as true positive, false positive or inconclusive; escalate where further investigation is required. Record evidence and decisions in the Investigation Register.

## Alert Classification

| Classification | Description | Expected Action |
|---|---|---|
| Informational | Activity requiring awareness but no immediate investigation | Record or monitor |
| Low | Suspicious activity with limited indicators of impact | Review and document |
| Medium | Credible suspicious activity requiring further investigation | Investigate and escalate where necessary |
| High | Strong indicators of compromise or significant security impact | Prioritise investigation and containment |
| Critical | Confirmed or suspected severe incident affecting critical systems or data | Immediate escalation and response |

## Investigation Evidence

| Evidence Source | Investigation Purpose |
|---|---|
| Windows Security Events | Authentication, account and access activity |
| Sysmon and Linux Authentication Logs | Process execution, system activity and authentication |
| SIEM and EDR Telemetry | Alert review, endpoint investigation and event correlation |
| Firewall and IDS Logs | Network traffic, filtering decisions and intrusion detections |
| Web Proxy Logs | HTTP/HTTPS requests, access decisions and User-Agent activity |
| Wireshark / PCAP | Packet-level analysis, protocols and suspicious communications |
| Threat Intelligence | Enrichment and assessment of indicators |
| SOAR and Automation Records | Workflow execution, alert enrichment and response activity |
| Response Verification | Endpoint isolation status and network connectivity tests |

## Limitations

Investigation conclusions depend on available telemetry, detection coverage and supporting evidence. Classifications and response decisions must be based on verified findings rather than assumptions.