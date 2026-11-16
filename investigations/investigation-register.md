# Investigation Register: Triton Health Services

> Investigations are documented using the [SOC Alert Triage and Investigation Methodology](../docs/02-alert-triage-and-investigation-methodology.md). Each entry records the affected asset, detection, telemetry, investigation, findings, response, outcome and relevant MITRE ATT&CK mapping.

## Summary

| ID | Investigation | Severity | Disposition | Assigned Analyst |
|---|---|---|---|---|
| I-01 | Windows failed logon activity | To be assessed | Pending investigation | Tier 1 SOC Analyst |
| I-02 | Successful logon following repeated failures | 🟠 High | True Positive | Tier 2 SOC Analyst |
| I-03 | SSH brute-force activity | To be assessed | Pending investigation | Tier 1 SOC Analyst |
| I-04 | RDP brute-force activity | 🟠 High | True Positive | Tier 1 SOC Analyst |
| I-05 | Mythic command-and-control activity | 🔴 Critical | True Positive | Tier 2 SOC Analyst |
| I-06 | EICAR malware detection and quarantine | Not assessed | Not conducted | Not assigned |
| I-07 | File integrity monitoring alert | To be assessed | Pending investigation | Tier 1 SOC Analyst |
| I-08 | Controlled endpoint isolation and recovery | To be assessed | Pending investigation | Tier 2 SOC Analyst |
| I-09 | Network flow and packet analysis | 🟠 High | Inconclusive | Tier 2 SOC Analyst |
| I-10 | SIEM investigation of suspicious activity | 🟠 High| True Positive | Tier 2 SOC Analyst |
| I-11 | Authentication Investigation | 🟠 High | True Positive | Tier 2 SOC Analyst |

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
| **Asset** | DC1 |
| **Detection** | Successful Administrator logons following repeated failures |
| **Telemetry** | Splunk Windows Security Events 4624, 4672 and 4634 |
| **Investigation** | Correlated three successful network logons from Kali using Logon IDs and timestamps. |
| **Findings** | Confirmed three NTLMv2 Administrator logons: 7 Nov (16:36:19), 10 Nov (10:12:29) and 10 Nov (22:57:17), each linked to privilege assignment and logoff events. |
| **Response** | Documented authentication evidence; no containment action confirmed. |
| **Outcome** | Confirmed three successful Administrator sessions from Kali; full compromise duration not established. |
| **MITRE ATT&CK Mapping** | T1078 – Valid Accounts. |

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
| **Asset** | DC1 |
| **Detection** | Repeated failed network logons from Kali |
| **Telemetry** | Splunk Windows Security Event ID 4625 |
| **Investigation** | Analysed failed logons from Kali, identifying targeted accounts and activity timeframe. |
| **Findings** | Identified 62 failed logons: 60 targeting Administrator and 2 targeting root, between 7 Nov 2026, 16:35:38 to 10 Nov 2026, 22:57:15 |
| **Response** | Documented authentication evidence; no containment action confirmed. |
| **Outcome** | Confirmed repeated failed authentication attempts against DC1; successful access is documented separately in I-02. |
| **MITRE ATT&CK Mapping** | T1110 – Brute Force. |

### I-05 · Mythic Command-and-Control Activity

| | |
|---|---|
| **Asset** | DC1 (192.168.56.110), Mythic C2 (192.168.56.111) |
| **Detection** | Suspicious Apollo payload execution and outbound C2 communications |
| **Telemetry** | Splunk Sysmon Events 1 and 3; Windows Security Event ID 4688 |
| **Investigation** | Correlated Apollo process execution with outbound network connections to the known Mythic server. |
| **Findings** | Confirmed Apollo execution via PowerShell on 8 Nov 2026 at 21:18:38, followed by three TCP connections to Mythic over port 80 (21:18:40, 21:59:56 and 22:02:43). |
| **Response** | Documented C2 activity and simulated exfiltration evidence; no containment action confirmed. |
| **Outcome** | Confirmed Mythic C2 activity and simulated retrieval of a 167-byte `passwords.txt` artifact (10 Nov 2026, Task T-3). |
| **MITRE ATT&CK Mapping** | T1071.001 – Web Protocols; T1041 – Exfiltration Over C2 Channel. |

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
| **Asset** | DC1 |
| **Detection** | Suspected internal-to-internal port-scanning activity investigated through Wireshark |
| **Telemetry** | Wireshark PCAP, TCP/HTTP traffic and network conversations |
| **Investigation** | Analysed traffic captured on 11 Nov 2026, 01:00–09:47 WCAST (UTC+1), examining RDP activity, TCP connections, HTTP communications and network conversations. |
| **Findings** | Identified 249 RDP packets from Kali to DC1 and 596 HTTP POST `/data` requests from DC1 to Mythic C2 at 10–12-second intervals. Confirmed TCP handshakes to Mythic on port 80 at 01:26:21, 02:02:19 and 03:09:27. DC1–Mythic exchanged approximately 6 MB; DC1–Splunk exchanged approximately 33 MB. Port scanning was not established. |
| **Response** | Recommended endpoint and authentication-log correlation and investigation of suspicious internal communications. |
| **Outcome** | Confirmed suspicious RDP and HTTP C2 network activity; successful RDP authentication and endpoint execution required separate SIEM validation. |
| **MITRE ATT&CK Mapping** | T1071.001 – Web Protocols; T1021.001 – Remote Desktop Protocol. |

### I-10 · SIEM Investigation

| | |
|---|---|
| **Asset** | DC1 |
| **Detection** | RDP brute-force and Mythic Apollo C2 activity |
| **Telemetry** | Splunk Windows Security, Sysmon and System Events |
| **Investigation** | Correlated authentication, process execution and network events to reconstruct attack activity. |
| **Findings** | Confirmed 62 failed logons (7–10 Nov); three successful Administrator logons (7 Nov 16:36:19; 10 Nov 10:12:29 and 22:57:17); Apollo execution (8 Nov 21:18:38); discovery commands (`whoami` at 21:48:45 and `ipconfig` at 21:49:33); C2 connections to Mythic (8 Nov 21:18:40, 21:59:56 and 22:02:43); simulated exfiltration of `passwords.txt` (10 Nov 23:52:28; Mythic artifact: 167 bytes). |
| **Response** | Documented investigation evidence; no containment action confirmed. |
| **Outcome** | Confirmed successful Administrator access, Apollo execution, C2 activity and simulated file exfiltration; no suspicious persistence or lateral movement confirmed. |
| **MITRE ATT&CK Mapping** | T1110.001 – Password Guessing; T1078 – Valid Accounts; T1059.001 – PowerShell; T1071.001 – Web Protocols; T1041 – Exfiltration Over C2 Channel. |


### I-11 · Authentication Investigation

| | |
|---|---|
| **Asset** | DC1 (192.168.56.110), WS01 (192.168.56.102), DeleDFIR.local |
| **Detection** | Weak domain password controls, suspicious credential use and Kerberos service-account exposure |
| **Telemetry** | Active Directory, Windows authentication, SMB, Kerberos, BloodHound and password-policy data |
| **Investigation** | Validated domain-user authentication, assessed password policies, tested credentials through NetExec and SMB, reviewed AD identities and relationships with BloodHound, and investigated credential exposure and Kerberos service-account weaknesses. |
| **Findings** | Identified weak password-policy settings and validated low-privileged domain credentials through SMB. BloodHound collection exposed a password stored in an AD user Description attribute. A Kerberoasting assessment recovered the weak password of an SPN-enabled service account. PSExec and SMBExec also demonstrated successful authenticated remote execution on WS01 with SYSTEM privileges. |
| **Response** | Reset the exposed account password, cleared its AD Description attribute, and documented recommendations for stronger password policies, secure service-account credentials and least-privilege access. |
| **Outcome** | Confirmed multiple domain credential weaknesses, validated their security impact and verified remediation of the exposed AD credential. |
| **MITRE ATT&CK Mapping** | T1078.002 – Domain Accounts; T1110.002 – Password Cracking; T1552.001 – Credentials In Files; T1558.003 – Kerberoasting; T1021.002 – SMB/Windows Admin Shares. |