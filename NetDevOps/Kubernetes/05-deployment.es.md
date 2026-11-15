---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Despliegues y rollout

[🇬🇧 English](05-deployment.md) · [🇨🇴 Español](05-deployment.es.md) · [↩ Kubernetes](README.es.md)

**Plataforma:** Kubernetes / kubectl; ejemplos pendientes de validación en laboratorio.

## `kubectl rollout status deployment/awx-web -n automation --timeout=120s`

```bash
kubectl rollout status deployment/awx-web -n automation --timeout=120s
```

- **Sirve para:** Esperar a que termine el despliegue y reportar si se completa en dos minutos.
- **Parámetros:** `rollout status`: consulta avance; `deployment/awx-web`: destino; `-n`: namespace; `--timeout=120s`: espera máxima.
- **Ejemplo de uso:** Validar el rollout de AWX web tras un despliegue autorizado sin modificar su configuración.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_rollout/kubectl_rollout_status/

> Pendiente de validación en laboratorio.
