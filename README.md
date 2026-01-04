# SOAR & EDR Incident Response Automation Project

## 📌 Project Overview
This project demonstrates an **automated SOC incident response workflow** using **SOAR (Tines)** and **EDR integration** to detect, analyze, and respond to endpoint security threats.

The playbook includes **alert enrichment, analyst-in-the-loop decision making, automated endpoint isolation**, and **real-time notifications** to the SOC team.

---

## 🎯 Objectives
- Automate EDR alert ingestion using webhooks
- Enrich detections with endpoint and process context
- Notify SOC analysts via Slack and email
- Enable analyst approval before executing containment actions
- Automatically isolate compromised endpoints
- Provide real-time response status updates

---

## 🛠 Tools & Technologies
- **Tines** – SOAR Platform
- **EDR Platform (API-based integration)**
- **Slack** – SOC Notifications
- **Email Notifications**
- **Webhooks & REST APIs**
- **Virtualized Lab Environment**

---

## 🏗 Architecture Overview
The solution follows this flow:

1. Endpoint generates a detection event
2. Detection is sent to **Tines** via webhook
3. Tines enriches the alert with:
   - Timestamp
   - Hostname
   - Source IP
   - Process name
   - Command line
   - File path
   - Sensor ID
4. Alert details are sent to Slack and Email
5. SOC analyst is prompted to approve containment
6. If approved, endpoint is isolated using EDR API
7. Isolation status is verified and reported to SOC

---

## 🔄 SOAR Workflow (Tines)

### 🔹 Workflow Steps
- **Webhook Trigger** – Retrieves EDR detection
- **Alert Notification** – Sends detailed alerts to Slack and Email
- **User Prompt** – Analyst chooses whether to isolate the endpoint
- **Conditional Logic**
  - YES → Isolate endpoint
  - NO → No action taken
- **Status Verification** – Confirms isolation status
- **Final Notification** – SOC team receives outcome

---

## 🧠 Use Case: Endpoint Compromise Detection

### 🔍 Detection Context
- Suspicious process execution
- Malicious command-line behavior
- Endpoint compromise indicators

### 🛡 Response Actions
- Analyst-approved endpoint isolation
- Prevents lateral movement
- Reduces dwell time

---

## 📸 Visuals
