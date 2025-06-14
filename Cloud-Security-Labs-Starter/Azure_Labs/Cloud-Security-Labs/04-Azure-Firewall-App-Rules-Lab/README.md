# Configure Application Level Rules within Azure Firewall

## Overview

This lab demonstrates how to configure application-level rules in Azure Firewall to allow secure, specific outbound access to internet resources from Azure VMs.

## Scenario

Your employer has deployed a secure multi-server architecture consisting of:
- A **jump server** with internet access.
- A **work server** with no internet access, only reachable via the jump server.
- An **Azure Firewall** that restricts internet access for the work server.

I am tasked with enabling secure access to **www.google.com** from the work server by configuring an **application rule** in Azure Firewall.

## Key Tasks

1. **Remote Access**
   - Log in to the Jump VM using RDP.
   - From the Jump VM, RDP into the Work VM using its private IP.

2. **Validate Firewall Restrictions**
   - Attempt to open `http://www.google.com` from the Work VM to verify it's currently blocked.

3. **Configure Azure Firewall Application Rule**
   - Navigate to the Azure Firewall in the portal.
   - Add a new application rule collection with the following details:
     - **Name**: `appcollection`
     - **Priority**: `100`
     - **Action**: `Allow`
     - **Target FQDNs**: `www.google.com`
     - **Protocols**: `http, https`

4. **Validate Rule Enforcement**
   - After deployment, retry accessing `http://www.google.com` from the Work VM.
   - Confirm access is now granted.

## Technologies Used

- Azure Firewall
- Azure Virtual Machines
- RDP (Remote Desktop Protocol)
- Internet Explorer
- Azure Networking

## Security Concepts

- Application-level firewall rules
- Least privilege access
- Controlled internet exposure for internal workloads
