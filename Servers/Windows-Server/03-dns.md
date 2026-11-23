---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# DNS diagnostics

[🇬🇧 English](03-dns.md) · [🇨🇴 Español](03-dns.es.md) · [↩ Windows Server](README.md)

**Platform:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-DnsClientServerAddress`

```powershell
Get-DnsClientServerAddress
```

- **Purpose:** List DNS server addresses configured on each network interface.
- **Arguments:** No flags; reports configured DNS server addresses without modifying them.
- **Use case:** Verify DNS resolvers configured on a Windows Server NIC.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/dnsclient/get-dnsclientserveraddress?view=windowsserver2022-ps

> Not lab-verified.

## `Resolve-DnsName -Name example.com -Type A`

```powershell
Resolve-DnsName -Name example.com -Type A
```

- **Purpose:** Query IPv4 A records for a hostname using the system's configured resolver behavior.
- **Arguments:** `-Name example.com`: example DNS name; `-Type A`: request IPv4 address records.
- **Use case:** Check whether the server can resolve a service hostname to IPv4.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/dnsclient/resolve-dnsname?view=windowsserver2022-ps

> Not lab-verified.
