---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Network interfaces and addressing

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ Windows Server](README.md)

**Platform:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-NetAdapter`

```powershell
Get-NetAdapter
```

- **Purpose:** List network adapters with their names, status and link speeds.
- **Arguments:** No parameters; lists visible adapters without changing settings.
- **Use case:** Check whether an Ethernet adapter is up after server startup.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/netadapter/get-netadapter?view=windowsserver2022-ps

> Not lab-verified.
