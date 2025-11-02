
# Active Directory Simulation – Adex Technologies

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **Adex Technologies**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**Adex Technologies** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8.1 Client PC (IT Department)
- 1 x Windows 8.1 Client PC (Sale Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.2.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8.1)   PC2 (Win 8.1)
```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 10.0.2.4  | AD Domain Controller (DC)   |
| Windows 8.1 PC  |  10.0.2.3   | IT Department           |
| Windows 8.1 PC | 10.0.2.15    | Sales Department               |

---

## Domain Configuration

- **Domain Name**: `Adex.local`
- **Server Name**: `Adex-Technologies`
- **Static IP**: `10.0.2.4`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
Adex.local
├── OU: IT Department
│   └── Users: Chisanzo.IT
    └── Users: Oluwaseyi.IT

├── OU: Sales
│   └── Users: Ibukun.Sales
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisableShutdown`
- **Linked to**: OU: EKITI(IT Department)
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `System` > `Removable Storage Access`
  - Set **"Remove and prevent access to shut down, restart, sleep and hibernate comands"** to **Enabled**

Result: Access to shutdown, restart or sleep is disabled for all users in the **EKITI(IT DEPARTMENT) OU**.

---

## Screenshots

- AD Domain Structure
- 
- GPO Editor Screenshot
- PC joined to domain
- Result of denied access to Shutdown, restart or Sleep

---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

**Oluwaseyi J. Adedire**  
Cybersecurity Analyst  
