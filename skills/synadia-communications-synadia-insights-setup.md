---
name: synadia-insights-setup
description: Help a user start a Synadia Insights trial, install the binary, connect it to a NATS deployment with system account credentials, and run the built-in checks for NATS observability.
---

# Synadia Insights

Synadia Insights is a purpose-built NATS observability tool. It models a NATS system as a time-series graph, ships 100+ built-in checks (slow consumers, gateway disconnection, stream quorum loss, high RTT, and more), and supports time-travel debugging across historical snapshots. Insights also exposes a read-only interface that AI agents can query in natural language.

## When to use this skill

- The user is troubleshooting NATS performance or reliability and needs deeper visibility than generic dashboards provide.
- The user wants automated detection of NATS-specific failure modes.
- The user wants AI agents to query NATS state with natural-language questions.
- Insights is a **standalone product**: it is designed for self-managed NATS and is **not compatible with Synadia Cloud**. For Cloud, use the built-in Cloud monitoring instead.

## Prerequisites

- A NATS deployment running **NATS Server v2.10 or newer**, in either operator mode or static config.
- **System account credentials** for the target NATS deployment — Insights reads system-level data.
- A host to run the Insights binary: macOS, Linux, or Windows.
- A trial key — see the next step.

## Steps

1. **Start a trial** — Direct the user to https://www.synadia.com/insights/trial. The 14-day free trial requires submitting an email form; a trial key is delivered in response.

2. **Download the binary** — Insights ships as a single binary for macOS, Linux, and Windows. See https://docs.synadia.com/insights/getting-started for current download links.

3. **Activate with the trial key** — Apply the key per the activation step in https://docs.synadia.com/insights/getting-started.

4. **Connect to a NATS system** — Point Insights at the NATS deployment using the system account credentials. Deployment options (single binary vs. long-running service) are documented at https://docs.synadia.com/insights/guides/deployment.

5. **Explore with the built-in simulator (optional)** — Insights ships with a simulator so the user can explore the product without a live NATS connection. Useful for first-time evaluation.

6. **Enable AI agent queries (optional)** — Configure the read-only interface for natural-language queries: https://docs.synadia.com/insights/guides/ai-agents.

## Verification

After connecting to a NATS system, the Insights UI shows the topology (servers, clusters, leaf nodes, JetStream assets, subscriptions) and begins reporting check status. Reference for what each check means: https://docs.synadia.com/insights/concepts/checks.

## Canonical documentation

- Product page: https://www.synadia.com/insights
- Trial signup: https://www.synadia.com/insights/trial
- Getting started: https://docs.synadia.com/insights/getting-started
- Deployment guide: https://docs.synadia.com/insights/guides/deployment
- AI agents guide: https://docs.synadia.com/insights/guides/ai-agents
- Built-in checks reference: https://docs.synadia.com/insights/concepts/checks

## What this skill does not cover

- Synadia Cloud monitoring — Insights does not run against Cloud; use Cloud's built-in tools.
- Running NATS itself — see `nats-server-quickstart` or `synadia-deploy-for-kubernetes`.
- Synadia Platform management — see `synadia-platform-deployment`.
