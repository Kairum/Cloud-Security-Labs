# Securely Access Script Secrets in Azure Key Vault

## Overview
This hands-on lab demonstrates how to securely access secrets in Azure Key Vault from a virtual machine using managed identities and Azure Private Link. It simulates a scenario where hardcoded secrets in PowerShell scripts are replaced with secure programmatic access via Key Vault.

## Scenario
You are a security engineer tasked with improving the security of automation scripts on a VM that currently uses plain-text secrets. The goal is to:
- Store secrets in Azure Key Vault
- Use a managed identity for secure authentication
- Ensure communication to Key Vault is private using Azure Private Link

## Lab Objectives
- Enable user-assigned managed identity on the VM
- Assign Key Vault Secrets Officer role
- Create a Key Vault with private endpoint access only
- Use PowerShell to connect to Azure via managed identity
- Store and retrieve secrets securely from Key Vault

## Key Azure Services Used
- Azure Key Vault
- Azure Private Link
- Azure Virtual Machine
- Managed Identities
- PowerShell (Az Module)

## PowerShell Script Sample
```powershell
Connect-AzAccount -Identity
$secret = Read-Host -AsSecureString
$kv = Get-AzKeyVault
Set-AzKeyVaultSecret -VaultName $kv.VaultName -Name MySecret -SecretValue $secret
Get-AzKeyVaultSecret -VaultName $kv.VaultName -name MySecret -AsPlainText
```

## Learning Outcome
This lab teaches secure authentication techniques in Azure, secret management using Key Vault, and the use of private endpoints for improved security posture.

---
*This lab was completed as part of my transition into a Cloud Security Engineer role.*
