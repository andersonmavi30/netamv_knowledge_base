---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# TCP connections and connectivity

[🇬🇧 English](04-connections.md) · [🇨🇴 Español](04-connections.es.md) · [↩ Windows Server](README.md)

**Platform:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-NetTCPConnection -State Listen`

```powershell
Get-NetTCPConnection -State Listen
```

- **Purpose:** Display TCP endpoints currently in the Listen state.
- **Arguments:** `-State Listen`: filter to TCP listening endpoints; results include local addresses and ports.
- **Use case:** Identify TCP ports exposed by running services.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/nettcpip/get-nettcpconnection?view=windowsserver2022-ps

> Not lab-verified.
