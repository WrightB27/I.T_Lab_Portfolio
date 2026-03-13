# Virtualized Deployment Method (Oracle VirtualBox)

To implement the Windows Server infrastructure in a controlled lab environment, Oracle VirtualBox was used as the hypervisor platform. This virtual environment simulates an enterprise network while remaining isolated from the host system.

This section documents the deployment method for one server (DC01). The same methodology was used for additional systems in the environment.

## Acquiring Windows Server 2022 Installation Media

Navigate to Microsoft’s official Evaluation Center.  
Select Windows Server 2022 (180-day evaluation).  
Complete the registration form.  
Download the 64-bit ISO file.  
Store the ISO in a designated lab media directory for reuse.

![SCREENSHOT – Microsoft Evaluation Center Download Page](/Lab%20Screenshots/Microsoft%20Eval%20Center%20Download%20Page.png)  
https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022

The ISO file was later mounted directly into the VirtualBox virtual machine as a virtual optical disk.

## Creating the Virtual Machine (DC01)

Open Oracle VirtualBox.  
Select New.

Configure the following:

Name: DC01  
Type: Microsoft Windows  
Version: Windows Server 2022 (64-bit)

Allocate system resources:

Memory: 4 GB minimum (8 GB recommended)  
CPU: 2 virtual processors

Create a virtual hard disk:

VDI format  
Dynamically allocated  
80 GB storage

## Configuring Network Adapters

DC01 was configured with two network adapters to simulate a segmented enterprise network.

### Adapter 1 – Internal Network

Mode: Internal Network  
Network Name: intnetwork  
Subnet: 192.168.0.0/24  
Purpose: Private communication between lab systems (AD, DHCP, SCCM, clients)

This adapter represents the internal corporate LAN.

![SCREENSHOT – Internal Network Adapter Settings](/Lab%20Screenshots/Internal%20Network%20Adapter%20Settings.png)

### Adapter 2 – NAT Network

Mode: NAT Network  
Network Name: NATNETWORK  
Purpose: Provides outbound internet access while maintaining isolation

![SCREENSHOT – NAT Network Adapter Settings](/Lab%20Screenshots/NAT%20Network%20Adapter%20Settings.png)

## Installing Windows Server 2022

Open VM Settings → Storage.  
Attach the downloaded ISO to the optical drive.  
Start the virtual machine.

Select:

Windows Server 2022 Standard (Desktop Experience)

Complete the installation wizard.  
Set the local Administrator password.  
Log in after installation completes.

## Initial Server Configuration

After installation:

Rename the server to: DC01

Configure static IP settings on the Internal Network adapter:

IP Address: 192.168.0.1  
Subnet Mask: 255.255.255.0  
Default Gateway: 192.168.0.254  
Preferred DNS: 192.168.0.1

Disable automatic DNS configuration on the NAT adapter.

Verify connectivity:

Ping 192.168.0.1

![SCREENSHOT – Static IP Configuration](/Lab%20Screenshots/Static%20IP%20Configuration.png)

![SCREENSHOT – Successful Ping Test](/Lab%20Screenshots/Sucessful%20Ping%20Test.png)

## Deployment Justification

VirtualBox was selected because it provides:

Controlled network segmentation  
Snapshot capability for rollback  
Repeatable deployment procedures  
Safe testing without affecting production systems

VirtualBox provides a controlled environment for deploying the Windows Server infrastructure without relying on physical hardware. The platform allowed the server to be created, configured, and tested in a way that mirrors real-world implementation. Changes could be made safely, and snapshots ensured recovery during configuration errors. This method demonstrates practical deployment skills while maintaining a stable and isolated lab environment.