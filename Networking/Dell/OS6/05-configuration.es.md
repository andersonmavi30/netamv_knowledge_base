---
tags: [dell, os6, cli]
validation: not-lab-verified
---

# Configuración — Dell OS6

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS6 — generally N-series (check model/release).

## `configure`

```text
configure
hostname DELL-LAB
exit
```

- **Sirve para:** Configura hostname en OS6 compatible.
- **Parámetros:** hostname: nombre del equipo.
- **Caso práctico:** Identificar switch de prueba.
- **Verificación:** `show running-config`

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Sirve para:** Guarda configuración activa donde aplique.
- **Parámetros:** running-config: origen; startup-config: destino.
- **Caso práctico:** Conservar cambios tras reinicio.
- **Verificación:** `show running-config`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
