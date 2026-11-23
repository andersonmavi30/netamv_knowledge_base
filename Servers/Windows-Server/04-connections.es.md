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

## `Test-NetConnection -ComputerName example.com -Port 443`

```powershell
Test-NetConnection -ComputerName example.com -Port 443
```

- **Sirve para:** Probar conectividad TCP hacia un nombre remoto y un puerto, con detalles diagnósticos.
- **Parámetros:** `-ComputerName example.com`: destino; `-Port 443`: puerto TCP remoto; realiza pruebas sin cambiar configuración.
- **Ejemplo de uso:** Verificar conectividad HTTPS saliente desde un servidor de aplicaciones.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection?view=windowsserver2022-ps

> Pendiente de validación en laboratorio.
