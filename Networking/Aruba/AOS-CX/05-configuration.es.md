---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Configuración

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; validar por modelo y release.

## `hostname CX-LAB`

```text
configure terminal
hostname CX-LAB
end
```

**Validar con:**

```text
show running-config | include hostname
```

- **Sirve para:** Cambia el hostname.
- **Parámetros:** hostname: identidad.
- **Ejemplo de uso:** Nombrar switch.

## `vlan 10`

```text
configure terminal
vlan 10
name USERS
end
```

**Validar con:**

```text
show vlan | include 10
```

- **Sirve para:** Crea VLAN 10 y la etiqueta.
- **Parámetros:** vlan: ID; name: etiqueta.
- **Ejemplo de uso:** Preparar red.

## `interface 1/1/2`

```text
configure terminal
interface 1/1/2
no routing
vlan access 10
no shutdown
end
```

**Validar con:**

```text
show running-config | begin interface 1/1/2
```

- **Sirve para:** Configura puerto access L2.
- **Parámetros:** no routing: L2; vlan access: VLAN.
- **Ejemplo de uso:** Conectar host.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

**Validar con:**

```text
show startup-config | include hostname
```

- **Sirve para:** Guarda configuración aprobada.
- **Parámetros:** running-config: origen; startup-config: guardada.
- **Ejemplo de uso:** Conservar cambios.

> Validar en laboratorio. Mirror/tshark requieren soporte y autorización; deshabilita al finalizar.
