---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Dell OS6

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Descripción de puertos

Consulta el comando en la [guía de interfaces](03-interfaces.es.md).

## Estado de puertos LACP

```text
show lacp interfaces
```

- **Sirve para:** Estado de puertos LACP.
- **Opciones y filtros:** interfaces: miembros LACP
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Consumo PoE

```text
show power inline
```

- **Sirve para:** Consumo PoE.
- **Opciones y filtros:** inline: potencia de puertos
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Salud del sistema

```text
show system
```

- **Sirve para:** Salud del sistema.
- **Opciones y filtros:** system: resumen hardware
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Estado SVI de gestión

```text
show ip interface brief | include vlan
```

- **Sirve para:** Estado SVI de gestión.
- **Opciones y filtros:** brief: resumen IPv4; L3
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

