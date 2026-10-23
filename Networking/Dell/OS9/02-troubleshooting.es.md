---
tags: [cli, dell, os9, troubleshooting]
validation: not-lab-verified
---

# Diagnóstico — Dell OS9

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verifica con `show version` y `?`.

## `show logging`

```text
show logging | grep DOWN
```

- **Sirve para:** Consulta logs OS9.
- **Parámetros:** Sin opciones.
- **Caso real:** Revisar flapping.

## `show arp`

```text
show arp | grep 192.0.2
```

- **Sirve para:** Revisa vecinos ARP en equipos compatibles.
- **Parámetros:** Sin opciones.
- **Caso real:** Verificar ARP de gateway.

## `show ip ospf neighbor`

```text
show ip ospf neighbor
```

- **Sirve para:** Consulta vecinos OSPF cuando esté activo.
- **Parámetros:** Sin opciones.
- **Caso real:** Localizar adyacencias incompletas.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
