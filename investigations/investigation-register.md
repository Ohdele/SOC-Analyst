# Investigation Register: Triton Health Services

> Investigations are documented using the [SOC Alert Triage and Investigation Methodology](../docs/02-alert-triage-and-investigation-methodology.md). Each entry records the affected asset, detection, telemetry, investigation, findings, response, outcome and relevant MITRE ATT&CK mapping.

## Summary

| ID | Investigation | Alert Source | Severity | Status | Outcome |
|---|---|---|---|---|---|
| I-01 | Windows failed logon activity | Splunk | To be assessed | To be documented | To be documented |
| I-02 | Successful logon following repeated failures | Splunk | To be assessed | To be documented | To be documented |
| I-03 | SSH brute-force activity | Wazuh | To be assessed | To be documented | To be documented |
| I-04 | RDP brute-force activity | Elastic SIEM | To be assessed | To be documented | To be documented |
| I-05 | Mythic command-and-control activity | Elastic SIEM | To be assessed | To be documented | To be documented |
| I-06 | EICAR malware detection and quarantine | Elastic SIEM | To be assessed | To be documented | To be documented |
| I-07 | File integrity monitoring alert | Wazuh | To be assessed | To be documented | To be documented |
| I-08 | Controlled endpoint isolation and recovery | LimaCharlie / Tines | To be assessed | To be documented | To be documented |
| I-09 | Network flow and packet analysis | Wireshark PCAP | 🔴 High | Investigation completed; further validation required | Identified 596 suspected C2 HTTP POST requests and 249 RDP packets; endpoint execution, successful RDP authentication and account compromise remain unverified. |

## Investigation Details

### I-01 · Windows Failed Logon Activity

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Detection** | Test-Brute-Force |
| **Telemetry** | Windows Event ID 4625 |
| **Investigation** | Analyse repeated failed logons and identify the source. |
| **Findings** | To be documented. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-02 · Successful Logon Following Repeated Failures

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Detection** | Successful logon following repeated failures |
| **Telemetry** | Windows Event IDs 4625 and 4624 |
| **Investigation** | Correlate failed attempts with the successful JSmith logon from `192.168.56.101`. |
| **Findings** | To be documented. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-03 · SSH Brute-Force Activity

| | |
|---|---|
| **Asset** | DFIR-Linux |
| **Detection** | Wazuh SSH brute-force alert |
| **Telemetry** | Linux authentication logs |
| **Investigation** | Analyse repeated SSH authentication failures and identify the source. |
| **Findings** | To be documented. |
| **Response** | Document verified firewall-drop response. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-04 · RDP Brute-Force Activity

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Detection** | Elastic SIEM RDP brute-force alert |
| **Telemetry** | Windows authentication logs |
| **Investigation** | Analyse repeated RDP authentication failures. |
| **Findings** | To be documented. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-05 · Mythic Command-and-Control Activity

| | |
|---|---|
| **Asset** | Lab endpoint |
| **Detection** | Elastic SIEM Mythic C2 detection |
| **Telemetry** | Endpoint and network telemetry |
| **Investigation** | Correlate telemetry and analyse indicators of compromise. |
| **Findings** | To be documented. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-06 · EICAR Malware Detection and Quarantine

| | |
|---|---|
| **Asset** | Windows endpoint |
| **Detection** | EICAR test-file detection |
| **Telemetry** | Endpoint security telemetry |
| **Investigation** | Review the detection and verify quarantine. |
| **Findings** | To be documented. |
| **Response** | Document the verified quarantine action. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-07 · File Integrity Monitoring Alert

| | |
|---|---|
| **Asset** | Monitored endpoint |
| **Detection** | File integrity monitoring alert |
| **Telemetry** | Wazuh FIM events |
| **Investigation** | Examine the affected file and determine the nature of the change. |
| **Findings** | To be documented. |
| **Response** | Document verified response actions. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-08 · Controlled Endpoint Isolation and Recovery

| | |
|---|---|
| **Asset** | DC1 |
| **Detection** | Controlled response workflow |
| **Telemetry** | LimaCharlie endpoint telemetry |
| **Investigation** | Review the event and verify analyst-approved isolation. |
| **Findings** | To be documented. |
| **Response** | Document endpoint isolation and recovery verification. |
| **Outcome** | To be documented. |
| **MITRE ATT&CK Mapping** | To be assessed. |

### I-09 · Network Flow and Packet Analysis

| | |
|---|---|
| **Asset** | DC1 (`192.168.56.110`), Kali (`192.168.56.101`), Mythic C2 (`192.168.56.111`) and Splunk (`192.168.56.130`) |
| **Detection** | Suspected internal-to-internal port-scanning activity investigated through Wireshark packet analysis |
| **Telemetry** | Wireshark PCAP, TCP/HTTP traffic and network conversations |
| **Severity** | 🔴 High |
| **Investigation** | Analysed traffic captured on 2026-11-11 between 01:00:00 and 09:47:03 WCAST (UTC+1), examining connection patterns, source and destination systems and potential scanning activity. |
| **Findings** | Identified 596 HTTP POST requests to `/data` between DC1 and Mythic C2 and 249 RDP packets from Kali to DC1; port scanning, successful RDP authentication and endpoint execution remained unconfirmed. |
| **Response** | Recommend endpoint investigation, authentication-log correlation, executable validation and review of RDP access restrictions. |
| **Outcome** | Investigation completed; suspicious internal communications documented. Port-scanning activity was not established. Further endpoint and authentication-log validation required. |
| **MITRE ATT&CK Mapping** | T1071.001 – Web Protocols; T1021.001 – Remote Desktop Protocol. |