# Kivotos Platform

This repository contains the Kubernetes platform configuration for the Kivotos project. It uses [FluxCD](https://fluxcd.io/) and [Kustomize](https://kustomize.io/) to manage and deploy infrastructure and applications.

## Repository Structure

- `base/` - Base Kubernetes manifests and overlays
  - `application/` - Application manifests and kustomizations
  - `platform/` - Platform components (cert-manager, gateway-api, etc.)
- `cluster/` - Cluster-specific configuration and Flux system setup
- `example/` - Example Helm charts and values
- `util/` - Utility files (e.g., encryption keys)

## Getting Started

1. **Install FluxCD**  
   Follow the [FluxCD installation guide](https://fluxcd.io/docs/installation/).

2. **Bootstrap the Cluster**  
   Bootstrap cluster using flux cli.

   ```sh
   flux bootstrap github \                               
  --token-auth \
  --owner=dodistyo \
  --repository=kivotos \
  --branch=main \
  --path=cluster/sandbox \
  --personal
   ```

3. **Customize Your Deployment**  
   Edit the files in `base/` and `cluster/` as needed for your environment.

## Encryption

Secrets are managed using [SOPS](https://github.com/mozilla/sops) and [age](https://github.com/FiloSottile/age). See `.sops.yaml` for configuration.

## License

[MIT](LICENSE)