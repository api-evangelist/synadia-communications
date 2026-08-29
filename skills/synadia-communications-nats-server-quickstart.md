---
name: nats-server-quickstart
description: Install and run a local NATS server, install the nats CLI, and publish/subscribe a first message. Optionally enable JetStream for persistence.
---

# NATS Server Quickstart

NATS is the open-source cloud-native messaging system created and maintained by Synadia. Use this skill to stand up a local `nats-server` for development, testing, or evaluation.

## When to use this skill

- The user wants to run NATS locally for development.
- The user is evaluating NATS for the first time.
- The user explicitly does not want a managed service (otherwise see the `synadia-cloud-onboarding` skill).

## Prerequisites

- A terminal on macOS, Linux, or Windows.
- Optionally: Homebrew (macOS), Docker, or `curl` for binary install.

## Install `nats-server`

Choose one approach:

**macOS (Homebrew)**

```bash
brew install nats-server
```

**Docker**

```bash
docker run -p 4222:4222 nats:latest
```

**Binary release (any platform)**

Download the archive for your OS/arch from https://github.com/nats-io/nats-server/releases, extract it, and move the `nats-server` binary to a directory on `PATH`.

## Install the `nats` CLI

**macOS**

```bash
brew install nats-io/nats-tools/nats
```

**Other platforms**

Download from https://github.com/nats-io/natscli/releases.

## Run the server and verify

```bash
# Terminal 1 — start the server with debug + verbose logs
nats-server -DV

# Terminal 2 — subscribe
nats sub greetings

# Terminal 3 — publish
nats pub greetings "hello, world"
```

The subscriber prints the message immediately. If it does not, confirm the server is listening on `127.0.0.1:4222` and that no other process is bound to that port.

## Enable JetStream (persistence)

JetStream adds streams, durable consumers, Key-Value, and Object Store on top of core NATS:

```bash
nats-server -js -DV
```

Create a stream and publish to it:

```bash
nats stream add ORDERS --subjects "orders.>"
nats pub orders.new '{"id":1}'
nats stream info ORDERS
```

## Next steps

- Configuration reference: https://docs.nats.io/running-a-nats-service/configuration
- Clustering and supercluster: https://docs.nats.io/running-a-nats-service/configuration/clustering
- Move to managed: see the `synadia-cloud-onboarding` skill.

## Canonical documentation

- NATS installation: https://docs.nats.io/running-a-nats-service/introduction/installation
- `nats` CLI repository: https://github.com/nats-io/natscli
- NATS server repository: https://github.com/nats-io/nats-server
- Synadia (maintainers of NATS): https://www.synadia.com

## What this skill does not cover

- Production hardening: TLS, authentication, accounts, monitoring.
- JetStream design patterns and consumer semantics.
- Synadia Cloud and Synadia Platform — see related skills and product pages.
