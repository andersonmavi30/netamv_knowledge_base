---
tags: [cli, cisco, ios, filters]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🔍 Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS · **Versiones de referencia:** IOS 15.x (classic; feature availability varies). Confirma el comando en tu versión instalada.

## `show ip interface brief | include GigabitEthernet`

```text
show ip interface brief | include GigabitEthernet
```

- **Sirve para:** Muestra solo líneas coincidentes.
- **Parámetros:** |: tubería; include: líneas que coinciden.
- **Ejemplo de uso:** Listar solo GigabitEthernet.

## `show logging | exclude LINK`

```text
show logging | exclude LINK
```

- **Sirve para:** Oculta mensajes que contienen LINK.
- **Parámetros:** exclude: descartar coincidencias.
- **Ejemplo de uso:** Revisar otros errores.

## `show running-config | begin interface`

```text
show running-config | begin interface
```

- **Sirve para:** Muestra la salida desde la primera coincidencia.
- **Parámetros:** begin: primera coincidencia y todo lo posterior.
- **Ejemplo de uso:** Saltar cabecera global.

## `show running-config | section router`

```text
show running-config | section router
```

- **Sirve para:** Muestra bloques de configuración que empiezan por router.
- **Parámetros:** section: coincide con una sección.
- **Ejemplo de uso:** Revisar configuración de procesos de routing.

> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
