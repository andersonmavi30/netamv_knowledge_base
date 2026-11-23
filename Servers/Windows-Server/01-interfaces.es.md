---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Interfaces y direcciones de red

[🇬🇧 English](01-interfaces.md) · [🇨🇴 Español](01-interfaces.es.md) · [↩ Windows Server](README.es.md)

**Plataforma:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-NetAdapter`

```powershell
Get-NetAdapter
```

- **Sirve para:** Mostrar adaptadores de red y sus estados, velocidades y nombres.
- **Parámetros:** Sin parámetros; consulta adaptadores visibles. No realiza cambios.
- **Ejemplo de uso:** Comprobar si la interfaz Ethernet está activa tras iniciar el servidor.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/netadapter/get-netadapter?view=windowsserver2022-ps

> Pendiente de validación en laboratorio.
