```
k create ns communitization-bot

# prepare yourself
k apply -f argo/communitization-bot/secrets.yml -n communitization-bot

argocd app create communitization-bot --repo https://github.com/TOSUKUi/kube-manifests \
  --dest-namespace communitization-bot \
  --dest-server https://kubernetes.default.svc \
  --path ./argo/communitization-bot

argocd app set communitization-bot --sync-policy automated --auto-prune --allow-empty
```
