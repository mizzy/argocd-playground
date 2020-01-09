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

