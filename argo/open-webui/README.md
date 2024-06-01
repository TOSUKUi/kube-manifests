```
argocd app create open-webui --repo https://github.com/TOSUKUi/kube-manifests \
  --dest-server https://kubernetes.default.svc \
  --path ./argo/open-webui \
  --dest-namespace default

argocd app set open-webui --sync-policy automated --auto-prune --allow-empty
```
