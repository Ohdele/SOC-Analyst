# 01 · Scope & Context

> Triton Health Services is a **fictional** company created for this portfolio project. All business details and security scenarios are simulated.

## Organization Profile

| **Organization Detail** | **Description** |
|---|---|
| **Name** | Triton Health Services |
| **Industry** | Healthcare |
| **Size** | Approximately 260 employees, hybrid workforce, HQ in Columbus, OH |
| **Customers** | Approximately 450 outpatient clinics across the US |
| **Data Held** | ePHI for ~800,000 patients (identities, medical history, appointment records) |
| **IT Environment** | On-premises enterprise environment with Active Directory, employee workstations and centralized security monitoring |
| **Threat Profile** | Credential theft, ransomware execution, unauthorized lateral movement, ePHI exfiltration and other suspicious activities |
| **Security Monitoring** | Splunk SIEM, LimaCharlie EDR and automated alert triage and response integrations |

## Why This SOC Assessment Matters

- **Threat detection and response.** Triton needs visibility into suspicious authentication, credential theft, ransomware, lateral movement, phishing and potential ePHI exfiltration.
- **Incident investigation.** Correlate endpoint and authentication evidence, validate suspicious activity and support timely containment to minimize MTTD and MTTR.
- **Operational visibility.** Maintain reliable log ingestion, optimize SIEM performance and improve detection coverage to reduce monitoring gaps and false positives.

## Scope

### In-Scope

- **Identity & Authentication:** Active Directory Domain Controllers, Kerberos/NTLM authentication logs, and Windows Security Event Logs (Events 4624, 4625, 4720, 4738).
- **Endpoints & Telemetry:** Windows and Linux workstations/servers monitored via LimaCharlie EDR and Sysmon (Process creation, network connections, file integrity).
- **SIEM & Ingestion:** Splunk Enterprise log collection, index configurations, and custom SPL detection searches.
- **Automation & Response:** n8n and Tines SOAR playbooks for alert enrichment, ticket routing, and endpoint containment.
- **Target Data Assets:** File access logs and telemetry covering sensitive local ePHI repositories.

**Out of scope**
- Physical security and facility access controls across clinic locations.
- Local IT infrastructure managed independently by outpatient clinics.
- Production healthcare environments and live patient data.

## Assumptions

- **Telemetry & Log Availability:** Relevant log sources are configured to generate and forward security events to Splunk; ingestion completeness is assessed where validated.
- **Simulated Adversary Activity:** Controlled attack scenarios generate security events for investigation and response testing.
- **Lab Execution Boundary:** Findings reflect detection performance, log visibility and response automation within the simulated SOC environment.
- **Evolving Implementation:** Detection rules and automation workflows may change as the project progresses.
