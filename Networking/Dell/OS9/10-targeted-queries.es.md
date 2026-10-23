---
tags: [cli, targeted-troubleshooting, operations]
validation: not-lab-verified
---

# Búsquedas de operación — Dell OS9

[🇬🇧 English](10-targeted-queries.md) · [🇨🇴 Español](10-targeted-queries.es.md) · [↩ Índice](README.es.md)

> Los ejemplos son orientativos: valida el modelo, release y ayuda de CLI antes de usarlos.

## Hostname configurado

```text
show running-config | grep hostname
```

- **Sirve para:** Hostname configurado.
- **Opciones y filtros:** grep: coincidencias
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Errores CRC de puertos

```text
show interfaces | grep CRC
```

- **Sirve para:** Errores CRC de puertos.
- **Opciones y filtros:** grep: selecciona líneas
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Alarmas de enlaces

```text
show logging | grep DOWN
```

- **Sirve para:** Alarmas de enlaces.
- **Opciones y filtros:** grep: busca eventos
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Búsqueda de rutas

```text
show ip route | grep 203.0.113
```

- **Sirve para:** Búsqueda de rutas.
- **Opciones y filtros:** grep: filtro texto
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

## Configuración SNMP

```text
show running-config | grep snmp
```

- **Sirve para:** Configuración SNMP.
- **Opciones y filtros:** grep: coincidencias
- **Caso práctico:** Consultar solo los datos relevantes de este equipo para investigar una falla sin recorrer toda la salida.

