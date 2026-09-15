# Workflows réutilisables nod3win

`vpsctl-deploy.yml` : build sur GitHub → artefact → VPS via vpsctl. Dans chaque repo, `.github/workflows/deploy.yml` :

```yaml
name: Deploy
on:
  push: { branches: [main] }
  workflow_dispatch:
jobs:
  deploy:
    uses: nod3win/.github/.github/workflows/vpsctl-deploy.yml@main
    with: { app: mon-app }       # + dir: sous-dossier, type: next|node|static|python, static-dir: dist
    secrets: inherit             # VPS_DEPLOY_KEY (secret du repo)
```
