---
tags: [cli, check-point, gaia, field-commands]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Verificaciones operativas

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert. Confirma versión R8x y rol antes de ejecutar.

## `cpstat os -f memory`

```text
cpstat os -f memory
```

- **Sirve para:** Consulta memoria del sistema.
- **Parámetros:** -f memory: estadísticas de memoria.
- **Ejemplo de uso:** Investigar consumo de recursos.

## `cpview`

```text
cpview
```

- **Sirve para:** Abre diagnóstico interactivo.
- **Parámetros:** Consola interactiva; salir por menú.
- **Ejemplo de uso:** Localizar consumo de CPU.
- **Precaución:** No agregues grep a cpview interactivo.

## `vpn tu conn 192.0.2.10 54321 198.51.100.20 443 6`

```text
vpn tu conn 192.0.2.10 54321 198.51.100.20 443 6
```

- **Sirve para:** Consulta conexión VPN cifrada.
- **Parámetros:** IP/puerto origen, IP/puerto destino, protocolo 6 TCP.
- **Ejemplo de uso:** Investigar falta de cifrado.

## `clish -c "show ntp"`

```text
clish -c "show ntp"
```

- **Sirve para:** Consulta configuración NTP.
- **Parámetros:** -c: comando Gaia Clish.
- **Ejemplo de uso:** Verificar configuración horaria.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)
