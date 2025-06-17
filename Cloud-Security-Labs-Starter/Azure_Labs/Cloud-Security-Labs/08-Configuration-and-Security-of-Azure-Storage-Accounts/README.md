# 🔐 Configuration and Security of Azure Storage Accounts

## 📘 Introduction
This hands-on lab provides a comprehensive walkthrough for configuring and securing an Azure Storage Account. I will learn how to:

- Create and configure a storage account
- Secure access using shared access signatures (SAS), access keys, and stored access policies
- Upload and retrieve data using Azure Storage Explorer
- Rotate keys and revoke access
- Integrate security best practices

This lab simulates real-world scenarios involving storage security using Microsoft Azure services.

---

## 🧰 Prerequisites

- An active Azure subscription (or lab-provided credentials)
- Remote desktop client:
  - Windows: Microsoft Remote Desktop
  - macOS: Microsoft Remote Desktop
  - Linux: Remmina
- Microsoft Azure Storage Explorer installed on the VM

---

## 🛠️ Lab Steps

### 1. Create and Configure an Azure Storage Account

- In the Azure Portal:
  - Navigate to **Create a resource** → **Storage account**
  - Set a globally unique name (e.g., `acgstorage2`)
  - Choose **Locally-redundant storage (LRS)**
  - Accept defaults → **Review + Create** → **Go to resource**

---

### 2. Connect to a Windows VM via RDP

- Use provided public IP and credentials to RDP into the lab virtual machine
- Accept certificate warnings as needed

---

### 3. Upload Files via Azure Storage Explorer

- Sign in to Azure through Storage Explorer
- Create a blob container named `images`
- Upload image files from `C:\images` into the blob container

---

### 4. Secure the Storage Account

#### 🔑 Access Keys

- In Azure Portal → Storage Account → **Access keys**
- Copy `key1`, then:
  - In Storage Explorer: connect using **Account name and key**
  - Upload/download files
- Rotate `key1` in Azure and observe authentication failure in Explorer

---

#### 🔗 Shared Access Signatures (SAS)

##### SAS #1: Blob Service + Read/List (Service-level only)

- Generate SAS → Connect in Storage Explorer
- Observe read/list limitations (container access denied)

##### SAS #2: Blob Service + Container Access

- Modify SAS to include **Container + Object**
- Attempt upload → Expect **Insufficient credentials** error

##### SAS #3: Blob Service + Write/Add/Create

- Update permissions and generate new SAS
- Upload should now succeed

##### ❌ Revoke Access

- Rotate storage account access key to invalidate all existing SAS tokens
- Observe authentication errors across all SAS connections

---

### 5. Stored Access Policy (SAP)

- In Azure Portal → Container → Access policy:
  - Create `Test-SAP` with full permissions and valid time window
- In Storage Explorer:
  - Generate SAS token using `Test-SAP`
  - Upload and delete files to validate policy
- Delete SAP in portal to revoke access
- Refresh connection in Explorer → Access should now be denied

---

## ✅ Conclusion

- Created and secured an Azure Storage Account
- Explored multiple authentication methods (Access Keys, SAS, SAP)
- Validated permissions and access revocation in real time

This lab reinforces critical concepts in **Azure Storage security**, preparing you for real-world scenarios and certifications such as the **AZ-500**.

---


