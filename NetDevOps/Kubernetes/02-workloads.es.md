---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Cargas de trabajo y recursos

[🇬🇧 English](02-workloads.md) · [🇨🇴 Español](02-workloads.es.md) · [↩ Kubernetes](README.es.md)

**Plataforma:** Kubernetes / kubectl; ejemplos pendientes de validación en laboratorio.

## `kubectl get pods -n automation -o wide`

```bash
kubectl get pods -n automation -o wide
```

- **Sirve para:** Consultar pods del namespace automation, incluyendo nodo asignado e IP.
- **Parámetros:** `get pods`: lista pods; `-n automation`: selecciona namespace; `-o wide`: columnas adicionales.
- **Ejemplo de uso:** Ubicar el nodo que aloja un pod de AWX con reinicios.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Pendiente de validación en laboratorio.
