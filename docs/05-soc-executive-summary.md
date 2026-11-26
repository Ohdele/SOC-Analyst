# 05 · Executive Summary

**To:** Triton Health Services Leadership Team  
**Subject:** SOC operations project: security monitoring, investigations and response  
**Date:** To be updated

## The Short Version

This project simulates a Security Operations Center (SOC) for Triton Health Services, a fictional healthcare organisation handling sensitive patient and business information. It demonstrates security monitoring, alert triage, investigation, threat detection and incident response across controlled lab environments.

## What Could Go Wrong

1. **Unauthorised access:** Compromised credentials or inadequate firewall controls could allow attackers to access organisational systems and networks.
2. **Malicious endpoint activity:** Malware or command-and-control activity could compromise workstations and servers.
3. **Undetected security threats:** Insufficient telemetry collection and event correlation could allow malicious activity to remain unnoticed.
4. **Delayed incident response:** Poor alert triage and delayed containment could increase attacker dwell time and operational impact.

## What We Implemented

| Area | Implementation |
|---|---|
| **Detection and triage** | Authentication, brute-force, malware and suspicious activity detection and investigation |
| **Threat investigation** | Event correlation, endpoint, packet, firewall and web proxy investigation across Splunk, pfSense, Suricata, Squid and Wireshark. |
| **Incident response & automation** | Alert notifications, analyst-approved endpoint isolation, containment verification and recovery checks using LimaCharlie, Slack and email. |


## What We Need From You

- **Review** the documented SOC architecture and investigation evidence.
- **Assess** the demonstrated detection and response capabilities.
- **Identify** remaining detection gaps and opportunities for improvement.

## After These Actions

The project provides documented evidence of SOC monitoring, investigation, event correlation and incident response capabilities, with remaining gaps and opportunities for improvement identified through implementation.
