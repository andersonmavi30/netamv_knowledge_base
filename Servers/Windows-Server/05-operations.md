---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Services and event logs

[🇬🇧 English](05-operations.md) · [🇨🇴 Español](05-operations.es.md) · [↩ Windows Server](README.md)

**Platform:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-Service -Name WinRM`

```powershell
Get-Service -Name WinRM
```

- **Purpose:** Display the Windows Remote Management service status and display name.
- **Arguments:** `-Name WinRM`: select the WinRM service; read-only.
- **Use case:** Check whether the WinRM service is running before troubleshooting PowerShell remoting.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1

> Not lab-verified.

## `Get-WinEvent -LogName System -MaxEvents 20`

```powershell
Get-WinEvent -LogName System -MaxEvents 20
```

- **Purpose:** Retrieve the 20 most recent entries from the Windows System event log.
- **Arguments:** `-LogName System`: System log; `-MaxEvents 20`: return at most 20 recent events; no changes.
- **Use case:** Review recent service, driver or network-related system events.
- **Official reference:** https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-5.1

> Not lab-verified.
