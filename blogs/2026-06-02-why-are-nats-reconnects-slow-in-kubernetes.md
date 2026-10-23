---
title: "Why are NATS reconnects slow in Kubernetes?"
url: "https://www.synadia.com/blog/troubleshooting-nats-reconnect-delays-kubernetes/"
date: "2026-06-02"
feed_url: "https://www.synadia.com/rss.xml"
---
NATS reconnect delays in Kubernetes usually come from stale TCP detection, DNS, or unreachable advertised URLs—not reconnect wait.
