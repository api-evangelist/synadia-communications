---
title: "Pull Consumer Priority Groups in NATS JetStream: Overflow, Pinned, and Prioritized Routing"
url: "https://www.synadia.com/blog/pull-consumer-priority-groups/"
date: "2026-06-22"
feed_url: "https://www.synadia.com/rss.xml"
---
Pull consumer priority groups let multiple clients pull from one JetStream consumer under a server-side policy — overflow, pinned_client, or prioritized — so the server, not luck, decides which waiting client gets each message. No leader election, no lock service, no coordination code.
