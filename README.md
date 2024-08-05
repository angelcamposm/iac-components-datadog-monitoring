# Kustomize Component | Datadog Unified Service Tagging

Este ejemplo de componente de [Kustomize](https://kustomize.io) muestra como añadir las etiquetas requeridas por [Unified Service Tagging](https://docs.datadoghq.com/getting_started/tagging/unified_service_tagging?tab=kubernetes) de [Datadog](https://www.datadoghq.com/).

## Requirements

- Requiere una versión de Kustomize v3.7.0 o superior.
- Se asume que el clúster objetivo, tiene desplegado el agente de Datadog.

Adicionalmente, para que el ejemplo funcione completamente, es necesario que en el `Deployment` objetivo en el primer contenedor (se da por supuesto que es la aplicación) exista el nodo `env` vacío o no:

Ejemplos:

```yaml
kind: Deployment
apiVersion: v1
metadata:
  name: my-app
spec:
  template:
    spec:
      containers:
        - name: app
          env: []
```

Con valores ya establecidos

```yaml
kind: Deployment
apiVersion: v1
metadata:
  name: my-app
spec:
  template:
    spec:
      containers:
        - name: app
          env:
            - name: APP
              value: my-awesome-app
```

## Maintainers

- 🧑‍💻 Angel Campos