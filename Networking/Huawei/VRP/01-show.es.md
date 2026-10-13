---
tags: [cli, huawei, vrp, show]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Huawei](../README.es.md)

**Plataforma:** Huawei / VRP · **Versión orientativa:** VRP (generic; confirm your device's release).

## `display version`

```text
display version
```

- **Sirve para:** Muestra versión VRP y uptime.
- **Parámetros/filtros:** Sin flags; comprueba equipo y versión.
- **Caso real:** Identificar versión antes de cambios.

## `display device`

```text
display device
```

- **Sirve para:** Muestra hardware y estado de tarjetas.
- **Parámetros/filtros:** Sin flags; puede variar por equipo.
- **Caso real:** Revisar hardware antes del diagnóstico.

## `display interface brief`

```text
display interface brief
```

- **Sirve para:** Resume enlaces y contadores de errores.
- **Parámetros/filtros:** brief: vista resumida.
- **Caso real:** Encontrar puertos caídos.

## `display ip interface brief`

```text
display ip interface brief
```

- **Sirve para:** Lista interfaces IPv4 y estado.
- **Parámetros/filtros:** brief: tabla IP resumida.
- **Caso real:** Comprobar IP de VLANIF de gestión.

## `display ip routing-table 198.51.100.10`

```text
display ip routing-table 198.51.100.10
```

- **Sirve para:** Consulta rutas para una IP destino.
- **Parámetros/filtros:** IP: consulta por destino.
- **Caso real:** Revisar forwarding a un host remoto.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
