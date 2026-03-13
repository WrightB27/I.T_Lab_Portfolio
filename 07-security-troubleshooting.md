# Security and Troubleshooting Considerations

This section documents the security controls implemented within the **CorpNet.local** environment and outlines the troubleshooting procedures used during deployment of Active Directory, DNS, and DHCP services. These measures ensure the domain infrastructure remains secure, stable, and easier to manage as additional systems are introduced into the network.

## Security Considerations

Security within the domain environment is enforced through centralized identity management and Group Policy within Active Directory.

A domain password policy was implemented to strengthen authentication security across all domain accounts. The policy enforces a **minimum password length of 12 characters**, requires **password complexity**, and limits authentication attempts through a **three-attempt account lockout threshold**. These settings significantly reduce the likelihood of brute-force password attacks while maintaining reasonable usability for legitimate users.

Administrative privileges are controlled through the **Local_Admins** security group. Rather than assigning administrative permissions directly to user accounts, elevated rights are granted through group membership. This approach follows the principle of centralized privilege management and ensures administrative access can be modified quickly without editing permissions on individual systems.

The **Restricted Groups** policy was implemented through Group Policy to enforce membership within the local **Administrators** group on domain systems. This policy ensures that only authorized members of the **Local_Admins** group retain administrative privileges. If a user attempts to manually add unauthorized accounts to the local Administrators group, Group Policy will automatically revert the membership back to the approved configuration.

Centralizing permissions through Active Directory groups and enforcing membership through Group Policy provides a scalable method of controlling administrative access as the environment grows.

Additional security practices were also followed during deployment. Infrastructure servers such as **DC01** were assigned **static IP addresses** to ensure consistent network communication and prevent address changes that could disrupt domain services. Only required roles were installed on the server, reducing the overall attack surface of the system.

These practices establish a foundational security posture appropriate for a small enterprise domain environment.

## Active Directory Authentication Issues

One of the most common issues encountered in a domain environment occurs when a client system fails to join the domain or authenticate properly. In most cases this issue is related to incorrect DNS configuration.

Domain clients must use the **domain controller as their preferred DNS server**. If a client device is configured to use an external DNS server such as a public resolver, it will not be able to locate the domain controller or resolve internal domain records required for authentication.

Administrators should verify that client systems are configured to use **DC01 (192.168.0.1)** as their DNS server. Correct DNS configuration allows the client to locate domain services and successfully complete the domain join process.

## DNS Name Resolution Failures

DNS functionality must be verified to ensure that domain resources can be located correctly within the **CorpNet.local** environment.

Administrators can test DNS functionality using the **nslookup** command to confirm that hostnames resolve correctly. This test verifies that the DNS server is responding to queries and returning the correct records.

Administrators should also confirm that the necessary DNS records exist within the forward lookup zone. This includes verifying that **A records** exist for domain systems and that the domain controller has properly registered its service records within the **CorpNet.local** zone.

Proper DNS record registration ensures that domain services such as authentication and resource discovery function correctly across the network.

## DHCP Address Assignment Problems

If a client system fails to obtain an IP address automatically, the DHCP service should be examined to determine the source of the problem.

Administrators should verify that the **DHCP Server service is running**, confirm that the server is **authorized within Active Directory**, and ensure that the **DHCP scope is active** with available addresses remaining in the configured range.

If a client device receives an address in the **169.254.x.x range**, this indicates that the system has assigned itself an **Automatic Private IP Address (APIPA)** because it was unable to contact the DHCP server.

Client systems can be forced to request a new DHCP lease using the following commands:

ipconfig /release
ipconfig /renew


The **ipconfig /all** command can also be used to confirm that the correct gateway, subnet mask, and DNS server information have been assigned.

These diagnostic steps help administrators quickly identify whether the issue originates from DHCP configuration, network connectivity, or client settings.

## VirtualBox Networking Issue Resolution

During the lab deployment process, an issue occurred where the Windows Server system was unable to reach external network resources. While internal communication between virtual machines functioned correctly, the server could not access the internet to download updates or retrieve external resources.

This issue was resolved by configuring a **second network adapter** within **VirtualBox** using **NAT Network mode**.

The first network adapter remained connected to the internal lab network, which allowed communication between domain systems such as the domain controller and client machines. The second adapter provided a NAT connection to the host system’s internet access.

With this configuration, the internal domain environment remained isolated from external networks while still allowing the server to access the internet when required for updates or software installation.

This dual-adapter design separates **internal infrastructure communication** from **external network connectivity**, which is a common practice in virtualization labs.

## Summary

Security within the **CorpNet.local** environment is enforced through centralized authentication policies, controlled administrative privileges, and consistent group-based permission management. These controls help ensure that administrative access remains restricted and manageable across the domain.

Troubleshooting procedures focus on verifying DNS configuration, DHCP scope functionality, and virtual network connectivity. Following a structured troubleshooting approach allows administrators to quickly isolate configuration issues and restore normal operation of critical network services.