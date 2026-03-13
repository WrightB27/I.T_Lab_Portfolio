# Section 3 – DHCP Configuration

This section documents the deployment and configuration of the Dynamic Host Configuration Protocol (DHCP) service on DC01. DHCP provides automated IP address assignment and network configuration to client devices within the CorpNet.local environment. By centralizing address distribution, DHCP reduces manual network configuration and ensures that client systems receive consistent network parameters.

## DHCP Role Overview

Server: DC01  
Server IP Address (Static): 192.168.0.1  
Subnet: 192.168.0.0 /24  
Gateway: 192.168.0.254  
DHCP Scope Range: 192.168.0.50 – 192.168.0.200  

In this infrastructure, DHCP is hosted directly on the domain controller to simplify management in the lab environment. The service distributes addresses to domain clients while infrastructure devices remain statically assigned.

## Installing the DHCP Server Role

Open **Server Manager**.

Select **Add Roles and Features**.

Proceed through the wizard until reaching the **Server Roles** page.

Select:

DHCP Server

Continue through the wizard and install the role.

After installation completes, the DHCP role is added to the server but requires additional configuration before it becomes operational.

## DHCP Post-Installation Configuration

After the DHCP role installation finishes, the server must complete the post-installation configuration process.

Open **Server Manager**.

Select the notification flag and choose **Complete DHCP Configuration**.

Authorize the DHCP server using domain administrator credentials.

This process registers the DHCP server within Active Directory so that it is permitted to issue IP address leases on the network. Unauthorized DHCP servers are blocked in domain environments to prevent rogue address assignment.

## Creating a DHCP Scope

Open **DHCP Manager**.

Navigate to:

IPv4 → DC01

Right-click **IPv4** and select **New Scope**.

Configure the following settings:

Scope Name: CorpNet Scope  
IP Address Range: 192.168.0.50 – 192.168.0.200  
Subnet Mask: 255.255.255.0  

This range distributes addresses to domain client systems while reserving lower addresses in the subnet for infrastructure devices such as servers, routers, or network appliances.

The default lease duration of **8 days** was retained because client systems in this lab environment remain relatively stable on the network.

![SCREENSHOT – DHCP Scope Configuration](/Windows%20Server%20Infrastructure%20Lab/Lab%20Screenshots/DHCP%20scope%20IP%20range%20configuration.png)

## Configuring Scope Options

Scope options define the network configuration settings automatically delivered to DHCP clients.

Configure the following options:

003 Router (Default Gateway):  
192.168.0.254  

006 DNS Server:  
192.168.0.1  

015 DNS Domain Name:  
CorpNet.local  

These options ensure that client systems receive the correct gateway and DNS configuration when obtaining an IP address. Clients will automatically communicate through the correct router and use the internal DNS server for name resolution.

## DHCP Reservation

DHCP reservations allow specific devices to always receive the same IP address while still using DHCP for management.

Navigate to:

IPv4 → Reservations → New Reservation

Create a reservation using the device MAC address and assign a specific IP address within the DHCP scope range.

Reservations are commonly used for devices such as printers, management systems, or infrastructure appliances that require predictable network addressing but should still be centrally managed through DHCP.

## DHCP Server Authorization Verification

To verify that the DHCP server is properly authorized within Active Directory, the following command can be executed in PowerShell:

netsh dhcp show server


The output should display DC01 as an authorized DHCP server. This confirmation ensures that the server is permitted to issue IP address leases within the domain environment.

![SCREENSHOT – DHCP Authorization Confirmation](/Windows%20Server%20Infrastructure%20Lab/Lab%20Screenshots/DHCP%20Server%20authorization.png)

## DHCP Lease Verification

To confirm that DHCP is functioning correctly, a client system was configured to obtain an IP address automatically.

On the client system, run:

ipconfig /release
ipconfig /renew
ipconfig /all

The client successfully received an IP address within the configured scope range along with the correct DNS server and default gateway settings.

Expected configuration:

IP Address: 192.168.0.50 – 192.168.0.200  
Gateway: 192.168.0.254  
DNS Server: 192.168.0.1  
DNS Suffix: CorpNet.local  

Successful lease assignment confirms that DHCP is properly distributing network configuration to domain client systems.

![SCREENSHOT – Client Receiving DHCP Lease](/Windows%20Server%20Infrastructure%20Lab/Lab%20Screenshots/IT%20Client%20ipconfig%20showing%20correct%20parameters.png)

## Summary

The DHCP server on DC01 is now fully configured and operational. The service automatically distributes IP addresses and essential network configuration to client systems within the CorpNet.local environment. Centralized DHCP management reduces administrative overhead while ensuring consistent network configuration across all domain-connected devices.