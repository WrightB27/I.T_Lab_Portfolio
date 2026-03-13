# Conclusion

The CorpNet.local infrastructure was successfully deployed using Windows Server 2022 within a virtualized Oracle VirtualBox environment. The implementation demonstrated the integration of core enterprise network services including Active Directory Domain Services, DNS, and DHCP within a controlled lab architecture.

Active Directory provides centralized authentication and directory management for the domain. Organizational Units and security groups were implemented to create a structured administrative model that supports role-based access control and efficient policy enforcement across departments.

DNS was configured as an Active Directory–integrated service to provide reliable internal name resolution. This configuration allows domain clients to locate the domain controller and other network resources required for authentication and service discovery. DHCP was deployed to automate IP address distribution and deliver consistent network configuration settings to client systems within the environment.

The virtual lab architecture utilized a dual-adapter network design within Oracle VirtualBox. An internal network adapter supports communication between domain infrastructure systems, while a NAT network adapter provides controlled external connectivity. This configuration mirrors real enterprise lab deployments while maintaining isolation from the host environment.

Security practices were implemented through domain password policies, role-based access control using security groups, and Group Policy enforcement of administrative privileges. These controls ensure that authentication policies and administrative permissions are centrally managed and consistently enforced across domain systems.

The deployment also included validation and troubleshooting procedures to confirm proper service integration. Client testing verified successful domain authentication, DHCP lease assignment, and DNS name resolution. Additional troubleshooting scenarios involving DNS configuration, DHCP scope verification, and virtual network connectivity were resolved through systematic service validation and network diagnostics.

Overall, the completed infrastructure demonstrates the foundational components of a Windows Server domain environment. The lab integrates identity management, name resolution, automated network configuration, and centralized security controls within a structured and scalable architecture. The deployment reflects common enterprise practices used to design, implement, and maintain domain-based Windows network infrastructures.