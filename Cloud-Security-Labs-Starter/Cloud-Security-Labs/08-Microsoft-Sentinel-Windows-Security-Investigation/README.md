# Investigate Windows Security Events with Microsoft Sentinel

## Overview

This hands-on lab walks through the configuration of Microsoft Sentinel to monitor and investigate security events on a Windows VM. You'll deploy Sentinel, configure connectors, simulate suspicious activity, and perform incident investigations.

---

## Learning Objectives

- 🛠️ Deploy Microsoft Sentinel and enable it on a Log Analytics workspace
- 🔗 Add and configure the **Windows Security Events** solution
- 📡 Collect Windows security event logs using data connectors
- 🔍 Enable and tune analytics rules to detect suspicious behavior
- ⚠️ Simulate security events and use the Sentinel investigation graph

---

## Tools and Services Used

- Microsoft Sentinel (SIEM)
- Azure Log Analytics
- Windows Virtual Machine (Audit and Event Logs)
- Kusto Query Language (KQL)
- Azure Resource Manager

---

## Lab Steps

### 1. Deploy Microsoft Sentinel
- Navigate to Microsoft Sentinel > Select a workspace > Enable Sentinel

### 2. Add the Windows Security Events Solution
- Go to Content Hub in Sentinel
- Search for and install **Windows Security Events**

### 3. Configure the Data Connector
- Navigate to **Data connectors**
- Select Windows Security Events > Connect
- Link the existing Windows VM for log forwarding

### 4. Configure Analytics Rules
- Enable:
  - **Scheduled Task Hide**
  - **Excessive Windows Logon Failures**
- Adjust each rule:
  - Run every 5 minutes
  - Match events from the last 5 minutes or 1 day as appropriate

### 5. Modify the Windows VM Audit Policy
- Enable success auditing for Registry object access:
  - `Advanced Audit Policy Configuration > Audit Policies > Object Access > Audit Registry`

- Enable auditing for registry key:
  - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule`

### 6. Simulate Attacks
- Run these PowerShell commands:
```powershell
C:\Scripts\PsExec64.exe -accepteula -i -s cmd.exe
REG DELETE "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tree\Unprotect-User" /v SD /f
```

### 7. Investigate in Microsoft Sentinel
- Use the **investigation graph** to analyze incidents and map attack paths

---

## Optional Enhancements

- Integrate with Microsoft Defender for Endpoint for advanced signals
- Create automated playbooks for incident response
- Connect Sentinel to external data sources like AWS GuardDuty

---

## Screenshots

- [x] Sentinel Dashboard
- [x] Analytics Rules Configuration
- [x] Event Logs in Log Analytics
- [x] Investigation Graph Output

---

## Author

**Kairu Mambo**  
Cloud Security Engineer (Aspiring)  
[GitHub Portfolio](https://github.com/) | Charlotte, NC
