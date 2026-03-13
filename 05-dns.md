# Section 2 – DNS Configuration

This section documents the configuration and validation of the Domain Name System (DNS) service for the **CorpNet.local** domain. DNS is a critical component of Active Directory because domain clients rely on it to locate domain controllers, authenticate to the network, and access shared resources.

Proper DNS configuration ensures that systems within the environment can resolve hostnames to IP addresses and locate domain services required for authentication and network communication.

---

## Verifying DNS Role Installation

The DNS Server role was installed automatically when **DC01** was promoted to a domain controller.

To verify that the DNS service is installed and operational:

Open **Server Manager**.

Navigate to:

Tools → DNS

Confirm that the **DNS Manager** console opens and that **DC01** appears within the management tree.

This confirms that the DNS service is installed and actively managing the domain’s DNS infrastructure.
---

## Forward Lookup Zone Configuration

During domain controller promotion, a DNS forward lookup zone was automatically created for the domain.

Verify that the following zone exists:

CorpNet.local

This forward lookup zone allows client systems within the network to resolve hostnames to IP addresses for resources located inside the domain.

To confirm the zone configuration:

Navigate to:

Forward Lookup Zones → CorpNet.local

Ensure the following DNS records are present:

- **SOA (Start of Authority)**
- **NS (Name Server)**
- **Host (A) record for DC01**

These records form the foundation of name resolution for the domain environment.

![SCREENSHOT – Forward Lookup Zone Showing CorpNet.local](/Lab%20Screenshots/DNS%20Forward%20Lookup%20Zones%20showing%20CorpNet.local.png)

---

## DNS Record Verification

Next, verify that the domain controller successfully registered its host record within the DNS zone.

Locate the **DC01** host record inside the **CorpNet.local** zone and confirm that the associated IP address is:

192.168.0.1

This record allows client systems to resolve the hostname **DC01** to the correct server address.

Proper registration of the domain controller’s host record is essential for domain services such as authentication, directory access, and service discovery.
---

## Reverse Lookup Zone Configuration

A reverse lookup zone allows DNS servers to resolve IP addresses back to hostnames. This capability is useful for network diagnostics, logging, and troubleshooting activities.

To create the reverse lookup zone:

Open **DNS Manager**.

Navigate to:

Reverse Lookup Zones

Right-click **Reverse Lookup Zones** and select:

New Zone

Configure the following settings:

Zone Type: Primary Zone  
Replication Scope: Store the zone in Active Directory  
Network ID: 192.168.0

This configuration establishes a reverse lookup zone for the **192.168.0.0/24** subnet used within the CorpNet.local network.
---

## PTR Record Configuration

After the reverse lookup zone is created, a **Pointer (PTR)** record should be configured for the domain controller.

Navigate to:

Reverse Lookup Zones → 0.168.192.in-addr.arpa

Right-click inside the zone and select:

New Pointer (PTR)

Configure the record as follows:

Host IP Number: 1  
Host Name: DC01.CorpNet.local

This PTR record maps the IP address **192.168.0.1** back to the hostname **DC01.CorpNet.local**, enabling reverse DNS resolution.

Reverse lookups are particularly useful for validating connections, analyzing logs, and confirming host identities during troubleshooting.

![SCREENSHOT – PTR Record for DC01](/Lab%20Screenshots/Reverse%20Lookup%20Zone%20PTR%20Record.png)

---

## DNS Forwarders Configuration

DNS forwarders allow the internal DNS server to resolve external domain names by forwarding queries to a public DNS server.

To configure DNS forwarders:

Open **DNS Manager**.

Right-click **DC01** and select:

Properties

Navigate to the **Forwarders** tab.

Add the following public DNS server:

8.8.8.8

With this configuration in place, the DNS server forwards unresolved queries to an external DNS provider rather than attempting full recursive resolution through root hints.

This improves efficiency when resolving internet-based domain names.

![SCREENSHOT – DNS Forwarders Configuration](/Lab%20Screenshots/DNS%20Forwarders%20Configuration.png)

---

## DNS Client Configuration

Domain clients must use the domain controller as their preferred DNS server to properly locate domain resources.

Client systems should be configured with the following DNS setting:

Preferred DNS Server: 192.168.0.1

This ensures that all domain-related queries are sent to the internal DNS server, which maintains authoritative records for the CorpNet.local environment.

Clients typically receive this configuration automatically through DHCP scope options.
---

## Recursive Query Behavior

DNS recursion allows the DNS server to query other DNS servers on behalf of a client when resolving external domain names.

To verify that recursion is enabled:

Open **DNS Manager**.

Right-click **DC01** and select:

Properties → Advanced

Confirm that the **Enable recursion** option is selected.

Recursion must remain enabled to allow internal clients to resolve internet domains when DNS forwarders are configured.
---

## DNS Name Resolution Test

DNS functionality was validated using the **nslookup** command.

Open Command Prompt on a client system and run: 

nslookup DC01

The command should return the IP address:

192.168.0.1

Successful resolution confirms that the DNS server is functioning correctly and that domain hostnames are resolving properly within the network.

![SCREENSHOT – Successful nslookup Test](/Lab%20Screenshots/nslookup%20validation%20results.png)

---

## Summary

The DNS service for the **CorpNet.local** domain has been successfully configured and validated. The environment includes a forward lookup zone for internal hostname resolution, a reverse lookup zone with PTR records for reverse mapping, and DNS forwarders to support external domain queries.

With these components in place, domain clients can reliably locate the domain controller and resolve both internal and external hostnames, ensuring stable communication across the network infrastructure.