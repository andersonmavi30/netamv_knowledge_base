---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Servicios y registros de eventos

[🇬🇧 English](05-operations.md) · [🇨🇴 Español](05-operations.es.md) · [↩ Windows Server](README.es.md)

**Plataforma:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-Service -Name WinRM`

```powershell
Get-Service -Name WinRM
```

- **Sirve para:** Mostrar el estado y nombre del servicio Windows Remote Management.
- **Parámetros:** `-Name WinRM`: seleccionar el servicio WinRM; solo consulta.
- **Ejemplo de uso:** Verificar si WinRM está iniciado antes de diagnosticar PowerShell Remoting.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1

> Pendiente de validación en laboratorio.

## `Get-WinEvent -LogName System -MaxEvents 20`

```powershell
Get-WinEvent -LogName System -MaxEvents 20
```

- **Sirve para:** Consultar los 20 eventos más recientes del registro System de Windows.
- **Parámetros:** `-LogName System`: registro System; `-MaxEvents 20`: devolver máximo 20 eventos recientes; sin cambios.
- **Ejemplo de uso:** Revisar eventos recientes de servicios, controladores o fallos del sistema.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-5.1

> Pendiente de validación en laboratorio.
