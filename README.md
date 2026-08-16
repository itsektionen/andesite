# Andesite - V1

Andesite is a github action for deploying to IN-SMN.

## Usage

Copy the following template into `.github/workflows/deploy.yaml` in your repository.

```yaml
name: Build and deploy

on:
  push:
    branches: ["main"] # Change this if your main branch is not called main

jobs:
  build-and-deploy:
    permissions:
      contents: read
      packages: write
    uses: itsektionen/andesite/.github/workflows/v1.yml@main
    secrets: inherit
    with:
      deploy-dir: <deploy-dir> # Update this
```

Replace `<deploy-dir>` with the directory on IN-SMN that the docker-compose.yaml is in. (i.e. `/home/deploy/<deploy-dir>/docker-compose.yaml`)¨

For mor information on deployment, see [docs.kth.it](https://docs.kth.it/docs/infrastructure/in-smn/containers#automatic-deployment).

For a list of settings, see [configuring Andesite](https://docs.kth.it/docs/infrastructure/in-smn/containers#configuring-andesite).
