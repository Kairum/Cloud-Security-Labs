
# Monitor Storage for Security Events with Azure Monitor

## Introduction
This lab demonstrates how to monitor Azure Blob Storage for security events using Azure Monitor Logs. You will enable diagnostic logging on a storage account and configure alerts for anonymous access attempts.

## Lab Objectives
- Enable diagnostic logging for Blob storage to a Log Analytics workspace
- Upload a file and enable anonymous access
- Query logs using Kusto Query Language (KQL)
- Create an alert for anonymous access attempts

## Steps

### 1. Configure Diagnostic Settings
- Go to the Storage account > Monitoring > Diagnostic settings
- Add a setting for Blob service logs
- Send logs to Log Analytics workspace

### 2. Perform Anonymous Access
- Upload a file to the container
- Change its access level to allow public access
- Access the file from an incognito browser

### 3. Use Azure Monitor Logs to Query Logs
```kql
StorageBlobLogs
| where AuthenticationType == 'Anonymous' and StatusCode == 200
```

### 4. Create an Azure Monitor Alert
- Create an alert rule using the log query
- Set alert threshold to 0
- Set severity to 2 (Warning)

## Outcome
Successful configuration will result in receiving an alert whenever an anonymous access to the storage blob is logged.
