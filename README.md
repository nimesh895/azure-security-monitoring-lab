# azure-security-monitoring-lab – AZ-900 Hands-On Project

**Project Goal**: Demonstrate core Azure security, governance, networking, monitoring, and cost management concepts through a practical lab deployment.

**Key Achievements**:
- Deployed a secure virtual network with 2 Windows VMs and custom Network Security Groups (NSGs) restricting management access.
- Implemented Azure RBAC using scoped roles to enforce least-privilege principles.
- Applied Azure Policy to restrict VM sizes and regions.
- Integrated Azure Activity Logs and VM events into Log Analytics Workspace.
- Configured Microsoft Sentinel for security monitoring with basic KQL queries.
- Optimized costs to stay under $15 using Azure free credits.

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
├── VM1 (Standard_B1ls, Windows Server)
├── VM2 (Standard_B1ls, Windows Server)
├── Network Security Group (SecureLabNSG) → Restricts RDP to specific IP
├── Log Analytics Workspace (SecureLabLA)
└── Microsoft Sentinel (connected to SecureLabLA)

