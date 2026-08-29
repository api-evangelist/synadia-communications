---
name: synadia-cloud-onboarding
description: Help a user sign up for Synadia Cloud (managed NATS), create their first system and account, and connect a NATS client to send their first message.
---

# Synadia Cloud Onboarding

Synadia Cloud is a fully-managed NATS service operated by Synadia, the creators of NATS. Use this skill when a user wants managed NATS messaging without running their own infrastructure.

## When to use this skill

- The user asks how to get started with Synadia Cloud, NGS, or hosted NATS.
- The user needs a NATS endpoint for an application, agent fleet, or prototype and does not want to run a server themselves.
- The user explicitly wants a managed offering (otherwise see the `nats-server-quickstart` skill for self-hosted).

## Prerequisites

- An email address (signup is self-serve).
- The `nats` CLI installed locally — see https://github.com/nats-io/natscli/releases or `brew install nats-io/nats-tools/nats` on macOS.

## Steps

1. **Sign up** — Direct the user to https://cloud.synadia.com. Signup options are OAuth with GitHub or Google, email + password, or SSO for organizations that have it configured. Account creation is interactive and requires a human.

2. **Create a system** — In the Synadia Cloud dashboard, the user creates a *system*, an isolated NATS deployment in one or more regions. A default *account* is created inside the system automatically; accounts are isolation boundaries for users, streams, KV, and Object Store. Additional accounts can be added later.

3. **Download credentials** — From the account view, the user downloads a `.creds` file containing the JWT and nkey seed needed for client authentication.

4. **Connect with the `nats` CLI** — Save a context pointing at the Synadia Cloud global endpoint and the downloaded `.creds` file:

   ```bash
   nats context save synadia-cloud \
     --server tls://connect.ngs.global \
     --creds /path/to/account.creds
   nats context select synadia-cloud
   ```

   In one terminal, subscribe:

   ```bash
   nats sub demo.hello
   ```

   In a second terminal, publish:

   ```bash
   nats pub demo.hello "hello from my agent"
   ```

## Verification

The subscriber should print the published message immediately. If nothing arrives, verify the `.creds` file path and that `tls://connect.ngs.global` is reachable from the network running the client.

## Canonical documentation

- Synadia Cloud product page: https://www.synadia.com/cloud
- Synadia documentation: https://docs.synadia.com
- NATS protocol and client libraries: https://docs.nats.io
- Synadia Cloud signup: https://cloud.synadia.com/register

## What this skill does not cover

- Self-hosted NATS — see the `nats-server-quickstart` skill.
- Synadia Platform (Control Plane, self-managed) — see https://www.synadia.com/platform.
- JetStream stream/consumer design and KV/Object Store usage — defer to https://docs.nats.io.
