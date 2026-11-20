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

## `execute update-now`

```text
execute update-now
```

- **Sirve para:** Solicitar una actualización inmediata de firmas FortiGuard.
- **Parámetros:** `update-now`: inicia actualización; requiere conectividad y puede modificar firmas.
- **Ejemplo de uso:** Actualizar firmas IPS/AV durante mantenimiento autorizado.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966

> Pendiente de validación en laboratorio. Usar solo durante diagnóstico autorizado.

## `diagnose log test`

```text
diagnose log test
```

- **Sirve para:** Generar logs de prueba para comprobar el sistema de registro FortiOS.
- **Parámetros:** `log test`: crea eventos de prueba; no es solo una prueba de conectividad.
- **Ejemplo de uso:** Comprobar si FortiAnalyzer recibe eventos de prueba.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966

> Pendiente de validación en laboratorio; no publiques configuraciones, logs ni secretos.

## `execute log fortianalyzer test-connectivity`

```text
execute log fortianalyzer test-connectivity
```

- **Sirve para:** Probar la conexión del FortiGate con los servidores FortiAnalyzer configurados.
- **Parámetros:** `log fortianalyzer test-connectivity`: prueba activa de comunicación; requiere FAZ configurado.
- **Ejemplo de uso:** Confirmar conectividad antes de investigar logs no enviados.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966

> Pendiente de validación en laboratorio; no publiques configuraciones, logs ni secretos.

## `execute factoryreset`

```text
execute factoryreset
```

- **Sirve para:** Restablecer el FortiGate a valores de fábrica y reiniciar, borrando la mayor parte de la configuración.
- **Parámetros:** `factoryreset`: reseteo destructivo y reinicio; exigir backup y acceso de recuperación.
- **Ejemplo de uso:** Usar solo en baja de equipo autorizada o laboratorio aislado.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.7/administration-guide/702257/configuration-backups-and-reset

> Pendiente de validación en laboratorio. Atención: ver impacto antes de ejecutarlo.
