```
$ argocd app create hook-deletion-policy-test \
    --repo https://github.com/mizzy/argocd-playground.git \
    --path hook-deletion-policy-test \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```
