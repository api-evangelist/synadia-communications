---
title: "JetStream Scheduled Messages and Interest Retention"
url: "https://www.synadia.com/blog/jetstream-scheduled-messages-interest-retention/"
date: "2026-05-22"
feed_url: "https://www.synadia.com/rss.xml"
---
Scheduled messages can be used with JetStream Interest retention, but the retention policy still applies while the message is scheduled. In many cases, a Limits-based stream with TTL or MaxAge is the safer design.
