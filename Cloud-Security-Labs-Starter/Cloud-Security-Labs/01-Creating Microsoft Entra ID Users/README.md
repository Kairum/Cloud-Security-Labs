# Secure Lifecycle Management of Microsoft Entra ID Users

## Overview

This hands-on lab demonstrates how to manage user identities securely in Microsoft Entra ID. I will walk through the full user lifecycle, from creation to deletion, while applying identity and access management (IAM) best practices to support least privilege and reduce risk.

---

## Learning Objectives

- ✅ Create Microsoft Entra ID user accounts via the Azure Portal
- ✅ Modify user account properties and assign appropriate roles
- ✅ Revoke access to compromised or inactive accounts
- ✅ Delete user accounts and understand soft-delete behavior

---

## Tools and Services Used

- **Microsoft Azure Portal**
- **Microsoft Entra ID**
- **Azure Audit Logs** 

## Security Principles Demonstrated

- 🔐 **Least Privilege** – Assign roles with minimal access needed
- 📜 **Auditability** – Monitor changes using Azure activity logs
- 🚫 **Access Revocation** – Remove access immediately when required
- ♻️ **Lifecycle Management** – Keep identity inventory clean and secure

---

## Lab Steps

### 1. **Create a User**
- Navigate to Microsoft Entra ID > Users > + New user
- Create a user with no admin roles

### 2. **Modify User Account**
- Update user properties such as job title 

### 3. **Revoke Access**
- Revoke sign-in sessions
- Reset password or remove role assignments

### 4. **Delete the User**
- Review soft-deleted users under **Deleted users**
- Permanently delete the user account


## Screenshots

- [x] User Creation Form
- [x] Role Assignment Interface
- [x] Revoke Session Option
- [x] Deleted Users View

---

## Next Steps

- Automate user creation and RBAC assignment with scripts
- Implement Conditional Access policies for MFA enforcement
- Connect Entra ID logs to a SIEM for real-time monitoring

