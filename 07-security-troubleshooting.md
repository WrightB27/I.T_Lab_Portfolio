# Security and Troubleshooting Considerations

This section outlines security practices implemented in the CorpNet.local environment as well as troubleshooting steps taken during the deployment of Active Directory, DNS, and DHCP services.

## Security Considerations

Security within the domain environment is enforced through centralized management using Active Directory and Group Policy.

A domain password policy was configured to strengthen authentication security. The policy enforces a **minimum password length of 12 characters**, requires **password complexity**, and limits authentication attempts through a **three-attempt account lockout threshold**. These settings reduce the risk of brute-force password attacks while maintaining usability for legitimate users.

Administrative privileges are restricted through the **Local_Admins** security group. Instead of granting elevated permissions to individual user accounts, administrative rights are assigned through group membership. This approach simplifies management and ensures that privileges can be controlled consistently across the environment.

The **Restricted Groups** policy was used to enforce membership within the local Administrators group on domain systems. This prevents unauthorized users from gaining administrative access by manually modifying local group membership.

Using security groups and Group Policy ensures that permissions and administrative rights remain centralized, consistent, and scalable as the environment grows.

## Troubleshooting DNS and DHCP Issues

During deployment, several potential issues were considered and verified to ensure reliable operation of the network services.

If a client system fails to join the domain, the first step is verifying DNS configuration. Domain clients must use the domain controller as their preferred DNS server. If the DNS server is incorrect, the client will be unable to locate the domain controller.

DNS functionality can be verified using the **nslookup** command to confirm that hostnames resolve correctly within the CorpNet.local domain.

If a client system fails to obtain an IP address automatically, the DHCP service should be checked to ensure it is running and authorized in Active Directory. The DHCP scope must also be active and have available addresses within the configured range.

Using these verification steps allows administrators to quickly isolate configuration issues related to domain services.

## VirtualBox Networking Issue Resolution

During deployment, an issue occurred where the server could not access external network resources. This problem was resolved by configuring a **second network adapter** in VirtualBox using **NAT Network mode**.

The first adapter remained connected to the internal lab network to support communication between domain systems, while the NAT adapter provided internet access for updates and external connectivity.

This configuration allowed the environment to maintain an isolated internal network while still enabling external communication when required.

## Summary

Security within the CorpNet.local environment is enforced through centralized policies, group-based privilege management, and restricted administrative access. Troubleshooting procedures focus on verifying DNS resolution, DHCP configuration, and network connectivity to quickly identify and resolve infrastructure issues.