```
k create ns nginx

argocd app create nginx --repo https://github.com/TOSUKUi/kube-manifests \
  --dest-namespace nginx \
  --dest-server https://kubernetes.default.svc \
  --path ./argo/nginx

argocd app set nginx --sync-policy automated --auto-prune --allow-empty
```
