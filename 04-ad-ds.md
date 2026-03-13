# Section 1 – Active Directory Domain Services (AD DS)

This section documents the installation and configuration of Active Directory Domain Services on the Windows Server 2022 system designated as DC01. The server was promoted to a domain controller for the CorpNet.local domain and configured to manage centralized authentication, directory services, and organizational structure for the lab environment.

## Server Preparation – DC01

Before installing Active Directory Domain Services, DC01 was configured with a static IPv4 address to ensure that the server maintained a consistent network identity. Domain controllers should not rely on dynamically assigned IP addresses.

The following IPv4 settings were configured on the internal network adapter:

IP address: **192.168.0.1**  
Subnet mask: **255.255.255.0**  
Default gateway: **192.168.0.254**  
Preferred DNS server: **192.168.0.1**

To configure these settings, open **Network and Sharing Center**, select **Change adapter settings**, open the properties of the internal network adapter, select **Internet Protocol Version 4 (TCP/IPv4)**, and manually assign the address information.

![SCREENSHOT – Static IPv4 Configuration on DC01](/Lab%20Screenshots/Static%20IPv4%20Configuration%20on%20DC01.png)

## Installing the AD DS Role

Open Server Manager.

Select **Add Roles and Features**.

Proceed through the wizard until reaching the **Server Roles** page.

Select:

Active Directory Domain Services

Continue through the wizard and install the role.

![SCREENSHOT – AD DS Role Selected in Add Roles and Features Wizard](/Lab%20Screenshots/AD%20DS%20role%20install%20confirmation.png)

## Promoting the Server to a Domain Controller

After installation completes, a notification flag appears in Server Manager.

Select **Promote this server to a domain controller**.

Choose:

Add a new forest

Root domain name:

CorpNet.local

Set the **Directory Services Restore Mode (DSRM) password**.

Continue through the wizard using default configuration settings.

Select **Install**.

The system automatically reboots after promotion completes.

## Verifying Domain Controller Installation

After reboot, log in using the domain administrator account.

Open **Active Directory Users and Computers** to verify the domain structure.

Confirm the CorpNet.local domain appears and the server is listed as a domain controller.

![SCREENSHOT – Domain Controller Promotion Configuration](/Lab%20Screenshots/Domain%20Controller%20promotion%20confirmation.png)

## Creating Organizational Units

Organizational Units were created to logically separate departments within the domain.

The following OUs were created:

IT  
HR  
SALES  
MARKETING

This structure allows Group Policy and administrative permissions to be applied at the department level.

![SCREENSHOT – Active Directory Users and Computers Console](/Lab%20Screenshots/AD%20OU%20Structure.png)

## Creating Security Groups

Security groups were created to manage user permissions through Role-Based Access Control.

The following groups were created:

IT_Users  
HR_Users  
SALES_Users  
MARKETING_Users

Administrative access is managed through:

IT_Admins  
Local_Admins

Permissions are assigned to groups rather than individual user accounts to maintain scalability and enforce the principle of least privilege.

![SCREENSHOT – Security Groups Created](/Lab%20Screenshots/Security%20Group%20Creation.png)

## Default Domain Policy Configuration

The Default Domain Policy was modified to enforce baseline security requirements for user authentication across the domain.

Navigate to:

Group Policy Management → Default Domain Policy → Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies

### Password Policy

The following password security settings were configured:

Minimum password length: **12 characters**  
Password complexity: **Enabled**  
Maximum password age: **90 days**  
Minimum password age: **1 day**  
Enforce password history: **24 passwords**

These settings help protect against weak passwords and reduce the risk of credential compromise.

![SCREENSHOT – Default Domain Policy Password Settings](/Lab%20Screenshots/Default%20Domain%20Policy%20Password%20Settings.png)

### Account Lockout Policy

To protect against brute-force login attempts, the following account lockout settings were configured:

Account lockout threshold: **3 invalid logon attempts**  
Account lockout duration: **15 minutes**  
Reset account lockout counter after: **15 minutes**

These controls temporarily disable accounts after repeated failed login attempts, preventing automated password attacks.

![SCREENSHOT – Default Domain Policy Account Lockout Settings](/Lab%20Screenshots/Default%20Domain%20Policy%20Account%20Lockout%20Settings.png)

## Restricted Groups Configuration

Group Policy was used to enforce membership within the Local Administrators group.

Navigate to:

Group Policy Management → Default Domain Policy → Computer Configuration → Policies → Windows Settings → Security Settings → Restricted Groups

Configure the **Administrators** group with the following members:

CorpNet\Administrator  
CorpNet\IT_Admin  
CorpNet\SCCMAdmin

This ensures administrative privileges remain controlled and consistent across domain systems.

![SCREENSHOT – Restricted Groups Policy Configuration](/Lab%20Screenshots/GPO%20enforcing%20Local%20Admin%20group.png)

## Summary

Active Directory Domain Services is now deployed and configured for the CorpNet.local domain. The domain controller provides centralized authentication and directory management, while Organizational Units and security groups establish a scalable administrative structure for the environment.