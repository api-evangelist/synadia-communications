---
title: "Scaling JetStream Last-Per-Subject Streams with Many Subjects"
url: "https://www.synadia.com/blog/scaling-jetstream-last-per-subject-streams/"
date: "2026-05-22"
feed_url: "https://www.synadia.com/rss.xml"
---
JetStream streams that retain the last message per subject can accumulate many interior deletes under high update churn. For large or hot subject sets, file-backed streams or separating the hot log from the snapshot state are often better fits.
