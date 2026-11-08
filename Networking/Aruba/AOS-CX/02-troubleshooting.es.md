---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; comprueba versión y sintaxis con `show version` y `?`.

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad a un host.
- **Parámetros:** IP: IP destino.
- **Ejemplo de uso:** Revisar servidor de gestión.

## `traceroute 198.51.100.10`

```text
traceroute 198.51.100.10
```

- **Sirve para:** Consulta saltos a host remoto.
- **Parámetros:** IP: destino.
- **Ejemplo de uso:** Ubicar falla de enrutamiento.

## `show logging | include link`

```text
show logging | include link
```

- **Sirve para:** Busca eventos de enlace.
- **Parámetros:** include: filtro de texto.
- **Ejemplo de uso:** Investigar flapping.

## `show arp | include 192.0.2.10`

```text
show arp | include 192.0.2.10
```

- **Sirve para:** Busca vecino ARP.
- **Parámetros:** include: coincidencia IP.
- **Ejemplo de uso:** Confirmar MAC gateway.

> Ejemplos pendientes de validación en laboratorio; comandos y filtros pueden variar según versión y equipo.

## Diagnóstico de eventos y recursos

### `show events`

```text
show events
```

- **Sirve para:** Consultar notificaciones de eventos del sistema.
- **Parámetros:** events: historial de eventos; tiempos según reloj del sistema.
- **Ejemplo de uso:** Investigar incidencias sin cambiar configuración.

### `show system resource-utilization`

```text
show system resource-utilization
```

- **Sirve para:** Consultar utilización de CPU y memoria del switch.
- **Parámetros:** system resource-utilization: resumen de recursos de la plataforma.
- **Ejemplo de uso:** Investigar incidencias sin cambiar configuración.

> Pendiente de validación en laboratorio. AOS-CX 10.x; model/release support varies.

**Referencia:** https://arubanetworking.hpe.com/techdocs/AOS-CX/10.16/PDF/cli_6300-6400.pdf
