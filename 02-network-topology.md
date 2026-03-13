# Network Topology

This section describes the network structure used for the CorpNet.local lab environment.

The environment consists of a Windows Server 2022 domain controller (DC01) and a domain-joined client machine (Client01-IT). The server hosts Active Directory Domain Services, DNS, and DHCP.

The network operates within the 192.168.0.0/24 subnet. DC01 is statically assigned 192.168.0.1 and serves as the central infrastructure server for the domain environment.

DHCP distributes addresses to domain clients while DNS provides internal name resolution for the CorpNet.local domain.

[SCREENSHOT – Network Topology Diagram]