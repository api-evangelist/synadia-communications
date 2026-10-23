---
title: "Can JetStream Pull Consumers Fetch Strictly Ordered Batches?"
url: "https://www.synadia.com/blog/jetstream-pull-consumer-ordered-batches/"
date: "2026-05-20"
feed_url: "https://www.synadia.com/rss.xml"
---
JetStream preserves ordered delivery for a consumer, but a pull batch is not an atomic reservation when multiple clients fetch from the same consumer.
