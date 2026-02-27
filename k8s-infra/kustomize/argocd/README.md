# Argo CD Deployment

This directory uses an app-of-apps pattern and has Argo CD manage itself.

## Layout

- `kustomization.yaml`: one-time bootstrap entrypoint (Argo CD install + root app-of-apps application).
- `app-of-apps.yaml`: root Argo CD Application.
- `apps/`: child applications managed by app-of-apps (includes `namespaces` app).
- `self/`: Argo CD self-management kustomization.
- `install/`: Argo CD installation manifests (pins the HA install URL).

## Bootstrap

```bash
kubectl apply -k kustomize/argocd
```
