---
tags: [cli, dell, os9, packet-debug]
validation: not-lab-verified
---

# Mirroring / debug — Dell OS9

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verifica con `show version` y `?`.

> ⚠️ Dell no usa un sniffer universal. Port mirroring exige un puerto de análisis y autorización. Detén las sesiones al terminar; los paquetes pueden incluir datos sensibles.

## `monitor interface ?`

```text
monitor interface ?
```

- **Sirve para:** Consultar sintaxis de monitor de interfaz en OS9.
- **Parámetros:** ?: ayuda contextual; no es PCAP.
- **Caso real:** Consultar contadores en vivo.

## `show interfaces | grep CRC`

```text
show interfaces | grep CRC
```

- **Sirve para:** Busca contadores CRC en salida.
- **Parámetros:** | grep: filtrado por texto.
- **Caso real:** Confirmar errores físicos.

## `show logging | grep OSPF`

```text
show logging | grep OSPF
```

- **Sirve para:** Busca eventos OSPF.
- **Parámetros:** | grep: eventos coincidentes.
- **Caso real:** Investigar reinicios OSPF.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
