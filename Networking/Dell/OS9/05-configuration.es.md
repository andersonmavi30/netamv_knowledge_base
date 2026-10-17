---
tags: [cli, dell, os9, configuration]
validation: not-lab-verified
---

# Configuración — Dell OS9

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verifica con `show version` y `?`.

## `hostname DELL-LAB`

```text
configure
hostname DELL-LAB
end
```

- **Sirve para:** Configura hostname en OS9 compatible.
- **Parámetros:** hostname: nombre.
- **Caso real:** Nombrar equipo.

## `write memory`

```text
write memory
```

- **Sirve para:** Guarda cambios validados.
- **Parámetros:** write memory: persiste configuración.
- **Caso real:** Conservar cambios.

## `show configuration`

```text
show configuration
```

- **Sirve para:** Consulta configuración en modos compatibles.
- **Parámetros:** Disponible en contextos compatibles.
- **Caso real:** Revisar antes de guardar.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
