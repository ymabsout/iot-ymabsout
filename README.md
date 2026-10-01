# iot-ymabsout

GitOps source for **Inception-of-Things** part 3. Argo CD watches `app/` in this
repository and reconciles the `dev` namespace of the k3d cluster.

Switch versions by editing the image tag and pushing:

```sh
sed -i 's|wil42/playground:v1|wil42/playground:v2|' app/deployment.yaml
git commit -am "v2" && git push
```

Argo CD (auto-sync enabled) rolls the deployment within ~3 minutes, or instantly
with `argocd app sync playground`.
