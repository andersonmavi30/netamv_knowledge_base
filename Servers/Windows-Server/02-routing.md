---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Routing and route selection

[🇬🇧 English](02-routing.md) · [🇨🇴 Español](02-routing.es.md) · [↩ Windows Server](README.md)

**Platform:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-NetRoute -AddressFamily IPv4`

```powershell
Get-NetRoute -AddressFamily IPv4
```

- **Purpose:** List IPv4 route entries and their next hops, metrics and interfaces.
- **Arguments:** `-AddressFamily IPv4`: filter the route table to IPv4 entries; read-only.
- **Use case:** Inspect default routes or unexpected IPv4 paths.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/nettcpip/get-netroute?view=windowsserver2022-ps

> Not lab-verified.

## `Find-NetRoute -RemoteIPAddress 1.1.1.1`

```powershell
Find-NetRoute -RemoteIPAddress 1.1.1.1
```

- **Purpose:** Find the local route and source address selected to reach a remote IP.
- **Arguments:** `-RemoteIPAddress`: destination to evaluate; `1.1.1.1`: example address; does not add routes.
- **Use case:** Check selected egress path on a server with multiple NICs.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/nettcpip/find-netroute?view=windowsserver2022-ps

> Not lab-verified.
