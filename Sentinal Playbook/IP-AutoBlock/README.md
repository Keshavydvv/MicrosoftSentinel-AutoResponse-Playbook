# Microsoft Sentinel IP Auto-Block Playbook

This playbook automatically blocks suspicious IP addresses detected by Microsoft Sentinel and notifies the SOC team. It uses Microsoft Defender for Endpoint and Logic Apps to automate the entire response pipeline.

---

## Trigger

Triggered when a **high/medium severity incident** is created in Microsoft Sentinel.

---

##  Workflow Steps

1. **Get Incident Info** (from Sentinel)
2. **Get Entities** (from the incident)
3. **Loop through entities** and:
   -  If entity type is `ip`:
     - Block using Defender for Endpoint API
     - Send Email to SOC
     - Add Comment to incident
     - Tag incident: `AutoBlocked`
   -  Else:
     - Append to `SkippedEntities` variable
4. **(Optional)**: Add a comment to the incident with skipped entities

---

##  Technologies Used

- Microsoft Sentinel
- Azure Logic Apps (Standard)
- Microsoft Defender for Endpoint API
- Office 365 Mail Connector
- Azure AD App Registration (for Defender API)

---

##  File Structure

IP-AutoBlock/
├── logicapp-ipblock.json
├── README.md


---

##  Sample Email Sent

Subject:  IP Blocked – Sentinel Alert: Brute Force Login

Incident: Brute Force Detected
Source IP: 185.22.45.10
Action Taken: Blocked via Defender API
Link: View Incident in Sentinel



##  GitHub Tags

`microsoft-sentinel` `logic-app` `automated-response` `defender` `ip-blocking`
