# Section 1 – Active Directory Domain Services (AD DS)

This section documents the installation and configuration of Active Directory Domain Services on the Windows Server 2022 system designated as DC01. The server was promoted to a domain controller for the CorpNet.local domain and configured to manage centralized authentication, directory services, and organizational structure for the lab environment.

## Installing the AD DS Role

Open Server Manager.

Select **Add Roles and Features**.

Proceed through the wizard until reaching the **Server Roles** page.

Select:

Active Directory Domain Services

Continue through the wizard and install the role.

[SCREENSHOT – AD DS Role Selected in Add Roles and Features Wizard]

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

[SCREENSHOT – Domain Controller Promotion Configuration]

## Verifying Domain Controller Installation

After reboot, log in using the domain administrator account.

Open **Active Directory Users and Computers** to verify the domain structure.

Confirm the CorpNet.local domain appears and the server is listed as a domain controller.

[SCREENSHOT – Active Directory Users and Computers Console]

## Creating Organizational Units

Organizational Units were created to logically separate departments within the domain.

The following OUs were created:

IT  
HR  
SALES  
MARKETING

This structure allows Group Policy and administrative permissions to be applied at the department level.

[SCREENSHOT – OU Structure in Active Directory]

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

[SCREENSHOT – Security Groups Created]

## Restricted Groups Configuration

Group Policy was used to enforce membership within the Local Administrators group.

Navigate to:

Group Policy Management → Default Domain Policy → Computer Configuration → Policies → Windows Settings → Security Settings → Restricted Groups

Configure the **Administrators** group with the following members:

CorpNet\Administrator  
CorpNet\IT_Admin  
CorpNet\SCCMAdmin

This ensures administrative privileges remain controlled and consistent across domain systems.

[SCREENSHOT – Restricted Groups Policy Configuration]

## Summary

Active Directory Domain Services is now deployed and configured for the CorpNet.local domain. The domain controller provides centralized authentication and directory management, while Organizational Units and security groups establish a scalable administrative structure for the environment.