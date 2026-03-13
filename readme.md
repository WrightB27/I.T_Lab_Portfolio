# Windows Server Infrastructure Lab (CorpNet.local)

This project documents the deployment of a Windows Server 2022 domain environment using Oracle VirtualBox. The infrastructure simulates a small enterprise network and demonstrates the configuration of core Windows Server services including Active Directory Domain Services, DNS, and DHCP.

The environment was designed to provide centralized authentication, automated network configuration, and internal name resolution while maintaining security through role-based access control and domain policy enforcement.

## Environment Overview

Domain Name: CorpNet.local  
Domain Controller: DC01  
Client System: Client01-IT  
Server Platform: Windows Server 2022  
Virtualization Platform: Oracle VirtualBox  

## Network Configuration

Subnet: 192.168.0.0/24  
Domain Controller IP: 192.168.0.1  
Default Gateway: 192.168.0.254  

DHCP Scope Range:  
192.168.0.50 – 192.168.0.200  

DNS Server:  
192.168.0.1  

## Implemented Services

Active Directory Domain Services (AD DS)  
Domain-based authentication and centralized directory management

Domain Name System (DNS)  
Internal hostname resolution for domain resources

Dynamic Host Configuration Protocol (DHCP)  
Automated IP address distribution and network configuration

Group Policy and Security Controls  
Password policy enforcement and restricted administrative privileges

## Documentation

The following sections describe the full deployment and configuration process:

1. Design Rationale  
2. Network Topology  
3. Virtualized Deployment Method (VirtualBox)  
4. Active Directory Domain Services Configuration  
5. DNS Configuration  
6. DHCP Configuration  
7. Security and Troubleshooting Considerations  
8. Conclusion

Each section documents the configuration steps used to deploy the infrastructure along with validation procedures used to verify proper operation.

## Purpose of the Lab

This lab demonstrates the practical deployment of a Windows Server domain environment and reinforces core infrastructure concepts including centralized authentication, automated network configuration, internal DNS name resolution, and administrative security controls.

The project serves as documentation of a working Windows Server infrastructure implemented in a controlled virtual environment.