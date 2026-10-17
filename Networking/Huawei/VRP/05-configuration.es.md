---
tags: [cli, huawei, vrp, configuration]
vendor: Huawei
os: "VRP"
versions: "VRP (generic; confirm your device's release)"
validation: not-lab-verified
---

# ⚙️ Configuración general

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Huawei](../README.es.md)

**Plataforma:** Huawei / VRP · **Versión orientativa:** VRP (generic; confirm your device's release).

## `system-view`

```text
system-view
sysname HW-LAB
return
```

- **Sirve para:** Cambia el nombre del equipo.
- **Parámetros/filtros:** system-view: configuración; sysname: hostname; return: usuario.
- **Caso real:** Nombrar switch de laboratorio.

## `system-view`

```text
system-view
vlan 10
 quit
interface GigabitEthernet0/0/1
 port link-type access
 port default vlan 10
 quit
return
```

- **Sirve para:** Asigna puerto access a VLAN 10.
- **Parámetros/filtros:** port link-type access: L2 access; port default vlan 10: PVID.
- **Caso real:** Conectar host de laboratorio a VLAN 10.
- **Precaución:** Verifica rol de trunk/puerto; puede cortar tráfico.

## `system-view`

```text
system-view
ip route-static 198.51.100.0 255.255.255.0 192.0.2.254
return
```

- **Sirve para:** Crea ruta IPv4 estática en equipos con L3.
- **Parámetros/filtros:** prefijo/máscara: red; next-hop: router alcanzable.
- **Caso real:** Llegar a subred remota.
- **Precaución:** Requiere soporte L3 y next-hop alcanzable.


## `save`

```text
save
```

- **Sirve para:** Guarda configuración activa para reinicio.
- **Parámetros/filtros:** Puede pedir confirmación interactiva.
- **Caso real:** Guardar cambios probados.
- **Precaución:** Guarda después de revisar; VRP con candidate config puede requerir commit primero.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
