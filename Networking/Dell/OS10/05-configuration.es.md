---
tags: [dell, os10, cli]
validation: not-lab-verified
---

# Configuración — Dell OS10

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Dell SmartFabric OS10 — supported PowerSwitch platforms; verify release/model.

## `configure terminal`

```text
configure terminal
hostname DELL-LAB
end
```

- **Sirve para:** Configura hostname.
- **Parámetros:** configure terminal: modo config; hostname: nombre; end: salir.
- **Caso práctico:** Nombrar switch.
- **Verificación:** `show running-configuration`

## `copy running-configuration startup-configuration`

```text
copy running-configuration startup-configuration
```

- **Sirve para:** Guarda configuración OS10 donde aplique.
- **Parámetros:** running-configuration: origen; startup-configuration: destino.
- **Caso práctico:** Persistir cambio validado.
- **Verificación:** `show running-configuration`

> Referencia orientativa y pendiente de validación en laboratorio. Dell tiene familias con CLI diferentes; comprueba la documentación del modelo antes de ejecutar comandos.

[Dell Support](https://www.dell.com/support/home/en-us/products/networking)
