# Design Rationale

The network infrastructure for CorpNet.local is designed to provide a secure and manageable environment for a small organization using Windows Server 2022. The primary server, DC01, hosts Active Directory Domain Services (AD DS), DNS, and DHCP. Centralizing these core services ensures efficient authentication, name resolution, and IP address management while minimizing infrastructure complexity in a small-scale deployment.

The domain uses a single-forest, single-domain model to simplify administration and reduce overhead. Organizational Units (IT, HR, SALES, MARKETING) are structured to allow logical separation of departments and targeted application of Group Policy. This design supports scalability while maintaining administrative clarity.

Role-Based Access Control (RBAC) is implemented using departmental security groups (IT_Users, HR_Users, SALES_Users, MARKETING_Users) and administrative groups (IT_Admins, Local_Admins). Permissions are assigned to groups rather than individual user accounts to enforce the principle of least privilege. Administrative access is centralized through the Local_Admins group, which includes CorpNet\Administrator, CorpNet\IT_Admin, and CorpNet\SCCMAdmin. This ensures consistent control of elevated privileges across domain-joined systems.

The environment includes one domain-joined client system, Client01-IT, to demonstrate authentication, DHCP lease assignment, DNS registration, and Group Policy enforcement. This client validates end-to-end functionality of AD DS, DNS, and DHCP services.

The IP addressing scheme is structured within the 192.168.0.0/24 subnet. DC01 is statically assigned 192.168.0.1, the default gateway is 192.168.0.254, and DHCP distributes addresses within the range 192.168.0.50–192.168.0.200. This configuration separates infrastructure devices from dynamically assigned client systems.

Security policies enforce a 12-character minimum password length, complexity requirements, and a three-attempt account lockout threshold. These settings provide a strong authentication baseline while maintaining usability.

Overall, the infrastructure demonstrates best practices for small-scale Windows Server deployment, including centralized identity management, secure name resolution, automated IP distribution, and structured access control. The design is scalable, secure, and aligned with enterprise configuration standards.