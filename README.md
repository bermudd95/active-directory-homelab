# 🖥️ Active Directory Home Lab

> Active Directory home lab — from domain setup to PowerShell-automated onboarding workflows. Built as a foundation for enterprise IT support and future AD attack detection.

---

## 📌 Overview

This project is a hands-on Active Directory lab environment built in VMware, designed to develop and demonstrate core enterprise IT administration skills. It progresses through three phases — from basic domain setup to PowerShell-automated user lifecycle management to remote access configuration — mirroring real-world IT support workflows used in corporate environments.

The long-term vision is to expand this lab into an Active Directory attack detection environment, bridging IT operations with security operations and detection engineering.

## 🎯 Motivation

Active Directory is the backbone of enterprise identity and access management — and the #1 attack surface in corporate environments. Understanding AD from the admin side builds the foundation for both IT support operations and, eventually, detecting adversarial techniques like Kerberoasting, Pass-the-Hash, and Golden Ticket attacks.

This lab was built to:
- Gain hands-on experience with AD administration in a corporate-style environment
- Develop and document repeatable onboarding/offboarding workflows
- Automate common IT tasks using PowerShell
- Create SOP documentation that reflects real-world IT support standards
- Establish a foundation for future AD-focused threat detection and security monitoring

## 🏗️ Architecture

| Component | Details |
|---|---|
| **Hypervisor** | VMware |
| **Domain Controller** | Windows Server 2022 (Evaluation) |
| **Client Machine** | Windows 10/11 (Domain-Joined) |
| **Domain Name** | TBD |
| **Network** | NAT / Host-Only (VMware) |
| **Scripting** | PowerShell (Active Directory Module) |

> 📎 *A detailed architecture diagram and network layout can be found in [`docs/architecture.md`](docs/architecture.md)*

## 📂 Repository Structure
active-directory-homelab/ │ ├── README.md │ ├── docs/ │ ├── scope.md │ ├── architecture.md │ └── lessons-learned.md │ ├── phase-1-setup/ │ ├── README.md │ ├── screenshots/ │ └── notes.md │ ├── phase-2-onboarding/ │ ├── README.md │ ├── screenshots/ │ ├── scripts/ │ │ ├── New-ADUserOnboard.ps1 │ │ └── Disable-ADUserOffboard.ps1 │ └── sop/ │ ├── onboarding-sop.md │ └── offboarding-sop.md │ ├── phase-3-remote-access/ │ ├── README.md │ ├── screenshots/ │ └── notes.md │ └── LICENSE


## 🔄 Phases

### Phase 1: Domain Setup & AD Navigation `🟢 In Progress`
- Install and configure Windows Server 2022 as a Domain Controller
- Promote server to DC and configure AD DS
- Create Organizational Units (OUs), user accounts, and security groups
- Practice core admin tasks: password resets, account lockouts, account disabling
- Explore Group Policy basics

### Phase 2: Onboarding & Offboarding Workflows `⬜ Planned`
- Join a Windows 10/11 client VM to the domain
- Simulate full user onboarding: account creation → group assignment → GPO application → domain login verification
- Simulate user offboarding: disable account → remove groups → move to "Terminated" OU
- Write PowerShell automation scripts for onboarding and offboarding
- Document both workflows as formal SOPs

### Phase 3: Remote Access & Group Policy `⬜ Planned`
- Configure Remote Desktop with AD-authenticated access
- Install and configure OpenSSH Server with AD authentication
- Manage access control through AD security groups (e.g., `SSH_Users`, `RDP_Users`)
- Enforce Group Policy Objects: password policies, drive mapping, software deployment
- Troubleshoot GPO application with `gpresult /r`

### Future: AD Attack Detection (Cybersecurity Extension) `⬜ Roadmap`
- Integrate with Elastic Security / Sysmon for endpoint telemetry
- Simulate common AD attacks (Kerberoasting, Pass-the-Hash, DCSync)
- Write custom detection rules (KQL/EQL) mapped to MITRE ATT&CK
- Expand into the existing [SOC Threat Detection portfolio](https://soc-secengportfolio.vercel.app)

## 🛠️ Tools & Technologies

- **VMware** — Hypervisor for VM management
- **Windows Server 2022** — Domain Controller and AD DS
- **Windows 10/11** — Domain-joined client machine
- **PowerShell** — AD administration and automation scripting
- **Active Directory Users and Computers (ADUC)** — GUI-based AD management
- **Group Policy Management Console (GPMC)** — GPO creation and management
- **OpenSSH** — Remote access via SSH with AD authentication

## 📚 Key Learnings

Documented in [`docs/lessons-learned.md`](docs/lessons-learned.md) — updated as each phase is completed. Includes mistakes made, troubleshooting steps, and insights gained.

## 🔗 Related Projects

| Project | Description |
|---|---|
| [SOC Threat Detection & SIEM Suite](https://soc-secengportfolio.vercel.app) | 9-lab SOC portfolio with KQL/EQL queries and MITRE ATT&CK mapping |
| [ApexIntel](https://github.com/bermudd95) | Automated CTI pipeline ingesting CISA KEV and EPSS feeds |
| [Mobile Threat Triage Engine](https://github.com/bermudd95) | iOS network traffic analysis tool — zero-dependency threat hunting |

## ✍️ Author

**Danny Bermudez**
- 🔗 [Portfolio](https://soc-secengportfolio.vercel.app)
- 💼 [LinkedIn](https://linkedin.com/in/danny-bermudez-81b704190)
- 🐙 [GitHub](https://github.com/bermudd95)
