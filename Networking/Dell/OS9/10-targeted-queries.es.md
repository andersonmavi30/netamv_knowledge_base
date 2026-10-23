---
tags: [cli, dell, field-queries]
validation: not-lab-verified
---

# Cinco consultas operativas adicionales — Dell OS9

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Verifica opciones en tu modelo y versión exactos; ejemplos pendientes de prueba.

## Rutas aprendidas por BGP

```text
show ip route bgp | grep 198.51.100
```

- **Sirve para:** Rutas aprendidas por BGP.
- **Flags:** bgp: rutas aprendidas por BGP.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Contadores de un puerto físico

```text
show interfaces tengigabitethernet 0/2 | grep error
```

- **Sirve para:** Contadores de un puerto físico.
- **Flags:** 0/2: puerto; depende del modelo.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Configuración de interfaz concreta

```text
show running-config interface tengigabitethernet 0/2
```

- **Sirve para:** Configuración de interfaz concreta.
- **Flags:** interface: puerto específico.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Sincronización de reloj

```text
show ntp status
```

- **Sirve para:** Sincronización de reloj.
- **Flags:** status: estado NTP; depende del equipo.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Búsqueda puntual de uptime

```text
show version | grep uptime
```

- **Sirve para:** Búsqueda puntual de uptime.
- **Flags:** grep: coincidencia.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

