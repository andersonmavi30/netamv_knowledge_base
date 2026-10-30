---
tags: [cli, check-point, gaia, operations]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Operación de firewall

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert. Confirma versión R8x y rol antes de ejecutar.

## `fwaccel stat`

```text
fwaccel stat
```

- **Sirve para:** Consulta aceleración SecureXL.
- **Parámetros:** stat: estado y estadísticas.
- **Ejemplo de uso:** Investigar bajo rendimiento.

## `fw ctl multik stat`

```text
fw ctl multik stat
```

- **Sirve para:** Consulta instancias CoreXL.
- **Parámetros:** multik stat: estadísticas.
- **Ejemplo de uso:** Ver distribución entre workers.

## `cpstat fw -f all | grep -i policy`

```text
cpstat fw -f all | grep -i policy
```

- **Sirve para:** Busca datos de políticas en estadísticas.
- **Parámetros:** -f all: salida ampliada; grep: etiqueta.
- **Ejemplo de uso:** Ver información de política instalada.

## `cphaprob -a if`

```text
cphaprob -a if
```

- **Sirve para:** Consulta interfaces de ClusterXL.
- **Parámetros:** -a if: monitoreo de interfaces.
- **Ejemplo de uso:** Diagnosticar enlaces de sincronización.
- **Precaución:** Solo ClusterXL.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/Content/Topics-CLIG/FWG/fw-ctl.htm)
