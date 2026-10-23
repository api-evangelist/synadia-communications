---
title: "Preventing Duplicate Publishes While a Matching Message Exists in JetStream"
url: "https://www.synadia.com/blog/prevent-existing-duplicate-messages-jetstream/"
date: "2026-05-22"
feed_url: "https://www.synadia.com/rss.xml"
---
Nats-Msg-Id deduplicates within a time window. To reject a publish while a matching message still exists, make the subject the identity and use a publish expectation.
