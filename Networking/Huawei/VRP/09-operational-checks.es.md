---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Verificaciones operativas adicionales — Huawei VRP

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** VRP generic (verify platform/release). Confirma comando y flags con la ayuda contextual de tu versión.

## Contadores de errores

```text
display interface counters errors | include GigabitEthernet
```

- **Sirve para:** Consulta errores de interfaces.
- **Parámetros / flags:** counters errors: vista de errores donde aplique.
- **Caso real:** Detectar uplink con problemas.
- **Filtro / verificación:** `display interface counters errors`

## Resumen de vecinos OSPF

```text
display ospf peer brief | include Init
```

- **Sirve para:** Lista vecinos OSPF resumidos.
- **Parámetros / flags:** brief: tabla resumida.
- **Caso real:** Buscar vecino no Full.
- **Filtro / verificación:** `display ospf peer brief | include Init`

## Tabla de rutas estáticas

```text
display ip routing-table protocol static | include 198.51.100
```

- **Sirve para:** Muestra solo rutas estáticas.
- **Parámetros / flags:** protocol static: filtro de origen.
- **Caso real:** Verificar ruta estática.
- **Filtro / verificación:** `display ip routing-table protocol static | include 198.51.100`

## Verificación de hora

```text
display clock
```

- **Sirve para:** Muestra fecha, hora y zona horaria.
- **Parámetros / flags:** Sin parámetros.
- **Caso real:** Correlacionar alarmas con logs.
- **Filtro / verificación:** `display clock`

## Consumo de CPU

```text
display cpu-usage
```

- **Sirve para:** Consulta CPU donde esté disponible.
- **Parámetros / flags:** Estadísticas varían por modelo y tarjeta.
- **Caso real:** Investigar lentitud de CLI.
- **Filtro / verificación:** `display cpu-usage`

> ⚠️ Referencia de laboratorio aún no probada; distintas plataformas Dell y Huawei pueden usar variantes de comandos.

[Referencia del fabricante](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands)
