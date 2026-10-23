---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Dell OS10

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Interfaces con enlace caído

```text
show interface status | grep down
```

- **Sirve para:** Interfaces con enlace caído.
- **Opciones y filtros:** grep: coincidencias
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Búsqueda de prefijos

```text
show ip route | grep 203.0.113
```

- **Sirve para:** Búsqueda de prefijos.
- **Opciones y filtros:** grep: filtro texto
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Configuración SNMP

```text
show running-configuration | grep snmp
```

- **Sirve para:** Configuración SNMP.
- **Opciones y filtros:** grep: coincidencias
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Errores de puerto

```text
show interface ethernet 1/1/5 | grep error
```

- **Sirve para:** Errores de puerto.
- **Opciones y filtros:** grep: texto sensible a mayúsculas
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Presencia de VLAN 20

```text
show vlan | grep 20
```

- **Sirve para:** Presencia de VLAN 20.
- **Opciones y filtros:** grep: coincidencia texto
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

