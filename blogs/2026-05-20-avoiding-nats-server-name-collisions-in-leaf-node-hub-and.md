---
title: "Avoiding NATS Server Name Collisions in Leaf Node Hub-and-Spoke Topologies"
url: "https://www.synadia.com/blog/avoid-nats-server-name-collisions-leafnodes/"
date: "2026-05-20"
feed_url: "https://www.synadia.com/rss.xml"
---
When multiple Kubernetes NATS clusters connect to a shared hub, default pod-based server names can collide. Plan globally unique server names, cluster names, and JetStream domains before joining the mesh.
