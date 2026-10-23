---
tags: [cli, dell, field-queries]
validation: not-lab-verified
---

# Cinco consultas operativas adicionales — Dell OS10

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Verifica opciones en tu modelo y versión exactos; ejemplos pendientes de prueba.

## Estado de servidores NTP

```text
show ntp associations
```

- **Sirve para:** Estado de servidores NTP.
- **Flags:** associations: vecinos NTP.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Estado de un puerto

```text
show interface ethernet 1/1/5 | grep error
```

- **Sirve para:** Estado de un puerto.
- **Flags:** ethernet 1/1/5: identificador.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Rutas VRF de gestión

```text
show ip route vrf management | grep 198.51.100
```

- **Sirve para:** Rutas VRF de gestión.
- **Flags:** vrf management: instancia de routing.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Topología spanning-tree

```text
show spanning-tree | grep Root
```

- **Sirve para:** Topología spanning-tree.
- **Flags:** Sin opciones; requiere STP.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

## Consulta vecinos ARP

```text
show arp | grep 192.0.2
```

- **Sirve para:** Consulta vecinos ARP.
- **Flags:** Caché ARP: vecinos L3.
- **Caso práctico:** Localizar un dato preciso del estado de la red durante una investigación.

