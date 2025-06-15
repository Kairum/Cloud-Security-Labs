# Securely Connect a Web App to Azure SQL Database Using Private Link

## Overview

This lab demonstrates how to securely connect an Azure Web App to an Azure SQL Database using **Private Link**, **VNet Integration**, and **firewall rules**. These configurations ensure secure, private access across Azure resources without exposure to the public internet.

---

## Objectives

- Create and configure a new Azure SQL Database.
- Configure a Web App to securely access the SQL Database.
- Enable Private Endpoint on the SQL Server.
- Set up VNet Integration for the Web App.
- Test secure connectivity between the App and the SQL Database.

---

## Architecture Components

- Azure App Service (Web App)
- Azure SQL Database
- Virtual Network with Subnet
- Private Endpoint for SQL Server

---

## Steps Performed

### 1. Create Azure SQL Database

- Created SQL Server and SQL Database in the same region as the App Service.
- Enabled SQL authentication and configured basic compute/storage tier.

### 2. Configure SQL Server Firewall

- Set Public Access to `Selected Networks`.
- Added client IP and allowed Azure services access.
- Executed SQL query in Query Editor to create a `Todo` table.

### 3. Configure Web App Environment

- Retrieved the SQL connection string (ADO.NET).
- Added the connection string as an App Setting in the Web App.
- Verified that the Web App can connect and write to the database.

### 4. Setup VNet Integration

- Connected the Web App to a virtual network (`vnet1`) and subnet (`subnet1`).

### 5. Enable Private Endpoint for SQL Server

- Disabled public network access to SQL Server.
- Created a Private Endpoint for SQL Server in the same VNet.

---

## Validation

- Successfully created and retrieved `Todo` items from the Web App after private connectivity was enforced.
- Verified database access was available only via the private endpoint.

---

## Key Security Features Used

- **Azure Private Link**: Secure access to Azure SQL over a private IP.
- **App Service VNet Integration**: Enables outbound calls from the Web App to Azure services via VNet.
- **Firewall Restrictions**: Public traffic blocked; only VNet traffic allowed.

---

## Conclusion

This lab showcases how to implement secure, production-grade architecture in Azure by combining platform-as-a-service (PaaS) resources with advanced network isolation.
