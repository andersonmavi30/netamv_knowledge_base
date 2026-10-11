---
tags: [cli, fortinet, fortios, filters]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔍 Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Compatibilidad:** FortiOS 7.x (comprueba tu versión exacta).

## `get system status | grep Version`

```text
get system status | grep Version
```

- **Sirve para:** Muestra líneas que contienen Version.
- **Parámetros:** |: tubería; grep: búsqueda de texto.
- **Ejemplo de uso:** Localizar versión de firmware.

- **Filtro práctico:** `get system status | grep -i hostname` — Ejemplo real: busca el hostname sin distinguir mayúsculas.

## `get system status | grep -i hostname`

```text
get system status | grep -i hostname
```

- **Sirve para:** Busca sin distinguir mayúsculas/minúsculas.
- **Parámetros:** -i: ignora mayúsculas/minúsculas.
- **Ejemplo de uso:** Buscar el hostname sin importar mayúsculas.

- **Filtro práctico:** `get system status | grep -i version` — Busca la versión del firmware con -i.

## `show system interface | grep -f port3`

```text
show system interface | grep -f port3
```

- **Sirve para:** Muestra el bloque de configuración coincidente con contexto (si es compatible).
- **Parámetros:** -f: salida con contexto de configuración.
- **Ejemplo de uso:** Ubicar los ajustes de port3.

- **Filtro práctico:** `show firewall address | grep -f LAB-NET` — Conserva el contexto del objeto coincidente.

## `get system interface | grep -n port3`

```text
get system interface | grep -n port3
```

- **Sirve para:** Muestra coincidencias con número de línea.
- **Parámetros:** -n: numeración de líneas.
- **Ejemplo de uso:** Encontrar port3 en salidas extensas.

- **Filtro práctico:** `diagnose vpn tunnel list | grep -n name=` — Busca nombres de túneles con números de línea.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
