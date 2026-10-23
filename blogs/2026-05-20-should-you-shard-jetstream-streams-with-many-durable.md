---
title: "Should You Shard JetStream Streams with Many Durable Consumers?"
url: "https://www.synadia.com/blog/jetstream-sharding-many-durable-consumers/"
date: "2026-05-20"
feed_url: "https://www.synadia.com/rss.xml"
---
A single JetStream stream with many durable consumers can work, but it will not scale linearly forever. Sharding is a design tradeoff driven by CPU, I/O, lag, and consumer behavior.
