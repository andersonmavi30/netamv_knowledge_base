---
tags: [cli, dell, os9, interfaces]
validation: not-lab-verified
---

# Interfaces — Dell OS9

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verifica con `show version` y `?`.

## `show interfaces tengigabitethernet 0/1`

```text
show interfaces tengigabitethernet 0/1
```

- **Sirve para:** Consulta enlace en Force10 compatible.
- **Parámetros:** Interfaz: valida unidad/puerto.
- **Caso real:** Revisar errores uplink.

## `show running-config`

```text
show running-config
```

- **Sirve para:** Consulta configuración antes de cambiar.
- **Parámetros:** Sin opciones.
- **Caso real:** Ubicar bloque de interfaz.

## `interface tengigabitethernet 0/1`

```text
configure
interface tengigabitethernet 0/1
 description LAB-UPLINK
exit
end
```

- **Sirve para:** Etiqueta uplink en OS9 compatible.
- **Parámetros:** interface: puerto físico; description: etiqueta.
- **Caso real:** Etiquetar puerto de prueba.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
