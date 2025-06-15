# Ensuring Compliance with Azure Policies

## 📘 Introduction

This hands-on lab demonstrates how Azure Policy can be used by security engineers to enforce compliance standards across Azure resources. I will learn how to assign policies that:
- Require cost allocation tags on resource groups.
- Ensure newly deployed resources inherit those tags automatically.

These tagging strategies are critical for financial accountability, governance, and operational insights in large-scale Azure environments.

---

## 🛠️ Lab Objectives

1. Assign a policy that **requires resource groups to include a 'Cost Allocation' tag**.
2. Assign a policy that **automatically inherits the 'Cost Allocation' tag for all resources** within a tagged resource group.
3. Create and test compliant and non-compliant resources.
4. **Remediate existing resources** that do not comply with policy.

---

## 🚀 Steps Performed

### 1. Assign Azure Policies

#### 🔒 Block Resource Groups Without a Tag
- **Policy Assigned**: *Require a tag on resource groups*
- **Tag Required**: `Cost Allocation`
- **Custom Message**: "Resource groups must have a cost allocation tag for financial reporting and chargeback."

#### 🔁 Inherit Tags for Deployed Resources
- **Policy Assigned**: *Inherit a tag from the resource group if missing*
- **Tag Inherited**: `Cost Allocation`
- Enabled remediation with a **User-assigned Managed Identity**

---

### 2. Create and Test Resources

#### 🏷️ Add Tags to Resource Group
- Added `Cost Allocation: IT` to the lab resource group.

#### 🌐 Deploy Resources
- **PolicyVnet1** created before policies – does NOT have the tag.
- **PolicyVnet2** created after policies – automatically inherited the tag.

---

### 3. Remediation

#### 🔧 Trigger Remediation
- Ran remediation task to apply missing tags to existing resources.
- Successfully updated **PolicyVnet1** with the `Cost Allocation` tag post-remediation.

---

## ✅ Outcomes

| Resource        | Tagged Automatically? | Tagged via Remediation? |
|----------------|------------------------|--------------------------|
| PolicyVnet1     | ❌                    | ✅                       |
| PolicyVnet2     | ✅                    | N/A                      |

---

## 🧠 Key Skills Demonstrated

- Azure Policy creation and assignment  
- Tag governance for financial reporting  
- Tag inheritance using managed identities  
- Compliance remediation of existing resources  
- Role of Azure Policy in automated governance

---

## 🏁 Conclusion

This lab showcased how Azure Policies enable cloud security and compliance teams to enforce governance rules at scale. I learned how to block non-compliant resources, automatically inherit critical metadata, and remediate legacy infrastructure with minimal manual effort.
