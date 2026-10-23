---
title: "Replace Redis with NATS: Atomic Counters and Microsecond Key-Value"
url: "https://www.synadia.com/blog/replace-redis-with-nats-atomic-counters-and-microsecond-key-value/"
date: "2026-07-01"
feed_url: "https://www.synadia.com/rss.xml"
---
NATS 2.12 added server-side increment-in-place counters, and the JetStream KV store answers hot gets in microseconds. If counters and key-value are why you run Redis, you can likely delete one system.
