
# Configure Service Principal Authentication for Azure Container Registry

## Overview

This lab demonstrates how to configure a **Service Principal** to authenticate with **Azure Container Registry (ACR)** for secure, automated access. I will verify push/pull permissions, work with container images, and run a containerized ASP.NET app—all without exposing credentials in a production pipeline.

---

## Objectives

- Review ACR permissions granted to a Service Principal
- Authenticate to ACR using a Service Principal
- Push and pull container images from ACR
- Run a container image on a virtual machine

---

## Tools and Prerequisites

- Azure Portal
- Azure Container Registry
- Azure Virtual Machine
- Remote Desktop Client (RDP):
  - **Windows**: Microsoft Remote Desktop
  - **macOS**: Microsoft Remote Desktop
  - **Linux**: Remmina

---

## Steps Performed

### 1. Confirm Service Principal Permissions

- Navigated to the lab’s resource group in the Azure portal.
- Viewed **Role Assignments** under IAM.
- Verified **Push Image** and **Pull Image** permissions granted to the Service Principal under `Microsoft.ContainerRegistry`.

### 2. Prepare Remote Access

- Located the public IP of the provisioned VM and connected via Remote Desktop.
- Logged into the VM using lab credentials.

### 3. Authenticate to ACR via PowerShell

Executed the following in PowerShell on the VM:

```bash
docker login -u <SP_USERNAME> -p <SP_PASSWORD> <REGISTRY_LOGIN_SERVER>
```

Note: Insecure password warning safely ignored due to lab context.

---

### 4. Work with Container Images

- Pulled an ASP.NET sample image:

```bash
docker pull mcr.microsoft.com/dotnet/samples:aspnetapp
```

- Tagged the image for ACR:

```bash
docker tag mcr.microsoft.com/dotnet/samples:aspnetapp <REGISTRY_LOGIN_SERVER>/aspnetapp
```

- Pushed to ACR:

```bash
docker push <REGISTRY_LOGIN_SERVER>/aspnetapp
```

- Listed local Docker images:

```bash
docker image ls
```

- Removed local image:

```bash
docker image rm <IMAGE_ID> -f
```

- Pulled image from ACR to confirm pull permissions:

```bash
docker pull <REGISTRY_LOGIN_SERVER>/aspnetapp
```

- Ran the container:

```bash
docker run -p 8080:8080 -d <REGISTRY_LOGIN_SERVER>/aspnetapp:latest
```

- Verified application running at `http://localhost:8080` on the VM via Internet Explorer.

---

## Security Concepts Demonstrated

- **Service Principal Authentication**: Enables programmatic access without user credentials.
- **Scoped Role Assignment**: Ensures least-privilege access (Push/Pull only).
- **Registry Authentication**: Supports CI/CD and DevOps pipelines securely.

---

## Conclusion

✅ Successfully authenticated a service principal with Azure Container Registry  
✅ Verified permissions for container push and pull  
✅ Deployed and tested a container image via Docker

