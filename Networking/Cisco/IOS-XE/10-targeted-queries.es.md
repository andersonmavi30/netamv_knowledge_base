---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Cisco IOS-XE

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Estado de enlaces agregados

```text
show etherchannel summary | include Po
```

- **Sirve para:** Estado de enlaces agregados.
- **Opciones y filtros:** summary: miembros LAG; solo switching
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Ruta CEF por origen y destino

```text
show ip cef exact-route 192.0.2.10 198.51.100.10
```

- **Sirve para:** Ruta CEF por origen y destino.
- **Opciones y filtros:** exact-route: ruta escogida
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Temperatura y alimentación

```text
show environment all | include Temperature|Power
```

- **Sirve para:** Temperatura y alimentación.
- **Opciones y filtros:** all: sensores, depende del modelo
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## LSAs externas OSPF

```text
show ip ospf database external | include Link State ID
```

- **Sirve para:** LSAs externas OSPF.
- **Opciones y filtros:** external: LSAs tipo 5
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Bindings de DHCP snooping

```text
show ip dhcp snooping binding | include 192.0.2
```

- **Sirve para:** Bindings de DHCP snooping.
- **Opciones y filtros:** binding: concesiones aprendidas
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

