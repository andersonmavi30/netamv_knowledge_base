---
tags: [cli, fortinet, fortios, interfaces]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔌 Configuración de interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Compatibilidad:** FortiOS 7.x (comprueba tu versión exacta).

## `show system interface`

```text
show system interface
```

- **Sirve para:** Consulta configuración actual de interfaces.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Revisar antes de modificar una interfaz.

## `config system interface`

```text
config system interface
    edit "port3"
        set alias "LAB-LAN"
        set ip 192.0.2.1 255.255.255.0
        set allowaccess ping
    next
end
```

- **Sirve para:** Configura IP, alias y acceso de administración en una interfaz de laboratorio.
- **Parámetros:** edit: selecciona port3; set ip: IPv4/máscara; set allowaccess: protocolos permitidos; next/end: guardar y salir.
- **Ejemplo de uso:** Permitir ping a una interfaz de laboratorio.
- **Precaución:** Los cambios aplican inmediatamente. set allowaccess reemplaza la lista previa; nunca pegar sin revisar en producción.

## `get system interface`

```text
get system interface
```

- **Sirve para:** Verifica estado e IP después del cambio.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Confirmar que aparezca la nueva IP.

> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
