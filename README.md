# SOAR & EDR Automation – LaZagne Credential Dumping Detection

## 📌 Project Overview
This project demonstrates an **automated SOC incident response workflow** for detecting and responding to **LaZagne credential dumping tool execution** on endpoints.

The solution integrates **EDR detections**, **Tines SOAR**, and **analyst-in-the-loop decision making** to enrich alerts, notify SOC analysts, and automatically **isolate compromised endpoints** upon approval.

This project simulates a **real-world SOC response scenario** focused on credential access attacks.

---

## 🎯 Objectives
- Detect execution of **LaZagne** on endpoints
- Automate alert ingestion using webhooks
- Enrich detections with endpoint and process context
- Notify SOC analysts via Slack and Email
- Enable analyst approval before containment
- Isolate compromised endpoints using EDR APIs
- Provide real-time response status updates

---

## 🛠 Tools & Technologies
- **Tines** – SOAR Automation Platform
- **EDR Platform (API-based integration)**
- **Slack** – SOC Notifications
- **Email Notifications**
- **Webhooks & REST APIs**
- **Virtualized Lab Environment**

---

## 🏗 Architecture Overview
The workflow follows this high-level architecture:

1. Endpoint executes LaZagne
2. EDR generates a detection
3. Detection is sent to **Tines** via webhook
4. Alert is enriched with contextual details
5. SOC analyst receives notifications
6. Analyst approves or denies containment
7. Endpoint is isolated if approved
8. Isolation status is verified and reported

---

## 🔄 SOAR Workflow (Tines)

### 🔹 Workflow Steps
1. **Webhook – Retrieve Detection**
   - Receives LaZagne execution alert from EDR

2. **Alert Enrichment**
   - Extracts:
     - Time
     - Hostname
     - Source IP
     - Process name
     - Command line
     - File path
     - Sensor ID
     - Detection link

3. **Alert Notification**
   - Sends enriched alert details to:
     - Slack
     - Email

4. **Analyst Decision (User Prompt)**
   - Analyst chooses:
     - ✅ YES → Isolate endpoint
     - ❌ NO → Take no action

5. **Automated Response**
   - If YES:
     - Endpoint is isolated using EDR API
     - Isolation status is verified
   - Final status is sent to Slack

---

## 🧠 Use Case: LaZagne Credential Dumping

### 🔍 Detection
- Detects execution of **LaZagne**, a known credential harvesting tool
- Identifies suspicious process execution and command-line behavior
- High-severity detection indicating potential credential compromise

### 🧩 MITRE ATT&CK Mapping
- **TA0006 – Credential Access**
- **T1555 – Credentials from Password Stores**
- **T1003 – Credential Dumping**

### 🛡 Response
- Analyst-reviewed containment decision
- Endpoint isolation to prevent lateral movement
- Rapid reduction of attacker dwell time

---

## 📸 Visuals
- SOAR & EDR Architecture Diagram
- Tines Workflow Diagram

