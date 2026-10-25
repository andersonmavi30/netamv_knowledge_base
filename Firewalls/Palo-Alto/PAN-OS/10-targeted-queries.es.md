---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Consultas operativas específicas

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** PAN-OS genérico; confirma la ayuda `?` en tu versión.

## `show session info`

```text
show session info
```

- **Sirve para:** Consulta ocupación de sesiones antes de investigar agotamiento.
- **Parámetros:** info: estadísticas globales; campos según versión.
- **Ejemplo de uso:** Comprobar si falta capacidad de sesiones.

## `show admins`

```text
show admins
```

- **Sirve para:** Identifica sesiones administrativas antes de cambios.
- **Parámetros:** admins: lista administradores; consulta específica.
- **Ejemplo de uso:** Evitar cambios simultáneos.

## `show jobs pending`

```text
show jobs pending
```

- **Sirve para:** Busca tareas pendientes sin revisar el histórico.
- **Parámetros:** pending: solo tareas pendientes.
- **Ejemplo de uso:** Comprobar si commit sigue en cola.

## `show system software status`

```text
show system software status
```

- **Sirve para:** Consulta procesos cuando fallan servicios.
- **Parámetros:** status: estado de procesos; valida soporte con ?.
- **Ejemplo de uso:** Identificar servicio reiniciando.

## `show system logdb-quota`

```text
show system logdb-quota
```

- **Sirve para:** Consulta cuotas de almacenamiento de logs.
- **Parámetros:** logdb-quota: asignación de espacio.
- **Ejemplo de uso:** Investigar ausencia de logs por cuota.

## `show running resource-monitor`

```text
show running resource-monitor
```

- **Sirve para:** Consulta consumo de recursos donde aplique.
- **Parámetros:** resource-monitor: mediciones de recursos.
- **Ejemplo de uso:** Correlacionar lentitud con consumo.

## `show session all filter rule LAB-ALLOW-HTTPS`

```text
show session all filter rule LAB-ALLOW-HTTPS
```

- **Sirve para:** Busca sesiones coincidentes con regla.
- **Parámetros:** filter rule: filtro de nombre de regla.
- **Ejemplo de uso:** Ver si nueva regla recibe tráfico.

## `show user group list`

```text
show user group list
```

- **Sirve para:** Lista grupos conocidos por el firewall.
- **Parámetros:** group list: grupos User-ID; requiere integración.
- **Ejemplo de uso:** Comprobar que un grupo de directorio esté aprendido.

## `show high-availability flap-statistics`

```text
show high-availability flap-statistics
```

- **Sirve para:** Consulta transiciones HA durante failover inestable.
- **Parámetros:** flap-statistics: transiciones HA; requiere HA.
- **Ejemplo de uso:** Investigar alternancia frecuente HA.

## `show dos-block-table`

```text
show dos-block-table
```

- **Sirve para:** Consulta IP bloqueadas después de tráfico anómalo.
- **Parámetros:** dos-block-table: fuentes bloqueadas; depende de versión.
- **Ejemplo de uso:** Determinar si protección bloqueó cliente legítimo.

> Nota: la selección por argumento es preferible al pipe cuando el CLI tiene filtros internos. Algunas salidas no admiten `| match`; confirma con `?` antes de usarlo. Ejemplos pendientes de validación en laboratorio.

[Official PAN-OS CLI reference](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy)
