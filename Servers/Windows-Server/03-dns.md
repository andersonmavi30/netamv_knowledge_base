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
