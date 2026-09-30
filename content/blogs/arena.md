---
title: "How to Fix the Chatbot Arena? Release All Data"
linkTitle: "How to Fix the LMArena? Release All Data"
date: 2025-05-02
url: /blogs/arena.html
author: Ricardo Dominguez-Olmedo
lede: "Releasing all Arena data would make LMArena a fairer leaderboard. It would also force us to reflect on whether we actually care who is at the top."
---

The Chatbot Arena leaderboard has recently become the center of controversy. [Researchers have shown](https://arxiv.org/abs/2504.20879) that some model providers have been able to collect much more Arena data than others. They argue that this asymmetry in data access gives certain providers an unfair competitive advantage.

[In response](https://x.com/lmarena_ai/status/1917492084359192890), the Arena organizers argue that access to Arena data is a positive thing —it helps providers optimize for millions of people's preferences. They further claim that if one provider collects more data than another, that's not necessarily unfair. After all, Provider B could, in principle, have employed the same data collection strategies as Provider A.

At the heart of this debate lies a subtle but critical issue: training on the test task. Unlike training on the test set—which is clearly problematic—training on the test task can be a legitimate attempt to improve model performance. If the goal is to better align models with human preferences, why not train on as much preference data as possible? At the same time, if a handful of providers have access to vastly more Arena data than everyone else, how can others hope to compete?

The researchers proposed to address such concerns by limiting how much Arena data any single provider can collect. But this doesn't necessarily level the playing field. Providers who already collected large amounts of data would retain their advantages. Those with more models on the Arena could still collect fresh data at higher rates. And well-resourced industry labs can obtain vast amounts of additional human preference data by other means. So, what can we do instead?

**LMArena should release all Arena data.** Doing so would ensure that every future submission has access to the same amount of Arena data — all of it. Given its scale, additional preference data that well-resourced labs may be able to collect would have diminishing value. The broader research community would benefit, since large real-world human preference datasets are scarce.

This approach aligns with the conclusions of our recent paper on "[training on the test task](https://arxiv.org/abs/2407.07890)". The best way to fight training on the test task is to embrace it. Unfairness in benchmarking arises only if some providers can train on the test task much more than others. By releasing all Arena data, we can hope to restore fair rankings by ensuring everyone can benefit as much as possible from this valuable community resource.

Embracing training on the test task has an additional benefit. Putting more pressure on a benchmark forces us to reflect on how much we should care about said benchmark. This intuition often manifests itself through the specter of "overfitting". But the Arena tests models on fresh data. As the organizers put it, "If a model does well on LMArena, it means that our community likes it!" And that's exactly what it means. Whether we choose to read too much into it is on us.
