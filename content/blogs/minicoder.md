---
title: "`mini-coder`: small models for agentic SWE research"
linkTitle: "mini-coder: small models for research on SWE agents"
date: 2025-09-30
url: /blogs/minicoder.html
author: Ricardo Olmedo
affiliation: Max Planck Institute for Intelligent Systems, Tübingen
lede: "Two distilled models (1.7B & 4B) + 400k training trajectories from Qwen 3 Coder. Download the models & dataset [here](https://huggingface.co/collections/ricdomolm/mini-coder-68dbc8198dd63ff63ed8ef7d)."
---

**SWE-bench Verified (Bash only)**
{.caption}

|                             | pass@1 | pass@100 |
| :-------------------------- | -----: | -------: |
| Qwen 3 Coder 30B-A3B        |   33.2 |     67.4 |
| **`mini-coder-4b`**         |   26.8 |     60.2 |
| gpt-oss-120b                |   26.0 |        - |
| **`mini-coder-1.7b`**       |   18.6 |     50.4 |
| SWE-agent-LM 7B             |   15.2 |        - |
| Qwen 3 4B Instruct 2507     |    4.0 |     25.1 |

Small models play a crucial role in today's research ecosystem. They enable a larger pool of researchers to contribute to the field, thereby accelerating scientific progress. Unfortunately, the entry barrier for agentic SWE research remains high: performant open-weight models are in the 30B-parameter range. To make matters worse, SWE agentic tasks require long, multi-turn interactions, further increasing GPU memory demands. As a result, research on post-training SWE agents generally requires multi-GPU—and often multi-node—setups.

To lower this entry barrier, we trained [`mini-coder`](https://huggingface.co/collections/ricdomolm/mini-coder-68dbc8198dd63ff63ed8ef7d): two small but performant agentic SWE models. We follow a straightforward training recipe: distillation from a larger, more capable model. We distill from [Qwen 3 Coder 30B](https://qwenlm.github.io/blog/qwen3-coder/), which strikes a good balance between performance and inference cost. Using the [SWE-smith](https://arxiv.org/abs/2504.21798) dataset of GitHub issues, together with the lightweight [mini-swe-agent](https://mini-swe-agent.com/latest/) scaffolding, we generated 400k training trajectories (~5.5B tokens). We then fine-tuned Qwen&nbsp;3&nbsp;1.7B and Qwen&nbsp;3&nbsp;4B Instruct on these trajectories.

The `mini-coder` models deliver SOTA performance on [SWE-Bench Verified Bash-only](https://www.swebench.com/) at their size. Remarkably, `mini-coder-4b` matches the performance of the much larger gpt-oss-120b, while `mini-coder-4b` outperforms SWE-Agent-LM 7B. The two models also achieve much higher pass@k than their corresponding base models. This indicates that the `mini-coder` models are strong candidates for RL fine-tuning, since pass@k reflects the fraction of problems from which effective supervision can be derived.

Unlike existing agentic SWE models, the `mini-coder` models can be post-trained on a single 80GB GPU—or smaller. They work seamlessly with mini-swe-agent, a lightweight, scalable, and developer-friendly agentic framework well-suited for RL fine-tuning. And because they are dense rather than MoE models, they benefit from a more mature fine-tuning ecosystem. Additionally, researchers can incorporate our [dataset](https://huggingface.co/datasets/ricdomolm/mini-coder-trajs-400k) of 400k training trajectories in their post-training recipes. All in all, we hope that the `mini-coder` models will accelerate progress in agentic SWE research.
