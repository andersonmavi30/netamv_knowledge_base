---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Conexiones TCP y conectividad

[🇬🇧 English](04-connections.md) · [🇨🇴 Español](04-connections.es.md) · [↩ Windows Server](README.es.md)

**Plataforma:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-NetTCPConnection -State Listen`

```powershell
Get-NetTCPConnection -State Listen
```

- **Sirve para:** Mostrar los extremos TCP que están en estado de escucha (Listen).
- **Parámetros:** `-State Listen`: filtrar puertos TCP en escucha; incluye direcciones y puertos locales.
- **Ejemplo de uso:** Identificar puertos TCP abiertos por servicios en ejecución.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/nettcpip/get-nettcpconnection?view=windowsserver2022-ps

> Pendiente de validación en laboratorio.
