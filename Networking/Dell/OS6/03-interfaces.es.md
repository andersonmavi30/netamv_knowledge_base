---
tags: [cli, dell, os6, interfaces]
validation: not-lab-verified
---

# Interfaces — Dell OS6

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verifica con `show version` y `?`.

## `show interfaces switchport`

```text
show interfaces switchport | include 1/0/1
```

- **Sirve para:** Consulta modos de puertos L2.
- **Parámetros:** Sin opciones.
- **Caso real:** Revisar trunk/access.

## `show running-config interface gigabitethernet 1/0/1`

```text
show running-config interface gigabitethernet 1/0/1
```

- **Sirve para:** Revisa la configuración de un puerto.
- **Parámetros:** interface: selecciona puerto.
- **Caso real:** Ver VLAN de acceso antes de cambiar.

## `interface gigabitethernet 1/0/2`

```text
configure
interface gigabitethernet 1/0/2
 description LAB-UPLINK
 exit
exit
```

- **Sirve para:** Configura descripción del puerto.
- **Parámetros:** interface: puerto; description: etiqueta.
- **Caso real:** Identificar uplink de laboratorio.

## `show interfaces description | include UPLINK`

```text
show interfaces description | include UPLINK
```

- **Sirve para:** Busca puertos cuya descripción configurada contiene UPLINK.
- **Opciones:** description: puertos y etiquetas; | include: filtra texto en versiones OS6 compatibles.
- **Caso práctico:** Identificar el uplink entre switches serie N durante una auditoría.
- **Compatibilidad:** OS6 serie N; confirma soporte de pipe en la versión instalada.
- **Referencia:** [Documentación del fabricante](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
