---
title: "From Noise to Diversity: Random Embedding Injection in LLM Reasoning"
authors: "Heejun Kim&#42;, [**Seungpil Lee&#42;**](iamseungpil.github.io), Jewon Yeom, Jaewon Sok, Seonghyeon Park, Jeongjae Park, Taesup Kim†, [Sundong Kim†](https://sundong.kim/)"
collection: publications
pub_type: preprint
permalink: /publication/2026-05-from-noise-to-diversity
excerpt: 'We study Random Soft Prompts — random embedding vectors appended to the input that, despite carrying no learned content, match optimized soft prompts on math reasoning. The gain comes from how the never-seen-before random position flattens early-token distributions and branches reasoning trajectories, lifting Pass@N at inference and translating into practical DAPO training improvements.'
date: 2026-05-12
venue: 'arXiv preprint'
paperurl: 'https://arxiv.org/abs/2605.11936'
codeurl: 'https://github.com/heejunkim00/RSP'
teaser: images/rsp26.png
bibtex_content: |
  @article{RSP_arXiv2026,
    title = {{From Noise to Diversity: Random Embedding Injection in LLM Reasoning}},
    author = {Kim, Heejun and Lee, Seungpil and Yeom, Jewon and Sok, Jaewon and Park, Seonghyeon and Park, Jeongjae and Kim, Taesup and Kim, Sundong},
    journal = {arXiv preprint arXiv:2605.11936},
    year = {2026},
  }
---

We isolate the simplest form of soft prompt — Random Soft Prompts (RSPs) — training-free vectors freshly resampled from a Gaussian fitted to the embedding table. RSPs reach accuracy comparable to optimized soft prompts on math reasoning benchmarks, suggesting the gain comes from the act of injection rather than learned content. The mechanism unfolds in two stages: attention absorbing a never-seen-before random position flattens early-token distributions and branches reasoning trajectories; later generation dilutes this influence so the response commits. At inference, RSPs lift early-stage token diversity and widen Pass@N; the same effect carries into DAPO training with practical gains.

[Download paper here](https://arxiv.org/abs/2605.11936)
