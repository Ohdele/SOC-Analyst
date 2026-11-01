# Investigation Register: Triton Health Services

> Investigations are documented using the [SOC Alert Triage and Investigation Methodology](../docs/02-alert-triage-and-investigation-methodology.md). Each entry records the alert, investigation evidence, findings, response actions and outcome.

## Summary

| ID | Investigation | Alert Source | Status | Outcome |
|---|---|---|---|---|
| I-01 | Windows failed logon activity | Splunk | To be documented | To be documented |
| I-02 | Successful logon following repeated failures | Splunk | To be documented | To be documented |
| I-03 | SSH brute-force activity | Wazuh | To be documented | To be documented |
| I-04 | RDP brute-force activity | Elastic SIEM | To be documented | To be documented |
| I-05 | Mythic command-and-control activity | Elastic SIEM | To be documented | To be documented |
| I-06 | EICAR malware detection and quarantine | Elastic SIEM | To be documented | To be documented |
| I-07 | File integrity monitoring alert | Wazuh | To be documented | To be documented |
| I-08 | Controlled endpoint isolation and recovery | LimaCharlie / Tines | To be documented | To be documented |

## Investigation Details

### I-01 · Windows Failed Logon Activity

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Telemetry** | Windows Event ID 4625 |
| **Detection** | Test-Brute-Force |
| **Investigation** | Analyse repeated failed logons and identify the source. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented |

### I-02 · Successful Logon Following Repeated Failures

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Telemetry** | Windows Event IDs 4625 and 4624 |
| **Detection** | Successful logon following repeated failures |
| **Investigation** | Correlate failed attempts with the successful JSmith logon from 192.168.56.101. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented |

### I-03 · SSH Brute-Force Activity

| | |
|---|---|
| **Asset** | DFIR-Linux |
| **Telemetry** | Linux authentication logs |
| **Detection** | Wazuh SSH brute-force alert |
| **Investigation** | Analyse repeated SSH authentication failures and identify the source. |
| **Response** | Document verified firewall-drop response. |
| **Outcome** | To be documented |

### I-04 · RDP Brute-Force Activity

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Telemetry** | Windows authentication logs |
| **Detection** | Elastic SIEM RDP brute-force alert |
| **Investigation** | Analyse repeated RDP authentication failures. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented |

### I-05 · Mythic Command-and-Control Activity

| | |
|---|---|
| **Asset** | Lab endpoint |
| **Telemetry** | Endpoint and network telemetry |
| **Detection** | Elastic SIEM Mythic C2 detection |
| **Investigation** | Correlate telemetry and analyse indicators of compromise. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented |

### I-06 · EICAR Malware Detection and Quarantine

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Telemetry** | Endpoint security telemetry |
| **Detection** | EICAR test-file detection |
| **Investigation** | Review the detection and verify quarantine. |
| **Response** | Document the verified quarantine action. |
| **Outcome** | To be documented |

### I-07 · File Integrity Monitoring Alert

| | |
|---|---|
| **Asset** | Monitored endpoint |
| **Telemetry** | Wazuh FIM events |
| **Detection** | File integrity monitoring alert |
| **Investigation** | Examine the affected file and determine the nature of the change. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented |

### I-08 · Controlled Endpoint Isolation and Recovery

| | |
|---|---|
| **Asset** | DC1 |
| **Telemetry** | LimaCharlie endpoint telemetry |
| **Detection** | Controlled response workflow |
| **Investigation** | Review the event and verify analyst-approved isolation. |
| **Response** | Document endpoint isolation and recovery verification. |
| **Outcome** | To be documented |