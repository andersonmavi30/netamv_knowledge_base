---
tags: [cli, netdevops, operational-checks]
validation: not-lab-verified
---

# 🧭 Verificaciones operativas — ampliación · Fortinet FortiOS

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** FortiOS 7.x. Los comandos no se han ejecutado en equipos; confirma la sintaxis con `?` y la documentación de tu versión.

## Estado SLA SD-WAN

```text
diagnose sys sdwan health-check | grep -i state
```

- **Sirve para:** Revisa latencia, pérdida y jitter de cada chequeo SD-WAN.
- **Parámetros / flags:** health-check: sondas SD-WAN; nombre opcional según versión.
- **Caso real:** Investigar si un ISP incumple el SLA.
- **Filtro / comprobación:** `diagnose sys sdwan health-check | grep -i state`

## Rutas por políticas en forwarding

```text
diagnose firewall proute list | grep 198.51.100
```

- **Sirve para:** Muestra rutas por política y decisiones SD-WAN en el plano de datos.
- **Parámetros / flags:** proute: routing por políticas; list: entradas y contadores.
- **Caso real:** Verificar interfaz de salida seleccionada para un destino.
- **Filtro / comprobación:** `diagnose firewall proute list | grep 198.51.100`

## Procesos y consumo de CPU

```text
diagnose sys top 1 10
```

- **Sirve para:** Observa los procesos de mayor consumo durante una prueba corta.
- **Parámetros / flags:** 1: refresco en segundos; 10: cantidad de procesos; q: salir.
- **Caso real:** Diagnosticar picos de CPU sin capturar tráfico.
- **Filtro / comprobación:** `Interactive: press q to quit (no pipe).`

## Estado de vecinos OSPF

```text
get router info ospf neighbor | grep 192.0.2
```

- **Sirve para:** Lista vecinos OSPF y estado de adyacencia.
- **Parámetros / flags:** ospf neighbor: vista de vecinos; requiere OSPF configurado.
- **Caso real:** Detectar vecino que no alcanza Full.
- **Filtro / comprobación:** `get router info ospf neighbor | grep 192.0.2`

## Estado de link-monitor

```text
diagnose sys link-monitor status | grep -i status
```

- **Sirve para:** Consulta estado de sondas link-monitor y failover.
- **Parámetros / flags:** status: estado de monitores configurados.
- **Caso real:** Identificar sonda WAN fallida antes de tocar rutas.
- **Filtro / comprobación:** `diagnose sys link-monitor status | grep -i status`

> ⚠️ Comandos de diagnóstico sobre funciones opcionales no devuelven información cuando esas funciones no están configuradas. Detén los monitores interactivos al terminar.

**Referencia**: [Fortinet FortiOS](https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/818746/sd-wan-related-diagnose-commands)
