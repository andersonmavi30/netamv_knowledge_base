---
tags: [cli, juniper, junos]
validation: not-lab-verified
---

# Interfaces y transceptores

[English](03-interfaces.md) · [Español](03-interfaces.es.md) · [Índice](README.es.md)

**Compatibilidad:** Junos OS; verificar modelo, versión y `?`.

## `show interfaces terse`

```text
show interfaces terse
```

- **Sirve para:** Resumir estados administrativos y de enlace de interfaces físicas y lógicas.
- **Parámetros:** terse: tabla resumida de estados y direcciones; inet indica IPv4.
- **Ejemplo de uso:** Encontrar interfaces caídas o con IP inesperadas.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-interfaces-gigabit-ethernet.html

> Pendiente de validación en laboratorio.

## `show interfaces diagnostics optics ge-0/0/0`

```text
show interfaces diagnostics optics ge-0/0/0
```

- **Sirve para:** Consultar potencia óptica RX/TX y alarmas del transceptor.
- **Parámetros:** diagnostics optics: métricas DOM; ge-0/0/0: puerto; requiere óptico compatible.
- **Ejemplo de uso:** Diagnosticar baja potencia óptica RX en un uplink.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/ref/command/show-interfaces-security.html

> Pendiente de validación en laboratorio.

## `show interfaces descriptions`

```text
show interfaces descriptions
```

- **Sirve para:** Listar interfaces, descripciones configuradas y estados operativos.
- **Parámetros:** descriptions: resumen de interfaces con etiquetas configuradas.
- **Ejemplo de uso:** Encontrar el uplink de un vecino sin revisar toda la configuración.
- **Referencia oficial:** https://www.juniper.net/documentation/us/en/software/junos/cli-reference/topics/topic-map/operational-commands.html

> Pendiente de validación en laboratorio.
