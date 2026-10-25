---
tags: [cli, palo-alto-networks, pan-os, configuration]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Ejemplos de configuración

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice PAN-OS](README.es.md)

**Plataforma:** Palo Alto Networks / PAN-OS · **Compatibilidad:** confirma la versión instalada con `show system info | match sw-version`. Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Configurar hostname del firewall

```text
configure
set deviceconfig system hostname PA-LAB
```

**Validar configuración candidata:**

```text
show deviceconfig system | match hostname
```

- **Sirve para:** Define hostname en configuración candidata y lo consulta.
- **Parámetros:** configure: modo config; set: cambio candidato; show: verifica candidato; commit: acción aparte.
- **Ejemplo de uso:** Identificar firewall de laboratorio sin aplicar commit.
- **Precaución:** No hacer commit en producción sin revisión y validar conectividad.

## Configurar DNS primario de gestión

```text
configure
set deviceconfig system dns-setting servers primary 192.0.2.53
```

**Validar configuración candidata:**

```text
show deviceconfig system dns-setting servers
```

- **Sirve para:** Define DNS primario del plano de gestión en candidate.
- **Parámetros:** primary: resolver preferido; show: consulta candidata.
- **Ejemplo de uso:** Preparar cambio DNS de laboratorio y revisar valor.
- **Precaución:** Cambiar DNS puede afectar actualizaciones y objetos FQDN tras commit.

## Crear objeto de IP

```text
configure
set address LAB-HOST ip-netmask 192.0.2.10
```

**Validar configuración candidata:**

```text
show address LAB-HOST
```

- **Sirve para:** Crea objeto host en vsys actual.
- **Parámetros:** address: nombre; ip-netmask: host/prefijo; show: revisión candidata.
- **Ejemplo de uso:** Preparar objeto para política futura.
- **Precaución:** Verifica propiedad vsys/Panorama antes de cambiar objetos.

## Asignar IPv4 a interfaz capa 3

```text
configure
set network interface ethernet ethernet1/3 layer3 ip 192.0.2.1/24
```

**Validar configuración candidata:**

```text
show network interface ethernet ethernet1/3
```

- **Sirve para:** Agrega dirección IPv4 a interfaz en candidate.
- **Parámetros:** ethernet1/3: interfaz; layer3: modo L3; ip: CIDR.
- **Ejemplo de uso:** Preparar direccionamiento LAN en laboratorio.
- **Precaución:** Cambiar modo/IP puede interrumpir acceso remoto después del commit.

## Aplicar candidate revisada

```text
configure
show | match LAB-HOST
commit
```

- **Sirve para:** Aplica configuración candidata revisada.
- **Parámetros:** show: consulta candidata; commit: activa cambios.
- **Ejemplo de uso:** Aplicar cambio aprobado luego de prechecks.
- **Precaución:** Commit puede aplicar cambios pendientes de otros; coordina con administradores.

> Referencia breve, pendiente de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/use-the-cli/cli-jump-start) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/get-started-with-the-cli/get-help-on-command-syntax)
