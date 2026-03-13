# Section 2 – DNS Configuration

This section documents the configuration and verification of the Domain Name System (DNS) service for the CorpNet.local domain. DNS is required for Active Directory to function properly because domain clients rely on DNS to locate domain controllers and other network services.

## Verifying DNS Role Installation

The DNS Server role was installed automatically during the promotion of DC01 to a domain controller.

Open **Server Manager**.

Navigate to:

Tools → DNS

Verify that the DNS Manager console opens and the server **DC01** appears in the management tree.

[SCREENSHOT – DNS Manager Console Showing DC01]

## Forward Lookup Zone Configuration

During the domain controller promotion process, a DNS forward lookup zone was automatically created for the domain.

Confirm the zone:

CorpNet.local

This zone allows domain clients to resolve hostnames within the internal network.

Navigate to:

Forward Lookup Zones → CorpNet.local

Verify that the following records exist:

- SOA (Start of Authority)
- NS (Name Server)
- Host (A) record for DC01

[SCREENSHOT – Forward Lookup Zone Showing CorpNet.local]

## DNS Record Verification

Confirm that the domain controller registered its host record correctly.

Locate the **DC01** host record inside the CorpNet.local zone.

Verify that the IP address associated with the record is:

192.168.0.1

This ensures that domain clients can resolve the domain controller by hostname.

[SCREENSHOT – Host Record for DC01]

## DNS Client Configuration

Domain clients must use the domain controller as their preferred DNS server.

Client systems should receive the following DNS configuration:

Preferred DNS Server: 192.168.0.1

This setting ensures that client systems query the internal DNS server for domain-related name resolution.

[SCREENSHOT – Client DNS Configuration]

## DNS Name Resolution Test

DNS functionality was verified using the **nslookup** command.

Open Command Prompt on the client system and run:

nslookup DC01

The command should return the IP address:

192.168.0.1

This confirms that the DNS server is resolving hostnames correctly within the domain environment.

[SCREENSHOT – Successful nslookup Test]

## Summary

The DNS service is functioning correctly for the CorpNet.local domain. Forward lookup zones are configured, host records are properly registered, and domain clients can successfully resolve the domain controller using DNS queries.