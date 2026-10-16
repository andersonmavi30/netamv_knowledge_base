---
tags: [dell, os9, cli]
validation: not-lab-verified
---

# Configuración — Dell OS9

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell Networking OS9 / FTOS — Force10-derived platforms, model-dependent.

## `configure`

```text
configure
hostname DELL-LAB
end
```

- **Sirve para:** Cambia hostname en laboratorio.
- **Parámetros:** configure: modo config; hostname: nombre; end: salir.
- **Caso práctico:** Renombrar switch.
- **Verificación:** `show running-config`

## `write memory`

```text
write memory
```

- **Sirve para:** Guarda configuración en OS9 compatible.
- **Parámetros:** write memory: persiste ajustes.
- **Caso práctico:** Guardar ajustes tras reiniciar.
- **Verificación:** `show running-config`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
