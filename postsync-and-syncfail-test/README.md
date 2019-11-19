```
$ argocd app create postsync-and-syncfail-test \
    --repo https://github.com/mizzy/argocd-playground.git \
    --path postsync-and-syncfail-test \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```
