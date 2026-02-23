# Enterprise MECM Home Lab – Endpoint Management & Patch Infrastructure

## Project Overview
This project documents the design and deployment of a fully functional Microsoft Endpoint Configuration Manager (MECM) enterprise lab environment built from the ground up in a virtualized network. The objective was to simulate a real-world corporate infrastructure and demonstrate the ability to deploy, configure, and troubleshoot enterprise endpoint management systems.

The environment includes Active Directory Domain Services, DNS, DHCP, SQL Server, WSUS, and a fully operational MECM Primary Site Server with Management Point, Distribution Point, and Software Update Point roles configured. Domain-joined Windows clients were deployed to validate device discovery, client installation, policy retrieval, and software update synchronization.

A primary focus of this lab was successfully configuring and troubleshooting the Software Update Point and WSUS integration to achieve a successful software update synchronization, confirming a fully functional patch management infrastructure similar to what is used in enterprise environments.

## Objectives
- Deploy a complete MECM Current Branch lab environment from scratch
- Integrate SQL Server, WSUS, and Software Update Point roles
- Configure boundaries, discovery methods, and client communication
- Successfully synchronize software updates from Microsoft
- Validate endpoint management and update infrastructure functionality
- Document troubleshooting and log-based diagnostics

## Lab Environment
**Hypervisor:** VirtualBox  
**Domain:** corpnet.local  
**Primary Site Server:** SCCM.corpnet.local  
**Site Code:** HQC  
**Roles Installed:**  
- Management Point  
- Distribution Point  
- Software Update Point  
- Component Server
- Reporting Services Point
- Service connection point 
- Site Database Server
- SMS provider
- Site system


**Supporting Infrastructure:**  
- Active Directory Domain Services  
- DNS & DHCP  
- SQL Server  
- Windows 10 domain-joined clients  

## Architecture Diagram
![MECM Lab Architecture](screenshots/architecture.png) 

## Key Accomplishments
- Built and configured an enterprise-style Windows domain environment
- Installed and configured MECM Primary Site Server
- Integrated WSUS with MECM Software Update Point
- Resolved Software Update Point synchronization and configuration issues
- Achieved successful update synchronization from Microsoft Update
- Validated working enterprise patch management workflow

## Verification
The MECM Software Update Point successfully synchronized with Microsoft Update and began populating the update catalog within the MECM console, confirming a fully operational configuration.

*(Insert screenshot of WSyncMgr.log showing “Sync succeeded” here)*

## Skills Demonstrated
- Microsoft Endpoint Configuration Manager (MECM)
- Windows Server Administration
- Active Directory & Group Policy
- WSUS & Patch Management Infrastructure
- SQL Server Integration
- Enterprise Troubleshooting & Log Analysis
- Virtual Lab Design & Implementation

## Project Status
Core MECM infrastructure deployment and software update synchronization successfully completed. Additional endpoint deployments and application management testing in progress.