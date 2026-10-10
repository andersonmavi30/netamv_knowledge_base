---
tags: [cli, cisco, ios-xe, troubleshooting]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# 🛠️ Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS XE · **Compatibilidad:** Cisco IOS XE 17.x (depende del modelo; valida tu versión).

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad ICMP hacia un destino IPv4.
- **Parámetros:** IP: host destino.
- **Ejemplo de uso:** Confirmar alcance desde el router.

## `traceroute 192.0.2.10`

```text
traceroute 192.0.2.10
```

- **Sirve para:** Muestra ruta salto por salto hacia un destino IPv4.
- **Parámetros:** IP: destino.
- **Ejemplo de uso:** Localizar un fallo de ruta.

## `show logging`

```text
show logging
```

- **Sirve para:** Consulta mensajes del buffer de logs.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Detectar eventos de caída y subida de enlace.

## `show interfaces GigabitEthernet1/0/1`

```text
show interfaces GigabitEthernet1/0/1
```

- **Sirve para:** Revisa estado, dúplex, contadores y errores.
- **Parámetros:** Nombre de interfaz: usa uno real del equipo.
- **Ejemplo de uso:** Buscar errores de entrada y descartes.

> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf
