# Deploy

## Purpose
Run the full system locally and define deployment manifests for staging/production.

## Responsibilities
- Local Docker Compose to run `web-app` + `backend-api` (and a chain RPC if needed)
- Environment configuration
- Future: Kubernetes/Helm overlays

## Interactions with other repositories
- **web-app** / **backend-api**: builds/images referenced by compose/manifests
- **contracts**: provides addresses/ABIs referenced by services

## Local run (development)
1. Copy `compose/.env.example` to `compose/.env` and adjust values
2. Build from sources and run:
docker compose -f compose/docker-compose.dev.yml up --build

## Environments
- **dev** (local compose)
- **staging** (TBD)
- **production** (TBD)

See `SYSTEM-OVERVIEW.md` for the end-to-end diagram.
