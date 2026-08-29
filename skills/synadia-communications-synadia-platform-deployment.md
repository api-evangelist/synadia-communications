---
name: synadia-platform-deployment
description: Guide a user through starting a Synadia Platform trial and deploying the Control Plane plus optional components (HTTP Gateway, Connectors, Workloads, FIPS) to manage a self-hosted NATS deployment.
---

# Synadia Platform

Synadia Platform packages NATS with enterprise features: a **Control Plane** to manage, secure, observe, and audit NATS systems and provision JetStream assets; an **HTTP Gateway** for HTTP access to NATS KV, Object Store, services, and messaging; **Connectors** for MongoDB, AWS, Azure, and GCP; **Workloads** for NATS-managed distributed compute; and a **FIPS 140-2** build for regulated environments.

## When to use this skill

- The user wants enterprise NATS with a management UI, RBAC, audit log, and observability.
- The user is self-hosting NATS and needs central control across regions or environments.
- The user requires FIPS compliance, mirrored data across regions, or KMS-backed secrets.
- For managed NATS without self-hosting, use the `synadia-cloud-onboarding` skill. For a turnkey on-cluster install of NATS + Platform together, use `synadia-deploy-for-kubernetes`.

## Prerequisites

- A target host to run the Control Plane — a Kubernetes cluster or a Docker host.
- A NATS deployment to manage (existing or new).
- Trial or production access — see the next step.

## Steps

1. **Choose a path** — Synadia Platform is available two ways:
   - **Self-managed trial (60 days, self-serve form)** — Direct the user to https://www.synadia.com/platform/trial. The trial requires submitting the form on that page (no credit card). The user installs and operates the Control Plane themselves on Kubernetes or Docker.
   - **Fully managed Platform (sales-led)** — Direct the user to https://www.synadia.com/contact to submit a primary contact inbound. A Synadia rep follows up to scope the engagement. Choose this path when the user wants Synadia to run Platform on their behalf rather than self-host.

   If the user chose the fully managed path, stop here — sales will drive the rest. Continue to step 2 only for the self-managed path.

2. **Choose a deployment target**:
   - Kubernetes: https://docs.synadia.com/platform/control-plane/deployment/kubernetes
   - Docker: https://docs.synadia.com/platform/control-plane/deployment/docker

3. **Install the Control Plane** — Follow the deployment guide for the chosen target. The Control Plane is the entry point that manages systems, accounts, JetStream assets, and connectors.

4. **Connect a NATS system** — In the Control Plane UI, register an existing NATS deployment or provision a new one. The conceptual model is documented at https://docs.synadia.com/platform/control-plane/architecture.

5. **Install the Control Plane CLI (optional)** — For scripted operations and CI workflows: https://docs.synadia.com/platform/control-plane/cli/setup.

6. **Enable optional components** — HTTP Gateway, Connectors, and Workloads can be enabled per the Platform docs once the Control Plane is running. For firewall-restricted networks, see Private Link: https://docs.synadia.com/platform/private-link.

## Canonical documentation

- Product page: https://www.synadia.com/platform
- Trial signup: https://www.synadia.com/platform/trial
- Control Plane architecture: https://docs.synadia.com/platform/control-plane/architecture
- Control Plane configuration: https://docs.synadia.com/platform/control-plane/configuration
- Kubernetes deployment: https://docs.synadia.com/platform/control-plane/deployment/kubernetes
- Docker deployment: https://docs.synadia.com/platform/control-plane/deployment/docker
- CLI setup: https://docs.synadia.com/platform/control-plane/cli/setup
- Private Link: https://docs.synadia.com/platform/private-link

## What this skill does not cover

- Running NATS itself on Kubernetes — see `synadia-deploy-for-kubernetes` for a turnkey NATS + Platform install, or `nats-server-quickstart` for a local dev server.
- Managed NATS — see `synadia-cloud-onboarding`.
- NATS observability — see `synadia-insights-setup`.
