# VProfile Helm — Kubernetes Packaging

**Helm chart** for deploying the VProfile multi-tier application to Kubernetes. This is the configuration repository that **Argo CD** watches and syncs to the EKS cluster (GitOps: Git is the source of truth).

## What this repo does

- Templated Kubernetes manifests for the full stack — app (Tomcat), database (MySQL), Memcached, RabbitMQ, and Ingress
- Values-driven configuration (`values.yaml`): image, tag, replicas, ports, storage
- The CI pipeline updates the app image tag here on each push; **Argo CD** then syncs the change to **Amazon EKS**

## Contents

- `helm/vprofile/` — the Helm chart (templates + values)
- `kubedefs/` — Kubernetes manifests

## Related repositories

- **[vprofile-app-public](https://github.com/thomasjosey540/vprofile-app-public)** — app + GitHub Actions CI/CD
- **[vprofile-infra-public](https://github.com/thomasjosey540/vprofile-infra-public)** — Terraform (EKS) + Argo CD

## Security

Secret values are placeholders. Real credentials are supplied at deploy time via Kubernetes Secrets and are not committed.
