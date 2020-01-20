## Create an application

```
$ argocd app create monitor-sync-fail-by-datadog \
    --repo https://github.com/mizzy/argocd-playground.git \
    --path monitor-sync-fail-by-datadog \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```

## Setup Datadog

https://app.datadoghq.com/signup/agent#kubernetes

Add annotations to argocd-server deployment.

```yaml
spec:
  template:
    metadata:
      annotations:
        ad.datadoghq.com/argocd-server.check_names: '["openmetrics"]'
        ad.datadoghq.com/argocd-server.init_configs: '[{}]'
        ad.datadoghq.com/argocd-server.instances: |
          [
             {
                "prometheus_url":"http://10.102.66.118:8082/metrics",
                "namespace":"argocd",
                "metrics":[
                  "argocd_app_sync_total",
                  "argocd_app_health_status"
                ]
             }
          ]
```
