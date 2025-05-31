# Flux GitOps Repository

This repository contains Kubernetes manifests and Flux configuration for GitOps deployments.

## Repository Structure

```
.
├── clusters/           # Cluster-specific configurations
│   └── production/     # Production cluster configuration
├── infrastructure/     # Infrastructure components
├── apps/              # Application deployments
└── flux-system/       # Flux system components
```

## Prerequisites

- Kubernetes cluster
- Flux CLI
- kubectl configured to access your cluster

## Getting Started

1. Install Flux CLI:
```bash
brew install fluxcd/tap/flux
```

2. Bootstrap Flux:
```bash
flux bootstrap github \
  --owner=PhamMinhHiepIT2 \
  --repository=flux-example \
  --branch=main \
  --path=./clusters/production \
  --personal
```

## Directory Structure

- `clusters/`: Contains cluster-specific configurations
  - `production/`: Production cluster configuration
- `infrastructure/`: Infrastructure components like databases, monitoring, etc.
- `apps/`: Application deployments
- `flux-system/`: Flux system components

## Adding New Applications

1. Create a new directory under `apps/` for your application
2. Add your Kubernetes manifests
3. Create a Kustomization file to manage the deployment
4. Reference the new Kustomization in the cluster's kustomization.yaml

## Maintenance

- Keep your Flux version up to date
- Regularly check for updates to your deployed applications
- Monitor the health of your GitOps deployments

## Contributing

1. Create a new branch for your changes
2. Make your changes
3. Submit a pull request

## License

MIT
