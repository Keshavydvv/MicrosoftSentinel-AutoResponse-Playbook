# Microsoft Sentinel Combined Playbook: Ransomware Detection + IP Auto-Blocking

This project implements a powerful **unified playbook** in Microsoft Sentinel that automates threat detection and response for:

-  **Suspicious IP blocking**
-  **Honeypot-based ransomware detection**

The playbook is built using **Azure Logic Apps**, **Microsoft Defender for Endpoint**, and **Sentinel analytics rules**, helping security teams rapidly detect and mitigate threats — all without human intervention.

---

##  Core Capabilities

-  Detects suspicious activity using Sentinel incidents
-  Parses alert entities to extract attacker IPs
-  Automatically blocks IPs via Defender Threat Indicators API
-  Triggers response when honeypot (decoy) files are accessed/altered
-  Sends detailed alerts to SOC team
-  Adds comments and tags to Sentinel incidents for traceability

---

##  Technologies Used

- Microsoft Sentinel
- Azure Logic Apps (Standard)
- Microsoft Defender for Endpoint (Threat Indicators API)
- Office 365 Mail / Teams (Notifications)
- Azure AD App Registration (OAuth2)

---

##  Unified Workflow Overview

Sentinel Alert (IP Threat or Honeypot Access)
↓
Logic App Triggered
↓
[Entity Parsing & Enrichment]
↓
┌────────────────────────────┐
│ If entity is IP │
│ → Block IP via Defender │
│ → Email SOC │
└────────────────────────────┘
↓
[Ransomware Detection Logic]
↓
If Honeypot Access Detected:
- Optional: Isolate device
- Notify SOC
↓
Add Comment + Tag Incident



##  Repo Structure

Sentinel-Ransomware-IP-AutoResponse-Playbook/
├── README.md ← This file
├── diagrams/
│ └── combined-architecture.png
├── IP-AutoBlock/
│ ├── logicapp-ipblock.json
│ └── README.md
├── HoneyTrap-Ransomware/
│ ├── logicapp-honeytrap.json
│ └── README.md



##  Tags

`microsoft-sentinel` `logic-app` `defender-for-endpoint` `ransomware-detection` `automated-playbook` `ip-blocking`

---
