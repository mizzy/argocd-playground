## Create an application

```
$ argocd app create postsync-and-syncfail-test \
    --repo https://github.com/mizzy/argocd-playground.git \
    --path postsync-and-syncfail-test \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```

## Set up sealed-secrets and encrypt slack webhool url

```
$ kubectl apply -f https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.9.5/controller.yaml
```

```
$ brew install kubeseal
```

```
$ kubectl -n default create secret generic slack \
  --from-literal=webhook=https://slackwebhookurl \
  --dry-run \
  -o yaml > slack-secret.yaml
```

```
$ kubeseal --format=yaml \
  < slack-secret.yaml \
  > slack-sealedsecret.yaml
$ rm slack-secret.yaml
```
