# 04 · Incident Response & Remediation

This document outlines the response process for investigating security alerts, containing threats, remediating affected systems and verifying recovery.

## Phase 1: Detection and Initial Triage

| Step | Action | Expected Evidence |
|---|---|---|
| 1 | Review incoming SIEM and EDR alerts. | Alert details and timestamps |
| 2 | Validate alert severity and determine whether activity is suspicious. | Triage findings |
| 3 | Identify affected systems, accounts and indicators. | Asset and IOC details |
| 4 | Correlate relevant Windows, Linux and network telemetry. | Supporting event records |
| 5 | Escalate confirmed or high-impact incidents where necessary. | Investigation record |

## Phase 2: Investigation and Containment

| Step | Action | Expected Evidence |
|---|---|---|
| 1 | Investigate suspicious activity and establish its scope. | Investigation findings |
| 2 | Identify affected endpoints, accounts and network indicators. | Evidence and IOC records |
| 3 | Isolate affected endpoints where authorised and supported. | Isolation verification |
| 4 | Disable compromised accounts or block malicious IPs where appropriate. | Verified response records |
| 5 | Preserve relevant logs and investigation evidence. | Evidence records |

## Phase 3: Remediation and Recovery

| Step | Action | Expected Evidence |
|---|---|---|
| 1 | Remove identified malicious files or activity where applicable. | Remediation records |
| 2 | Reset compromised credentials and review account access where necessary. | Account remediation evidence |
| 3 | Restore affected endpoints or services where required. | Recovery records |
| 4 | Verify endpoint security and monitoring functionality. | Verification evidence |
| 5 | Confirm that the suspicious activity has stopped. | Post-remediation findings |

## Response Validation

| Area | Validation Requirement |
|---|---|
| Detection | Confirm the alert was generated and investigated. |
| Containment | Verify that the authorised containment action succeeded. |
| Remediation | Confirm identified threats or weaknesses were addressed. |
| Recovery | Verify that affected systems returned to operation. |
| Documentation | Complete the investigation record and preserve supporting evidence. |

## Tracking

Each investigation and response action is documented in the [Investigation Register](../investigations/investigation-register.md), with supporting evidence retained in the project repository.

Response actions must reflect what was actually performed and verified during implementation.