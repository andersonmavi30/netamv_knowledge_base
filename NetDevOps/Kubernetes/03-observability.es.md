---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Logs y observabilidad

[🇬🇧 English](03-observability.md) · [🇨🇴 Español](03-observability.es.md) · [↩ Kubernetes](README.es.md)

**Plataforma:** Kubernetes / kubectl; ejemplos pendientes de validación en laboratorio.

## `kubectl logs -n automation deployment/awx-web --tail=100`

```bash
kubectl logs -n automation deployment/awx-web --tail=100
```

- **Sirve para:** Leer las últimas 100 líneas de logs de un deployment cuando el destino se resuelve sin ambigüedad.
- **Parámetros:** `-n automation`: namespace; `deployment/awx-web`: carga objetivo; `--tail=100`: últimas 100 líneas.
- **Ejemplo de uso:** Investigar un fallo de AWX web sin extraer logs ilimitados.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_logs/

> Pendiente de validación en laboratorio. Los logs pueden contener datos sensibles.

## `kubectl get events -n automation --sort-by=.metadata.creationTimestamp`

```bash
kubectl get events -n automation --sort-by=.metadata.creationTimestamp
```

- **Sirve para:** Listar eventos del namespace ordenados por fecha de creación.
- **Parámetros:** `get events`: enumera eventos; `-n`: namespace; `--sort-by`: ordena por campo JSONPath.
- **Ejemplo de uso:** Relacionar problemas de scheduling y errores de descarga de imágenes.
- **Referencia oficial:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Pendiente de validación en laboratorio. Los logs pueden contener datos sensibles.
