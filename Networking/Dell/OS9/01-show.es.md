---
tags: [cli, dell, os9, show]
validation: not-lab-verified
---

# Consultas y estado — Dell OS9

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verifica con `show version` y `?`.

## `show version`

```text
show version
```

- **Sirve para:** Identifica versión OS9 y hardware.
- **Parámetros:** Sin opciones.
- **Caso real:** Confirmar OS9.

## `show interfaces`

```text
show interfaces
```

- **Sirve para:** Consulta puertos y contadores.
- **Parámetros:** Sin opciones.
- **Caso real:** Encontrar enlaces caídos.

## `show ip route`

```text
show ip route
```

- **Sirve para:** Consulta rutas IPv4.
- **Parámetros:** Sin opciones.
- **Caso real:** Comprobar rutas.

## `show vlan`

```text
show vlan
```

- **Sirve para:** Consulta VLAN en equipos L2.
- **Parámetros:** Sin opciones; depende del equipo.
- **Caso real:** Buscar VLAN 10.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
