# Section 3 – DHCP Configuration

This section documents the installation and configuration of the Dynamic Host Configuration Protocol (DHCP) service on DC01. DHCP automatically assigns IP addresses and network configuration settings to client systems within the CorpNet.local environment.

## Installing the DHCP Server Role

Open **Server Manager**.

Select **Add Roles and Features**.

Proceed through the wizard until reaching the **Server Roles** page.

Select:

DHCP Server

Continue through the wizard and install the role.

[SCREENSHOT – DHCP Role Selected in Add Roles and Features Wizard]

## Authorizing the DHCP Server

After installation completes, the DHCP server must be authorized in Active Directory before it can begin issuing IP addresses.

Open **Server Manager**.

Select the notification flag and choose **Complete DHCP Configuration**.

Authorize the DHCP server using domain administrator credentials.

[SCREENSHOT – DHCP Authorization Confirmation]

## Creating a DHCP Scope

Open **DHCP Manager**.

Navigate to:

IPv4 → DC01

Right-click **IPv4** and select **New Scope**.

Configure the following settings:

Scope Name: CorpNet Scope  
IP Address Range: 192.168.0.50 – 192.168.0.200  
Subnet Mask: 255.255.255.0

This range provides IP addresses for domain client systems while reserving lower addresses for infrastructure devices.

[SCREENSHOT – DHCP Scope Configuration]

## Configuring Scope Options

Configure the following scope options to ensure clients receive proper network settings.

003 Router (Default Gateway):  
192.168.0.254

006 DNS Server:  
192.168.0.1

015 DNS Domain Name:  
CorpNet.local

These settings ensure that clients automatically receive the correct gateway and DNS server information when obtaining an IP address.

[SCREENSHOT – DHCP Scope Options Configuration]

## DHCP Reservation

A DHCP reservation can be configured to ensure that specific devices always receive the same IP address.

Navigate to:

IPv4 → Reservations → New Reservation

Configure the reservation using the device MAC address and assign a static IP within the DHCP range.

[SCREENSHOT – DHCP Reservation Configuration]

## DHCP Lease Verification

To verify DHCP functionality, a client system was connected to the network and configured to obtain an IP address automatically.

The client successfully received an IP address within the configured scope range along with the correct DNS and gateway settings.

This confirms that DHCP is functioning correctly within the CorpNet.local environment.

[SCREENSHOT – Client Receiving DHCP Lease]

## Summary

The DHCP server is now fully configured and operational. Client systems can automatically obtain IP addresses, gateway information, and DNS configuration, reducing manual network administration while ensuring consistent network settings across the environment.