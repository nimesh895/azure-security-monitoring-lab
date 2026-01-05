# azure-security-monitoring-lab – AZ-900 Hands-On Project

**Project Goal**: Demonstrate core Azure security, governance, networking, monitoring, and cost management concepts through a practical lab deployment.

**Key Achievements**:
- Deployed a secure virtual network with 2 Windows VMs and custom Network Security Groups (NSGs) restricting management access.
- Implemented Azure RBAC using scoped roles to enforce least-privilege principles.
- Applied Azure Policy to restrict VM sizes and regions.
- Integrated Azure Activity Logs and VM events into Log Analytics Workspace.
- Configured Microsoft Sentinel for security monitoring with basic KQL queries.
- Kept total lab cost low by monitoring usage and cleaning up resources promptly.

**Azure Services Used**:
- Virtual Machines
- Virtual Network
- Network Security Groups
- Microsoft Entra ID (RBAC)
- Azure Policy
- Log Analytics Workspace
- Microsoft Sentinel

## Lab Architecture Overview

Resource Group (SecureLabRG)
├── Virtual Network (SecureLabVNet)
│   └── Subnet (default)
├── VM1 (Standard_D4s_v3, 4 vCPUs, 16 GiB RAM, Windows Server)
├── VM2 (Standard_D4s_v3, 4 vCPUs, Windows Server)
├── Network Security Group (SecureLabNSG) → Restricts RDP to specific IP
├── Log Analytics Workspace (SecureLabLA)
└── Microsoft Sentinel (connected to SecureLabLA)



## Detailed Step-by-Step Implementation

### 1. Azure Portal Access & Resource Group Creation
Initialized the lab environment by creating a dedicated resource group for easy management and cleanup.

![Sign in to portal](sign_in_to_portal.png)  
![Creating resource group](creating_resource_group_SecureLabRG.png)

### 2. Virtual Network Deployment
Created an isolated virtual network with a default subnet to host the VMs securely.

![Creating VNet inside RG](creating_vnet_inside_RG.png)  
![VNet completely deployed](vnet_completely_deployed.png)

### 3. Virtual Machine Deployment
Deployed two Windows Server VMs using Standard_D4s_v3 size for reliable performance during security testing and monitoring exercises.

![Creating Azure Virtual Machine 1](creating_azure_virtual_machine1.png)  
![VM created successfully](vm_created_successfully.png)  
![Creating VM2](creating_Vm2.png)

### 4. Network Security Hardening
Created a custom Network Security Group and applied inbound rules to allow RDP (port 3389) **only from my public IP**, significantly reducing the attack surface.

![Creating network security group](creating_network_security_group.png)  
![Add NSG rule allow my public IP](add_nsg_rule_allow_my_public_ip.png)

### 5. Validating Secure Remote Access
Successfully tested RDP connectivity using Windows Remote Desktop client, confirming NSG restrictions work as intended.

![Check RDP login to Azure from built-in Windows Remote Desktop](check_RDP_login_to_azure_from_builtin_windows_remote_desktop.png)

### 6. Implementing Role-Based Access Control (RBAC)
Applied least-privilege principles by assigning scoped roles:
- Owner at resource group level (full control)
- Virtual Machine Contributor at individual VM level (limited to VM management only)

This demonstrates understanding of permission scoping and defense against privilege escalation.

![Assign VM1 role Virtual Machine Contributor](assign_vm1_role_virtual_machine_contributor.png)  
![Roles Owner and Contributor](roles_owner_and_contributor.png)

### 7. Azure Policy for Governance
Configured and assigned built-in policies to:
- Restrict allowed VM sizes
- Enforce allowed regions

Tested compliance by attempting non-compliant deployments (which were blocked).

![Trying to assign policy](trying_to_assign_policy.png)  
![Policy assign](policy_assign.png)  
![Policy assign2](policy_assign2.png)  
![Policy successfully assigned](policy_successfully_assigned.png)

### 8. Centralized Logging Setup
Created a Log Analytics workspace and configured diagnostic settings to collect VM and platform logs.

![Creating Log Analytics workspace](creating_log_analytics_workspace.png)  
![VM1 diagnostic settings](vm1_diagnostic_settings.png)

### 9. Microsoft Sentinel Deployment
Enabled Microsoft Sentinel on the Log Analytics workspace to provide SIEM capabilities and threat detection.

![Configure Microsoft Sentinel](configure_microsoft_sentinel.png)

### 10. Security Investigation with KQL
Executed KQL queries in Sentinel/Log Analytics to analyze ingested events (e.g., security, activity, and system logs).

![Run KQL query](run_kql_query.png)

## Cost Management & Responsible Practices

- Selected **Standard_D4s_v3** VMs for stable performance during extended testing.
- Regularly monitored costs via **Cost Management + Billing**.
- Deallocated VMs when not actively used.
- Deleted the entire resource group upon completion to eliminate all charges.
- Utilized free tiers for Log Analytics (first 5 GB/month) and Sentinel data ingestion.

**Result**: Responsible use of Azure free credits with full awareness of billing implications.

## Cleanup & Sustainability

All resources were contained within a single resource group (`SecureLabRG`). At project completion, the resource group was deleted, ensuring **zero ongoing costs**.

## Conclusion & Value to Employers

This project proves I can:
- Design and secure Azure infrastructure from scratch.
- Apply governance and compliance controls.
- Implement centralized monitoring and basic threat investigation.
- Manage costs effectively in a real cloud environment.

These are **essential day-to-day skills** for roles involving Azure administration, cloud operations, security monitoring, or support.

**Ready to contribute immediately** with practical, certification-backed Azure knowledge.

---

*Built and maintained by Nimesh Akalanka*  
*Microsoft Certified: Azure Fundamentals (AZ-900)*  

---

