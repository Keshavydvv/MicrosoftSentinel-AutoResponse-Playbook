# HoneyTrap Ransomware Detection Playbook

This Microsoft Sentinel playbook detects ransomware behavior by monitoring honeypot files. When an attacker attempts to access, encrypt, or modify these fake files, the playbook responds automatically and alerts the SOC.

---

## 🧠 How It Works

1. **Trigger**: Analytics rule detects honeypot file activity (rename, extension change, etc.)
2. **Get Incident Details**: From Sentinel
3. **Actions Taken**:
   - Send Email to SOC
   - (Optional) Isolate Device via Defender API
   - Add Comment to incident
   - Tag incident as `HoneyTrap`

---

## 🔧 Tools Used

- Microsoft Sentinel (Analytics Rules)
- Azure Logic Apps (Standard)
- Office 365 Outlook (Email Notifications)
- Microsoft Defender for Endpoint (optional isolation)
- Azure AD App Registration (for API)

---

## 📎 File Structure

HoneyTrap-Ransomware/
├── logicapp-honeytrap.json ← Logic App (exported JSON)
├── honeypot-alert.json (optional test)
├── README.md



## 📬 Sample Email Sent

🚨 Honeypot File Access Detected

Device: WIN-SERVER01
User: attacker@domain.com
File: C:\HoneyTrap\decoy_file.doc
Action: Detected ransomware behavior.
Response: SOC Notified


## 🔖 GitHub Tags

`ransomware-response` `honeytrap` `microsoft-sentinel` `logic-app` `automated-playbook`