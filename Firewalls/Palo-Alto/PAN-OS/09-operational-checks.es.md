---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Consultas operativas adicionales

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** PAN-OS. Verificar versión y ayuda `?` del equipo.

## `show jobs all | match FIN`

```text
show jobs all | match FIN
```

- **Sirve para:** Buscar trabajos finalizados de commit y descarga sin revisar todos.
- **Parámetros:** jobs all: historial; match FIN: filtra estado de finalización.
- **Ejemplo de uso:** Comprobar resultado de un commit.

## `show session id 12345`

```text
show session id 12345
```

- **Sirve para:** Muestra el estado detallado de una sesión por ID.
- **Parámetros:** id 12345: identificador obtenido de tabla de sesiones.
- **Ejemplo de uso:** Comprobar origen, destino y estado al investigar un cliente.

## `show user ip-user-mapping ip 192.0.2.10`

```text
show user ip-user-mapping ip 192.0.2.10
```

- **Sirve para:** Consulta el usuario asociado a una IP origen.
- **Parámetros:** ip: dirección exacta; requiere User-ID configurado y con datos.
- **Ejemplo de uso:** Investigar fallas de políticas por usuario.

## `show system disk-space | match /opt/panlogs`

```text
show system disk-space | match /opt/panlogs
```

- **Sirve para:** Busca la partición de logs en el espacio de disco.
- **Parámetros:** match: filtra texto; rutas de partición varían.
- **Ejemplo de uso:** Revisar capacidad cuando desaparecen logs.

## `show high-availability all | match peer`

```text
show high-availability all | match peer
```

- **Sirve para:** Busca campos relacionados con el peer en estado HA.
- **Parámetros:** all: datos HA ampliados; match peer: filtro de texto.
- **Ejemplo de uso:** Revisar peer al diagnosticar failover.

> Ejemplos sin validar en laboratorio. Algunas funciones requieren licencia, configuración o privilegios.

**Documentación oficial:** https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy
