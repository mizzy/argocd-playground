```
$ argocd app create presync-and-syncfail-test \
    --repo https://github.com/mizzy/argocd-playground.git \
    --path presync-and-syncfail-test \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```
