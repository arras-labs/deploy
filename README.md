# Deploy

## Overview
Operational repository to run the full system locally and define staging/production manifests.

## Scope
- Local development via Docker Compose
- Environment configuration
- Production manifests (e.g., Kubernetes/Helm)

## Structure
- `compose/` local Docker Compose files
- `k8s/` base and overlays for environments (to be added)
- `docs/` operational notes

## Local run
- Copy `compose/.env.example` to `compose/.env` and adjust values
- Build and run from source repositories:
  `docker compose -f compose/docker-compose.dev.yml up --build`

## CI
Can validate manifests and compose files. Extend as the platform evolves.

## Secrets
Do not commit secrets. Use environment-specific stores or platform secret managers.
