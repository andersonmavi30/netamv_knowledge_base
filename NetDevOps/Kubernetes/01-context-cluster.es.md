---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Contexto y clúster

[🇬🇧 English](01-context-cluster.md) · [🇨🇴 Español](01-context-cluster.es.md) · [↩ Kubernetes](README.es.md)

**Plataforma:** Kubernetes / kubectl; ejemplos pendientes de validación en laboratorio.

## `kubectl version --client`

```bash
kubectl version --client
```

- **Sirve para:** Consultar la versión del cliente kubectl sin contactar al clúster.
- **Parámetros:** `version`: información de versión; `--client`: solo cliente, sin consultar API server.
- **Ejemplo de uso:** Comprobar la herramienta antes de administrar un laboratorio K3s.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_version/

> No verificado en laboratorio.
