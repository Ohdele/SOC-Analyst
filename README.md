# SOC Analyst Operation: Triton Health Services

> **Portfolio project.** Triton Health Services is a fictional healthcare organization created for this SOC simulation. All systems, users, security events and findings are illustrative and based on controlled lab activities.

## Overview

An end-to-end Security Operations Center (SOC) operation for **Triton Health Services**, a fictional healthcare organization operating an on-premises Windows and Linux environment with Active Directory, endpoints, servers and centralized security monitoring.

This project demonstrates security monitoring, alert triage, endpoint and network investigation, event correlation, threat intelligence enrichment, detection engineering, incident response and automated containment. It also demonstrates analyst-approved response actions, endpoint isolation, containment verification and recovery.

**Why I built this:** SOC Analyst job descriptions repeatedly require practical experience in security monitoring, alert triage, investigation, threat detection and incident response. I wanted to demonstrate these capabilities through hands-on implementation, not just describe them. See [how this project maps to real job requirements](docs/06-soc-job-requirements-map.md).

## Key Findings

| Severity | Count | Headline |
|---|---:|---|
| 🔴 Critical | 1 | Mythic command-and-control activity and confirmed credential exfiltration from DC1 |
| 🟠 High | 6 | RDP brute-force, logon anomalies, network flow analysis, SIEM investigations, AD authentication weaknesses including `Kerberoasting` and `LaZagne` credential-access activity |
| 🟡 Medium | 2 | Unauthorized file modifications and suspicious account activity |
| 🟢 Low | Not established | No low-severity findings formally documented |

**Top priority:** Investigate and contain confirmed malicious activity, prioritizing command-and-control behaviour and repeated authentication attacks.

**## Architecture**

```mermaid
flowchart TD
    A[Windows Endpoints] --> B[Security Telemetry]
    C[Linux Servers] --> B
    D[Active Directory] --> B
    E[pfSense Firewall] --> B
    B --> F[SIEM Platforms]
    B --> G[EDR Platform]
    F --> H[Alert Detection]
    G --> H
    H --> I[Investigation and Triage]
    I --> J[Threat Intelligence Enrichment]
    J --> K[SOAR Orchestration]
    K --> L[Analyst Approval]
    L --> M[Incident Response]
    M --> N[Containment and Verification]
    N --> O[Recovery]
    I --> P[Investigation Documentation]
    M --> P
```

## Project Structure

| File | What it shows |
|---|---|
| [01 SOC Environment and Scope](docs/01-soc-environment-and-scope.md) | Organization context, lab environment, systems and monitoring scope |
| [02 Alert Triage and Investigation Methodology](docs/02-alert-triage-and-investigation-methodology.md) | How alerts are reviewed, prioritized, investigated and documented |
| [03 SOC Architecture and Telemetry Flow](docs/03-soc-architecture-and-telemetry-flow.md) | Monitoring architecture, log sources and telemetry flow |
| [04 Incident Response and Remediation](docs/04-incident-response-and-remediation.md) | Investigation, containment, remediation and verification activities |
| [05 SOC Executive Summary](docs/05-soc-executive-summary.md) | Key findings, operational outcomes and areas requiring attention |
| [06 SOC Job Requirements Map](docs/06-soc-job-requirements-map.md) | How project evidence maps to real SOC Analyst job requirements |
| [Investigation Register](investigations/investigation-register.md) | Documented investigations, findings, evidence and response actions |

## Frameworks and Methodologies

- **MITRE ATT&CK:** Mapping observed adversary behaviour to tactics and techniques.
- **Incident Response:** Investigation, containment, remediation and recovery activities.
- **Security Monitoring:** Centralized collection and analysis of Windows and Linux security telemetry.
- **Endpoint Detection and Response:** Monitoring endpoint activity, detecting credential-access behaviour and validating containment actions.
- **Threat Intelligence:** Enrichment and assessment of indicators of compromise.
- **Detection Engineering:** Developing, testing and refining detection rules.
- **Security Orchestration and Automation:** Coordinating alert notifications, analyst approval and automated endpoint isolation.
- **Network Security Monitoring:** Firewall traffic filtering, packet monitoring and analysis.

## What I Learned

- **Alert investigation requires evidence-based validation.** Correlating endpoint, authentication and network telemetry helps establish whether suspicious activity represents a genuine threat.
- **Containment requires verification.** A response action should be followed by checks confirming whether the intended security outcome was achieved.
- **Firewall enforcement provides an independent security layer.** Network traffic can be blocked before it reaches endpoints.
- **Documentation supports operational decisions.** Recording investigation findings, evidence and response actions makes incidents easier to review and communicate.
- **Human-in-the-loop automation supports faster response.** Integrating EDR and SOAR workflows streamlines response while keeping analysts in control of critical actions.

## What I'd Improve

- Expand detection coverage for additional attack techniques and suspicious behaviours.
- Integrate additional telemetry sources and improve event correlation.
- Develop further automated response workflows with appropriate analyst approval.
- Improve investigation documentation and evidence-handling procedures.
- Expand monitoring health checks, reporting and shift-handover documentation.

## Tools

Splunk · EDR · SOAR · Sysmon · pfSense · Suricata · Active Directory · PowerShell · MITRE ATT&CK · Wireshark · SPL · Linux · Python