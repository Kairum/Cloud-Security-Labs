
# Configuration and Security of Azure Storage Accounts

## Introduction
This hands-on lab provides experience with configuring and securing an Azure storage account. I will log in to the Azure portal and create a storage account, and then get familiar with the configuration options for it, including replication options, access tiers, and secure transfers. I then RDP into a Windows VM and use Microsoft Azure Storage Explorer to connect to the storage account. I will use Blob storage and attempt to upload and retrieve data from the blob.

## Solution

### Create and Configure a Storage Account
1. In the Azure portal, click Create.
2. Search and select "Storage account". Click Create.
3. Enter a globally unique name (e.g., acgstorage2).
4. Set Redundancy to Locally-redundant storage (LRS).
5. Leave other settings default, click Next: Advanced, then Review, then Create.
6. Click Go to resource.

### Log In to the VM with RDP
1. Connect using public IP and credentials from lab page.
2. Click Continue on certificate warning.

### Open Azure Storage Explorer, Connect to Azure Account, and Upload Images
1. Launch Microsoft Azure Storage Explorer.
2. Sign in with Azure using lab credentials.
3. Under Account Management, click Open Explorer.
4. Expand subscription, storage account, then Blob Containers.
5. Right-click Blob Containers > Create Blob Container named "images".
6. Select "images" container, then Upload > Upload Files.
7. Browse to C:\images, select images, and Upload.

### Enable Security on the Storage Account
#### Identify Access Keys
1. In Azure portal, go to storage account > Access keys.
2. Show and copy key1.

#### Use Access Keys in Storage Explorer
1. In Azure Storage Explorer, click socket icon.
2. Select "Storage account or service" > Account name and key.
3. Enter details, paste key1, and connect.
4. Upload/download images.

#### Revoke Access by Rotating Keys
1. In Azure portal, rotate key1 under Access keys.
2. In Storage Explorer, refresh connection.
3. Authentication Error should appear, confirming revoked access.
