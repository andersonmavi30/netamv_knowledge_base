---
tags: [cli, cisco, ios, show]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🔎 Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS · **Versiones de referencia:** IOS 15.x (classic; feature availability varies). Confirma el comando en tu versión instalada.

## `show version`

```text
show version | include IOS|uptime
```

- **Sirve para:** Muestra versión de Cisco IOS, hardware y uptime.
- **Parámetros:** Sin opciones.
- **Ejemplo de uso:** Identificar la versión antes de cambiar.

- **Filtro práctico:** `show version | include IOS|uptime` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## `show ip interface brief`

```text
show ip interface brief | include GigabitEthernet
```

- **Sirve para:** Resume direcciones IPv4 y estado de enlaces.
- **Parámetros:** brief: vista resumida.
- **Ejemplo de uso:** Verificar que GigabitEthernet0/0 está up/up.

- **Filtro práctico:** `show ip interface brief | include GigabitEthernet` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## `show ip route`

```text
show ip route 198.51.100.10
```

- **Sirve para:** Muestra rutas IPv4 instaladas.
- **Parámetros:** Sin opciones.
- **Ejemplo de uso:** Encontrar una ruta activa.

- **Filtro práctico:** `show ip route 198.51.100.10` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## `show running-config`

```text
show running-config | include ^hostname
```

- **Sirve para:** Consulta la configuración activa.
- **Parámetros:** Sin opciones.
- **Ejemplo de uso:** Revisar antes de configurar.

- **Filtro práctico:** `show interfaces GigabitEthernet0/0 | include line protocol|errors|drops` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.


> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
