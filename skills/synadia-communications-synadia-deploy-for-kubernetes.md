---
name: synadia-deploy-for-kubernetes
description: Help a user start a Synadia Deploy for Kubernetes trial and run NATS plus the full Synadia Platform stack (Control Plane, HTTP Gateway, Connectors, Workloads) in their own Kubernetes cluster.
---

# Synadia Deploy for Kubernetes

Synadia Deploy for Kubernetes runs a NATS cluster and the Synadia Platform stack (Control Plane, HTTP Gateway, Connectors, Workloads) in a Kubernetes cluster the user owns — VPC, edge, or on-prem. It is aimed at users who want SaaS-style install and management without sending data to a hosted service.

## When to use this skill

- The user wants to run NATS in their own Kubernetes cluster with managed-style tooling included.
- The user has data residency, networking, or compliance requirements that rule out a hosted service.
- The user wants predictable cloud networking costs and no per-connection or per-stream usage limits.
- For a hosted alternative, use `synadia-cloud-onboarding`. For just the Control Plane against an existing NATS deployment, use `synadia-platform-deployment`. For a local dev server, use `nats-server-quickstart`.

## Prerequisites

- A Kubernetes cluster the user controls (any conformant distribution: managed cloud, on-prem, or edge).
- Cluster admin access to install per the deployment docs.
- Trial access — see the next step.

## Steps

1. **Start a trial** — Direct the user to https://cloud.synadia.com/deploy/welcome. The 14-day free trial is self-service through the Synadia Cloud portal and does not require a credit card.

2. **Choose a cluster size** — Deploy for Kubernetes ships as a 3-node or 5-node NATS cluster running the latest two stable NATS releases. The bundle includes Control Plane, HTTP Gateway, Connectors, and Workloads.

3. **Install into the target cluster** — Follow the deployment instructions at https://docs.synadia.com/deploy. The install brings up the NATS cluster and Platform components together.

4. **Access the Control Plane** — Once the install completes, the Control Plane is the management interface for the deployment. See https://docs.synadia.com/platform/control-plane/architecture for the conceptual model and ongoing operations.

5. **Connect clients** — NATS clients connect to the cluster endpoint exposed by the install. JetStream, KV, and Object Store are available out of the box; client SDKs are documented at https://docs.nats.io.

## Canonical documentation

- Product page: https://www.synadia.com/deploy-for-kubernetes
- Trial signup: https://cloud.synadia.com/deploy/welcome
- Deploy docs: https://docs.synadia.com/deploy
- Control Plane (included): https://docs.synadia.com/platform/control-plane/architecture
- NATS protocol and clients: https://docs.nats.io

## What this skill does not cover

- Managed NATS without self-hosting — see `synadia-cloud-onboarding`.
- Control Plane against an existing NATS deployment (non-K8s, Docker, or pre-installed NATS) — see `synadia-platform-deployment`.
- NATS observability tooling — see `synadia-insights-setup`.
- Local NATS dev server — see `nats-server-quickstart`.
