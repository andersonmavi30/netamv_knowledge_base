---
tags: [cli, dell, os10, interfaces]
validation: not-lab-verified
---

# Interfaces — Dell OS10

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verifica con `show version` y `?`.

## `show running-configuration interface ethernet 1/1/2`

```text
show running-configuration interface ethernet 1/1/2
```

- **Sirve para:** Revisa configuración de una interfaz.
- **Parámetros:** ethernet 1/1/2: puerto físico.
- **Caso real:** Revisar función de uplink.

## `show interface phy-eth 1/1/2`

```text
show interface phy-eth 1/1/2
```

- **Sirve para:** Consulta detalles físicos.
- **Parámetros:** phy-eth: estado de medio físico.
- **Caso real:** Diagnosticar transceptor.

## `interface ethernet 1/1/2`

```text
configure terminal
interface ethernet 1/1/2
 description LAB-UPLINK
 exit
end
```

- **Sirve para:** Etiqueta uplink de laboratorio.
- **Parámetros:** interface: puerto; description: etiqueta.
- **Caso real:** Identificar enlace.

## `show interface description | grep UPLINK`

```text
show interface description | grep UPLINK
```

- **Sirve para:** Encuentra uplinks etiquetados en la tabla de estado y descripciones OS10.
- **Opciones:** show interface description: puertos, estado y etiquetas; | grep: filtra líneas.
- **Caso práctico:** Identificar la interfaz Ethernet asignada al uplink de distribución.
- **Compatibilidad:** Disponible en OS10 10.5.2.3+; verifica plataforma y ayuda CLI.
- **Referencia:** [Documentación del fabricante](https://www.dell.com/support/manuals/en-us/smartfabric-os10-emp-partner/smartfabric-os-user-guide-10-6-1-x/show-interface-description?guid=guid-e3b56a69-81a3-48b7-99ba-9dea91d50933&lang=en-us)

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
