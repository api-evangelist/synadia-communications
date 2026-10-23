---
title: "How to Map JetStream Subjects with External Metadata"
url: "https://www.synadia.com/blog/map-jetstream-subjects-device-group/"
date: "2026-05-20"
feed_url: "https://www.synadia.com/rss.xml"
---
When JetStream subject routing depends on external metadata, a custom mapper is usually the right boundary. Partition by device ID to preserve per-device order while scaling mapper workers.
