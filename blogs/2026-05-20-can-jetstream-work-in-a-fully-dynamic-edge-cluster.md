---
title: "Can JetStream Work in a Fully Dynamic Edge Cluster?"
url: "https://www.synadia.com/blog/jetstream-dynamic-edge-clusters-quorum/"
date: "2026-05-20"
feed_url: "https://www.synadia.com/rss.xml"
---
JetStream is a good fit when you can give its RAFT groups stable membership. For highly dynamic edge nodes, consider separating Core NATS routing from local JetStream persistence.
