---
tags: [windows-server, powershell, networking, cli, servers]
validation: not-lab-verified
---

# Diagnóstico DNS

[🇬🇧 English](03-dns.md) · [🇨🇴 Español](03-dns.es.md) · [↩ Windows Server](README.es.md)

**Plataforma:** Windows Server 2019 / 2022 / 2025; Windows PowerShell 5.1.

## `Get-DnsClientServerAddress`

```powershell
Get-DnsClientServerAddress
```

- **Sirve para:** Listar servidores DNS configurados en cada interfaz de red.
- **Parámetros:** Sin parámetros; muestra direcciones de DNS configuradas sin cambiarlas.
- **Ejemplo de uso:** Verificar los resolvedores DNS configurados en una NIC de Windows Server.
- **Referencia oficial:** https://learn.microsoft.com/en-us/powershell/module/dnsclient/get-dnsclientserveraddress?view=windowsserver2022-ps

> Pendiente de validación en laboratorio.
