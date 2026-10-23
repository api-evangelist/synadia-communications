---
title: "How to Fetch a Small NATS KV Key Hierarchy Without a Watcher"
url: "https://www.synadia.com/blog/fetch-nats-kv-key-hierarchy-without-watcher/"
date: "2026-05-28"
feed_url: "https://www.synadia.com/rss.xml"
---
For one-off NATS KV prefix reads, use JetStream batched Direct Get against the KV backing stream instead of creating a watcher.
