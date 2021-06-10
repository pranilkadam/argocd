
CLI
```
argocd app create --name test \
--repo https://github.com/pranilkadam/argocd \
--dest-server https://kubernetes.default.svc \
--dest-namespace argocd --path kubernetes
```

YAML

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test
  namespace: argocd
spec:
  project: default
  source:
    repoURL: https://github.com/pranilkadam/argocd.git
    targetRevision: HEAD
    path: argo/example-app
  destination:
    server: https://kubernetes.default.svc
    namespace: argocd
```

