---
title: "Handling JetStream WorkQueue Messages with No Consumer"
url: "https://www.synadia.com/blog/jetstream-workqueue-no-consumer-fallback/"
date: "2026-05-22"
feed_url: "https://www.synadia.com/rss.xml"
---
JetStream does not automatically move workqueue messages to a fallback consumer when no matching consumer exists. Choose retention semantics carefully, and add explicit cleanup or dead-letter handling where needed.
