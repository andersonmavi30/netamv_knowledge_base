---
tags: [cli, check-point, gaia, configuration]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Configuración

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Gaia Clish. Confirma versión R8x y rol antes de ejecutar.

## `set hostname CP-LAB`

```text
set hostname CP-LAB
```

- **Sirve para:** Establece hostname del laboratorio.
- **Parámetros:** set hostname: cambia nombre.
- **Ejemplo de uso:** Nombrar firewall de prueba.
- **Precaución:** Ejecuta `save config` tras validar.

## `set interface eth1 ipv4-address 192.0.2.1 mask-length 24`

```text
set interface eth1 ipv4-address 192.0.2.1 mask-length 24
```

- **Sirve para:** Asigna IPv4 a interfaz.
- **Parámetros:** eth1: puerto; mask-length: prefijo.
- **Ejemplo de uso:** Configurar interfaz LAN de prueba.
- **Precaución:** Puede cortar acceso de gestión.

## `show interface eth1`

```text
show interface eth1
```

- **Sirve para:** Verifica interfaz antes de guardar.
- **Parámetros:** show interface: consulta específica.
- **Ejemplo de uso:** Revisar IP/máscara.

## `save config`

```text
save config
```

- **Sirve para:** Guarda cambios de Gaia.
- **Parámetros:** save config: persiste configuración.
- **Ejemplo de uso:** Conservar cambios tras reiniciar.
- **Precaución:** Configuración Gaia distinta de instalación de políticas SmartConsole.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-commands-for-network-interfaces.htm)
