
# Enabling Always Encrypted in Azure SQL

## Introduction
I am assuming the role of a cloud data engineer. I have been asked to ensure customer data is always encrypted at rest. Staff such as administrators and backup operators should not have access to customer data, even when using tools like SQL Server Management Studio. The unencrypted data should only be available to the application. In this hands-on lab, I will create an Azure SQL database and an Azure key vault, encrypt data using SQL Server Management Studio (SSMS), and view encryption results.

## Solution

### Log in to the Azure portal using the credentials provided on the lab page.

### Note: To complete this lab, I will need to use a remote desktop client.
- Windows: Microsoft Remote Desktop on Windows 10
- MacOS: Microsoft Remote Desktop
- Linux: Remmina

### Create a SQL Server and SQL Database
1. Create an Azure SQL database with the following configuration:
   - Database name: sampledb1
   - Server: create new with SQL auth (cloud_user / Lab-VM1 password)
   - Compute: Standard tier, 200 DTUs
   - Connectivity: Public endpoint, allow Azure services
   - Data source: Use Sample data

### Create an Azure Key Vault
1. Deploy Azure Key Vault in the same resource group and region.
2. Set permission model to Vault access policy.
3. Grant full key permissions to "Cloud Student".

### Use RDP to Connect to the Virtual Machine
1. Locate VM public IP in Azure portal.
2. Use Microsoft Remote Desktop to connect using Lab-VM credentials.
3. Set Microsoft Edge as default browser.

### Connect to SQL Server
1. Use SQL Server Management Studio (SSMS) on the VM.
2. Connect using server name and SQL auth credentials.

### Encrypt SQL Server Data
1. Navigate to SalesLT.Customer table > Select Top 1000 Rows to view plaintext.
2. Right-click table > Encrypt Columns... wizard.
3. Encrypt FirstName, MiddleName, LastName using Deterministic encryption.
4. Use Azure Key Vault for master key.
5. Complete the encryption process via the wizard.
6. Re-select top rows and verify encryption is applied.

---

This lab demonstrates how to use **Always Encrypted** with **Azure SQL** to secure sensitive data even from privileged access.
