---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Enrutamiento y selección de rutas

[🇬🇧 English](02-routing.md) · [🇨🇴 Español](02-routing.es.md) · [↩ Windows Server](README.es.md)

**Plataforma:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-NetRoute -AddressFamily IPv4`

```powershell
Get-NetRoute -AddressFamily IPv4
```

- **Sirve para:** Listar rutas IPv4 con sus siguientes saltos, métricas e interfaces.
- **Parámetros:** `-AddressFamily IPv4`: filtrar rutas de la familia IPv4; consulta.
- **Ejemplo de uso:** Revisar rutas predeterminadas o caminos IPv4 inesperados.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/nettcpip/get-netroute?view=windowsserver2022-ps

> Pendiente de validación en laboratorio.
