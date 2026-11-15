---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Servicios y redes

[🇬🇧 English](04-networking.md) · [🇨🇴 Español](04-networking.es.md) · [↩ Kubernetes](README.es.md)

**Plataforma:** Kubernetes / kubectl; ejemplos pendientes de validación en laboratorio.

## `kubectl get svc -n automation -o wide`

```bash
kubectl get svc -n automation -o wide
```

- **Sirve para:** Listar los Services Kubernetes, sus tipos, IP internas y puertos expuestos en el namespace.
- **Parámetros:** `get svc`: consulta Services; `-n automation`: namespace; `-o wide`: columnas adicionales.
- **Ejemplo de uso:** Verificar cómo se publica AWX web dentro de un clúster K3s.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Pendiente de validación en laboratorio.

## `kubectl get endpointslices -n automation`

```bash
kubectl get endpointslices -n automation
```

- **Sirve para:** Consultar recursos EndpointSlice con los endpoints backend de los Services.
- **Parámetros:** `get endpointslices`: lista EndpointSlice; `-n automation`: namespace; requiere permisos RBAC.
- **Ejemplo de uso:** Verificar endpoints de un Service antes de analizar conectividad.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Pendiente de validación en laboratorio.
