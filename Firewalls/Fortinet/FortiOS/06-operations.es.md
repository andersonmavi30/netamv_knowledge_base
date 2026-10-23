---
tags: [cli, fortinet-fortios, operations]
validation: not-lab-verified
---

# 📋 Comandos adicionales de operación

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice](README.es.md)

**Familia de versiones:** 7.x. La disponibilidad depende de modelo, licencia y versión.

## `get firewall policy`

```text
get firewall policy | grep -i name
```

- **Sirve para:** Lista resumen de políticas (campos varían).
- **Parámetros:** Sin flags.
- **Caso real:** Identificar reglas activas.
- **Filtro/validación:** `get firewall policy | grep -i name`

## `diagnose sys session stat`

```text
diagnose sys session stat | grep -i session
```

- **Sirve para:** Consulta sesiones y recursos.
- **Parámetros:** stat: estadísticas de sesión.
- **Caso real:** Detectar consumo elevado de sesiones.
- **Filtro/validación:** `diagnose sys session stat | grep -i session`

## `get router info routing-table details 198.51.100.0`

```text
get router info routing-table details 198.51.100.0
```

- **Sirve para:** Consulta rutas del destino; valida sintaxis.
- **Parámetros:** details: muestra detalle.
- **Caso real:** Investigar ruta faltante.
- **Filtro/validación:** `get router info routing-table all | grep 198.51.100`

## `diagnose vpn ike gateway list`

```text
diagnose vpn ike gateway list | grep -i name=
```

- **Sirve para:** Consulta gateways IKE y su estado.
- **Parámetros:** list: lista de gateways.
- **Caso real:** Revisar estado fase 1.
- **Filtro/validación:** `diagnose vpn ike gateway list | grep -i name=`


## `execute backup full-config tftp lab-backup.conf 192.0.2.20`

```text
execute backup full-config tftp lab-backup.conf 192.0.2.20
```

- **Sirve para:** Exporta configuración completa a TFTP confiable.
- **Parámetros:** archivo e IP del servidor: destino.
- **Caso real:** Respaldo antes de cambios de laboratorio.
- **Filtro/validación:** `execute backup full-config ?`

## `diagnose debug reset`

```text
diagnose debug reset
```

- **Sirve para:** Reinicia filtros y estado de depuración.
- **Parámetros:** reset: limpia debug.
- **Caso real:** Preparar una sesión debug corta.
- **Filtro/validación:** `diagnose debug status`


> No probado en laboratorio; verificar con la ayuda CLI y documentación de la versión antes de ejecutarlo. Los respaldos completos y las salidas de diagnóstico pueden contener datos sensibles.
