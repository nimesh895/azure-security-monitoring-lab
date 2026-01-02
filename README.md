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


## Step-by-Step Implementation

### 1. Portal Sign-In and Resource Group Creation
![Sign in to portal](sign_in_to_portal.png)
![Creating resource group](creating_resource_group_SecureLabRG.png)

### 2. Virtual Network and Subnet Setup
![Creating VNet inside RG](creating_vnet_inside_RG.png)
![VNet completely deployed](vnet_completely_deployed.png)

### 3. Deploying Virtual Machines
![Creating Azure Virtual Machine 1](creating_azure_virtual_machine1.png)
![VM created successfully](vm_created_successfully.png)
![Creating VM2](creating_Vm2.png)

### 4. Network Security Group (Restricted RDP Access)
![Creating network security group](creating_network_security_group.png)
![Add NSG rule allow my public IP](add_nsg_rule_allow_my_public_ip.png)

### 5. RDP Connectivity Test
![Check RDP login to Azure from built-in Windows Remote Desktop](check_RDP_login_to_azure_from_builtin_windows_remote_desktop.png)

### 6. Role-Based Access Control (RBAC) – Scoped Least-Privilege
![Assign VM1 role Virtual Machine Contributor](assign_vm1_role_virtual_machine_contributor.png)
![Roles Owner and Contributor](roles_owner_and_contributor.png)

### 7. Azure Policy Enforcement
![Trying to assign policy](trying_to_assign_policy.png)
![Policy assign](policy_assign.png)
![Policy assign2](policy_assign2.png)
![Policy successfully assigned](policy_successfully_assigned.png)

### 8. Log Analytics Workspace and Diagnostic Settings
![Creating Log Analytics workspace](creating_log_analytics_workspace.png)
![VM1 diagnostic settings](vm1_diagnostic_settings.png)

### 9. Microsoft Sentinel Configuration
![Configure Microsoft Sentinel](configure_microsoft_sentinel.png)

### 10. KQL Query Example in Sentinel (Security Event Investigation)
![Run KQL query](run_kql_query.png)

## Cost Management
- Used **Standard_D4s_v3** VMs (4 vCPUs, 16 GiB RAM) for better performance during lab exercises.
- Monitored costs regularly via Cost Management + Billing.
- Deallocated VMs when not in use and deleted the entire resource group at project completion to avoid ongoing charges.
- Leveraged free tiers for Log Analytics (first 5 GB/month) and Sentinel ingestion. with Azure free credits.

## Cleanup
All resources were deployed in a single resource group `SecureLabRG` and deleted at the end to avoid ongoing charges.

## Conclusion
This lab provided hands-on experience with Azure networking, identity, governance, monitoring, and security — directly aligning with AZ-900 certification objectives and real-world cloud security practices.

**Portfolio-ready proof of AZ-900 skills in security, compliance, and monitoring.**

---

*Repository maintained by [Nimesh Akalanka] – Azure enthusiast & AZ-900 certified.*
