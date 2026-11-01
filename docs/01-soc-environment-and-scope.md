# 01 · SOC Environment & Scope

> Triton Health Services is a **fictional** healthcare organisation created for this portfolio project.

## The Organization

| | |
|---|---|
| **Company** | Triton Health Services |
| **Industry** | Healthcare |
| **Size** | Approximately 500 employees (simulated assumption) |
| **Environment** | On-premises Windows enterprise with Active Directory, Windows endpoints, Linux servers and network infrastructure |
| **Data held** | Electronic patient health records, patient identification and contact details, employee information, appointment and billing records, internal business documents and security logs |
| **Security operations** | Small SOC responsible for security monitoring, alert triage, investigation and incident response |
| **Infrastructure** | Centralised security monitoring across Elastic SIEM, Splunk and Wazuh |

## Why This Project Matters

- **Patient data protection:** Healthcare organisations handle sensitive information that requires appropriate security monitoring and protection.
- **Threat detection:** Suspicious authentication activity, malware and unauthorised access can affect systems and patient information.
- **Incident response:** Timely investigation, containment and remediation help reduce the impact of security incidents.
- **Operational visibility:** Centralised telemetry and investigation records provide visibility into security events across the environment.

## Scope

**In scope**

- Windows servers and workstations
- Active Directory and authentication activity
- Linux servers and endpoints
- Security telemetry from Sysmon, Windows Security Events and Linux authentication logs
- SIEM monitoring, alert detection and investigation
- Threat intelligence enrichment and SOC automation
- Incident containment, remediation and recovery workflows

**Out of scope**

- Production healthcare systems and live patient records
- Physical security of healthcare facilities
- Real-world patient care operations
- External systems not represented in the simulated lab environment

## Assumptions

- Triton Health Services and its infrastructure are simulated for this portfolio project.
- The environment represents an on-premises healthcare enterprise.
- Security investigations use controlled lab activity and test data.
- Findings and response actions are based on available lab telemetry and verified implementation evidence.
- No real patient information or production systems are involved.

## Stakeholders

| Role | Area |
|---|---|
| SOC Analyst | Alert monitoring, triage and investigation |
| SOC Engineer | SIEM configuration, telemetry collection and detection engineering |
| IT Administrator | Endpoint, server and Active Directory administration |
| Incident Response Lead | Incident escalation, containment and recovery |
| Management | Security oversight and operational reporting |