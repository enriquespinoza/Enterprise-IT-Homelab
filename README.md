# Enterprise IT Homelab

A hands-on enterprise IT infrastructure lab built to develop practical experience with virtualization, networking, systems administration, automation, cybersecurity, and container orchestration.

The lab is centered around **Proxmox Virtual Environment (PVE)** and is being developed incrementally to simulate technologies and operational practices found in enterprise IT environments.

## Project Objectives

The homelab is designed to provide hands-on experience with:

- Proxmox VE virtualization
- Linux and Windows server administration
- Virtual machines and containers
- TCP/IP networking and network troubleshooting
- Virtual switches and Linux bridges
- Infrastructure documentation
- Remote systems administration
- Network segmentation
- Active Directory and identity management
- DNS and DHCP
- PowerShell and infrastructure automation
- Kubernetes and container orchestration
- Monitoring and logging
- Cybersecurity controls and system hardening

The repository documents both the implementation process and troubleshooting encountered while building the environment.

---

## Current Architecture

The current environment uses a dedicated physical system running **Proxmox VE** as the virtualization host.

Current network design:

```text
                    Home Network / Internet
                              |
                         Wi-Fi Network
                              |
                    TP-Link Wireless Bridge
                              |
                           Ethernet
                              |
                         Network Switch
                              |
                       Proxmox VE Host
                              |
                            vmbr0
                              |
               +--------------+--------------+
               |              |              |
             VM/CT          VM/CT        Future VM/CT
```

The wireless bridge is used because a direct Ethernet connection to the primary router is not currently available at the Proxmox host location.

---

## Current Implementation Status

### Completed

- Installed Proxmox Virtual Environment
- Configured the physical system as a dedicated virtualization host
- Established access to the Proxmox VE management interface
- Configured initial network connectivity
- Implemented a Wi-Fi-to-Ethernet path for the virtualization host
- Connected the host through network switching infrastructure
- Began working with Proxmox Linux bridge networking
- Established a dedicated GitHub repository for infrastructure documentation
- Configured a local Git/VS Code workflow for maintaining the project

### In Progress

- Documenting the physical and logical network architecture
- Validating Proxmox bridge configuration
- Building the initial VM/container environment
- Improving remote administration
- Documenting troubleshooting procedures

### Planned

- Windows Server deployment
- Active Directory Domain Services
- DNS and DHCP services
- Linux server deployment
- VLAN/network segmentation
- Firewall policy testing
- PowerShell automation
- Infrastructure monitoring
- Centralized logging
- Kubernetes cluster
- Containerized services
- Backup and recovery testing
- Additional physical NIC/networking experimentation
- Security hardening
- AI-assisted infrastructure administration experiments

---

## Repository Structure

```text
Enterprise-IT-Homelab/
|
+-- README.md
+-- docs/
|   +-- architecture.md
|   +-- networking.md
|   +-- proxmox.md
|   +-- troubleshooting.md
|   +-- roadmap.md
|
+-- diagrams/
|
+-- scripts/
|
+-- .gitignore
```

### Documentation

**architecture.md**

Documents the physical and logical architecture of the lab.

**networking.md**

Documents addressing, switching, bridges, network interfaces, and future network segmentation.

**proxmox.md**

Documents Proxmox VE installation, configuration, virtualization, storage, and administration.

**troubleshooting.md**

Records technical problems, diagnostic commands, root causes, and resolutions.

**roadmap.md**

Tracks future infrastructure projects and planned improvements.

### Scripts

The `scripts/` directory will contain PowerShell, Bash, and other automation developed for the environment.

### Diagrams

The `diagrams/` directory will contain network and infrastructure diagrams as the environment expands.

---

## Technologies

| Area | Technologies |
|---|---|
| Hypervisor | Proxmox VE |
| Virtualization | KVM / LXC |
| Networking | TCP/IP, Ethernet, Wi-Fi bridge, Linux bridge |
| Administration | Linux CLI, SSH, Proxmox Web UI |
| Version Control | Git / GitHub |
| Development | Visual Studio Code |
| Automation | PowerShell / Bash |
| Planned Identity | Windows Server / Active Directory |
| Planned Containers | Docker / Kubernetes |
| Planned Security | Segmentation, firewalling, hardening, logging |

---

## Documentation Philosophy

This repository documents the environment as it is actually built.

Technologies listed as **planned** are not considered implemented until they have been deployed, configured, tested, and documented.

Configuration changes and troubleshooting steps are recorded to create a reproducible history of the lab's development.

---

## Security

Sensitive infrastructure information should not be committed to this repository.

This includes:

- Passwords
- API keys
- Private keys
- Authentication tokens
- Certificates containing private keys
- Personally identifiable information
- Sensitive configuration exports

IP addressing and diagrams may also be generalized where appropriate for public documentation.

---

## Roadmap

The long-term goal is to evolve the environment from a single Proxmox virtualization host into a small enterprise-style infrastructure lab supporting:

```text
Virtualization
      |
Networking
      |
Identity & Access Management
      |
Windows + Linux Infrastructure
      |
Automation
      |
Monitoring & Logging
      |
Cybersecurity
      |
Containers / Kubernetes
```

Each major implementation will be documented through this repository.