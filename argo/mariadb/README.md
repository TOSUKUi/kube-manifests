```
k apply -f argo/mariadb/secrets.yml

argocd app create mariadb --repo https://github.com/TOSUKUi/kube-manifests \
  --dest-server https://kubernetes.default.svc \
  --path ./argo/mariadb

argocd app set mariadb --sync-policy automated --auto-prune --allow-empty
```
