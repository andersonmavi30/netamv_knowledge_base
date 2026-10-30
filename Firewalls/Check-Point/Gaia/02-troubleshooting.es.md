---
tags: [cli, check-point, gaia, troubleshooting]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert. Confirma versión R8x y rol antes de ejecutar.

## `fw ctl conntab | grep 192.0.2.10`

```text
fw ctl conntab | grep 192.0.2.10
```

- **Sirve para:** Busca conexiones del cliente.
- **Parámetros:** conntab: tabla simplificada; grep: IP.
- **Ejemplo de uso:** Investigar sesiones ausentes.

## `fw tab -t connections -s`

```text
fw tab -t connections -s
```

- **Sirve para:** Consulta tamaño y entradas de conexiones.
- **Parámetros:** -t: tabla kernel; -s: estadísticas.
- **Ejemplo de uso:** Investigar saturación de tabla.

## `fw ctl pstat | grep -i memory`

```text
fw ctl pstat | grep -i memory
```

- **Sirve para:** Filtra estadísticas de memoria.
- **Parámetros:** pstat: estadísticas kernel; grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Investigar alarmas de recursos.

## `cphaprob stat`

```text
cphaprob stat
```

- **Sirve para:** Consulta ClusterXL cuando exista.
- **Parámetros:** stat: estado del miembro.
- **Ejemplo de uso:** Verificar activo/standby en failover.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/Content/Topics-CLIG/FWG/fw-tab.htm)
