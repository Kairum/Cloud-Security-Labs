# Investigate Windows Security Events with Microsoft Sentinel

## 🛡️ Overview
This lab demonstrates how to deploy and use Microsoft Sentinel,a cloud-native SIEM and SOAR solution, to detect, investigate, and respond to simulated Windows security threats. I will configure Sentinel, ingest logs, simulate suspicious behavior, and use investigation tools to analyze incidents.

---

## 🎯 Objectives

- Deploy Microsoft Sentinel on a Log Analytics Workspace
- Install the Windows Security Events solution
- Configure data connectors and analytics rules
- Enable auditing policies on a Windows VM
- Simulate real-world security incidents (e.g., hidden tasks, brute-force attacks)
- Investigate and triage incidents using Sentinel

---

## 🧰 Technologies Used

- Microsoft Azure
- Microsoft Sentinel
- Windows Virtual Machine
- Log Analytics Workspace
- Registry Editor, Group Policy Editor, Task Scheduler
- PsExec (Sysinternals)

---

## 🧪 Steps Performed

### 1. Deploy Microsoft Sentinel
- Enabled Microsoft Sentinel on an existing Log Analytics workspace.

### 2. Add Security Solutions
- Installed the **Windows Security Events** solution via the Content Hub.

### 3. Configure Data Connectors
- Set up **Windows Security Events via AMA** connector.
- Created a **Data Collection Rule** to ingest logs from a provisioned VM.

### 4. Configure Analytics Rules
- Enabled rules for:
  - **Scheduled Task Hide**
  - **Excessive Windows Logon Failures**
- Adjusted rule frequency and lookup window for timely detection.

### 5. Audit & Simulate Security Events
- Enabled object access auditing via **Group Policy**.
- Configured registry auditing for scheduled task access.
- Ran **Unprotect-User** scheduled task and hid it using `PsExec`.
- Verified that password was brute-forced using the malicious task.

### 6. Investigate Incidents
- Viewed and investigated incidents in Microsoft Sentinel using:
  - **Investigation Graph**
  - **Entity timeline**
  - **Alert correlation**

---




