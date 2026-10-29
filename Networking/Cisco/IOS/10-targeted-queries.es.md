---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Cisco IOS

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Descripciones de uplinks

Consulta el comando y su filtro en la [guía de interfaces](03-interfaces.es.md).

## LSAs Router de OSPF

```text
show ip ospf database router | include Link State ID
```

- **Sirve para:** LSAs Router de OSPF.
- **Opciones y filtros:** database router: LSAs Router
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Contadores de NAT

```text
show ip nat statistics | include Hits|Misses
```

- **Sirve para:** Contadores de NAT.
- **Opciones y filtros:** statistics: totales y hits
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Recursos de memoria

```text
show memory statistics | include Processor
```

- **Sirve para:** Recursos de memoria.
- **Opciones y filtros:** statistics: uso de memoria
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Contadores físicos Ethernet

```text
show controllers ethernet-controller GigabitEthernet0/0 | include error
```

- **Sirve para:** Contadores físicos Ethernet.
- **Opciones y filtros:** controller: contadores hardware; depende del modelo
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

