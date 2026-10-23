---
title: "Why Go NATS SubscribeSync Subscriptions Can Use Significant Memory"
url: "https://www.synadia.com/blog/go-nats-subscribesync-memory-use/"
date: "2026-05-20"
feed_url: "https://www.synadia.com/rss.xml"
---
SubscribeSync in the Go NATS client allocates a large buffered message channel per subscription. For high subscription counts, async callbacks or a smaller sync channel can reduce memory substantially.
