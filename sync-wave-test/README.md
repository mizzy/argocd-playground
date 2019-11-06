```
$ argocd app create sync-wave-test \
    --repo https://github.com/mizzy/argocd-playground.git \
    --path sync-wave-test \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```
