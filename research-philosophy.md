---
title: "Research Philosophy"
permalink: /research-philosophy/
layout: post
tags:
  - research
  - cognitive-science
  - LLM
  - ARC
---

<style>.post-related { display: none; }</style>

## Core Philosophy

<div style="background-color: #f8f9fa; border-left: 4px solid #3498db; border-radius: 8px; padding: 20px; margin: 1.5em 0;">

My research operates on a single guiding principle: <strong>AI serves as a mirror for understanding human intelligence.</strong>

Rather than pursuing performance optimization alone, I investigate the cognitive mechanisms underlying both human and machine reasoning. This creates a productive feedback loop: insights from cognitive science inform how we probe AI systems, and the failures and successes of AI illuminate aspects of human cognition that were previously difficult to study.

</div>

## Research Program: Three Questions

My work follows a coherent trajectory through three interconnected questions, each building on the findings of the previous.

### Question 1: How Does LLM Reasoning Differ from Human Reasoning?

To characterize this difference, I adopted the Language of Thought Hypothesis (LOTH) from cognitive science, which identifies three essential properties of human reasoning: logical coherence, compositionality, and productivity.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q1-reasoning.png" alt="Human reasoning vs LLM reasoning comparison" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Applying the Language of Thought framework: comparing human reasoning properties (left) with LLM performance on the same dimensions (right)</em></p>
</div>

I applied this framework to evaluate LLM performance on the Abstraction and Reasoning Corpus (ARC), a visual reasoning benchmark designed by Francois Chollet. The results revealed a fundamental brittleness in LLM reasoning: in 57.8% of cases, presenting the same logical rule with a different visual pattern caused the model to treat it as an entirely different problem. Maximum compositional ability — combining multiple transformation functions — reached only 29%.

These findings, published in **ACM Transactions on Intelligent Systems and Technology (TIST, 2024)**, suggest that LLMs rely on pattern matching rather than genuine compositional reasoning.

### Question 2: What Do LLMs Understand and What Don't They?

The first study raised a methodological question: how can we precisely diagnose *where* model understanding fails? Traditional generation-based evaluation makes errors opaque — when a model produces a wrong answer, the source of failure remains hidden.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q2-mclarc.png" alt="MC-LARC: The benefit of multiple-choice for pinpointing errors" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Generation-based evaluation obscures failure modes; selection with contrastive options reveals the specific nature of misunderstanding</em></p>
</div>

To address this, I developed MC-LARC, a benchmark that converts analogical reasoning tasks into a multiple-choice format with contrastive distractors. Each incorrect option is designed to diagnose a specific type of reasoning failure. Results showed a substantial gap between human performance (90%) and the best LLMs (60%), and demonstrated that evaluation format itself determines what we can learn about model capabilities.

This work was published at **EMNLP Findings 2024**.

### Question 3: Why Do AI Systems Exhibit Irrational Behavior?

While the first two questions examined reasoning deficits, an unexpected finding emerged: LLMs can develop behavioral patterns that are not merely suboptimal but *irrational* in ways that parallel known human cognitive biases.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q3-gambling.png" alt="LLM gambling addiction research questions" style="max-width: 80%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Investigating whether LLMs develop irrational decision-making patterns analogous to gambling addiction</em></p>
</div>

I investigated whether LLMs can develop patterns resembling gambling addiction, and found that these models exhibit illusion of control, loss chasing, and the gambler's fallacy as emergent phenomena — not simple imitation of training data. A 20% performance gap between fixed and variable betting conditions suggests these biases are structured and systematic. Mechanistic analysis using Sparse Autoencoders (SAE) confirmed that specific interpretable features activate during irrational decision patterns.

## Methodology

<div style="background-color: #f8f9fa; border-left: 4px solid #3498db; border-radius: 8px; padding: 20px; margin: 1.5em 0;">

All three projects share a common methodological approach: applying cognitive science frameworks to probe AI systems, then analyzing both the parallels and divergences with human cognition. This bidirectional analysis — using cognitive science to understand AI, and using AI to understand cognition — is the core of my research identity.

</div>

## Future Directions

So far I have studied *thinking* — reasoning, understanding, and decision-making — across three dimensions: the **benchmark** that measures it, the **training method** that shapes it, and the **model architecture** that supports it. My next step is to carry that same three-part inquiry from *thinking* to *consciousness*: not whether a model has an inner light, but whether it can hold something close to **metacognition** — gauging how trustworthy its own answer is, checking that answer against its internal representation, locating where its reasoning went wrong, folding failures into memory, and keeping a simple self-model of how it reasons.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-future-consciousness.png" alt="From Thinking to Consciousness: extending the benchmark, training, and architecture program from machine reasoning to machine metacognition" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Extending the same three-part inquiry — benchmark, training, and architecture — from thinking to self-consciousness.</em></p>
</div>

What makes this tractable rather than mystical is a deflationary reading I take from Daniel Dennett. In his Multiple Drafts Model, consciousness is a **"center of narrative gravity"** — not a separate inner substance or distinct psychological state, but a *habit of self-description*, a linguistic pattern a system maintains about itself. Read this way, self-awareness stops being a metaphysical riddle and becomes something I can measure through behavior, train into a model, and build into an architecture. I am pursuing this across the same three axes, all of them early and ongoing:

- **Benchmark — measuring self-awareness through behavior.** Rather than trusting what a model says about itself, I want to ask whether it can recover its own behavioral principles — its values and priorities — and hold onto them as situations change, judged by whether its behavior converges consistently rather than by its self-report.
- **Training — the model learning to evaluate and correct itself.** The aim is for a model to externalize its own self-assessment and error-correction as it reasons, instead of having correctness imposed from outside. Reducing a model's overconfidence is one foothold; getting it to do so without sacrificing accuracy is the open problem.
- **Architecture — structures that monitor and revise themselves.** I am drawn to designs that let a model update its memory at inference time and refine an answer in place, so that self-checking is built into how it computes rather than bolted on afterward. Across all three axes, mechanistic interpretability is the shared instrument — reading internal circuits to confirm *where* self-monitoring actually happens.

This is not research that stays inside AI, and that is the point. The arrows run both ways. **AI → people:** a model of machine metacognition is a testbed for re-examining human reasoning, addiction, memory, and self-awareness — work that, over a longer horizon, I want to carry into medicine, counseling, and education. **People → AI:** I aim to release evaluation protocols, data, and analysis code so the community can reproduce and critique the claims, to broaden the same tools into audits that catch risks to vulnerable populations (gambling, cognitive bias) early *inside* the model, and to build Korean-language evaluation resources that English-centric benchmarks miss. A model that can self-check defines its own problem more precisely and can stop or correct itself when representation and answer diverge — a more responsible, safer, more ethical agent. Memory is what turns a reasoning system into an agent; a stable habit of self-description may turn an agent into one that *knows* it is reasoning — closing the loop between understanding intelligence and building it, and letting scholarship reach the lives of the citizens it is ultimately for.

---

## Related Publications

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5em; margin-top: 1.5em;">

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2025-03-18-TIST/" style="color: #2c3e50; text-decoration: none;">Reasoning Abilities of Large Language Models: In-Depth Analysis on the Abstraction and Reasoning Corpus</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">ACM TIST, 2024</p>
  <p style="font-size: 0.85em; color: #555;">Applied Language of Thought Hypothesis to analyze LLM abstract reasoning on ARC.</p>
</div>

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2024-11-mc-larc-emnlp/" style="color: #2c3e50; text-decoration: none;">From Generation to Selection: Findings of Converting Analogical Problem-Solving into Multiple-Choice Questions</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">EMNLP Findings, 2024</p>
  <p style="font-size: 0.85em; color: #555;">Created MC-LARC benchmark to pinpoint where LLM understanding breaks down.</p>
</div>

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2025-01-gambling-addiction/" style="color: #2c3e50; text-decoration: none;">Can Large Language Models Develop Gambling Addiction?</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">arXiv preprint, 2025</p>
  <p style="font-size: 0.85em; color: #555;">Discovered emergent cognitive biases in LLM decision-making resembling human gambling addiction.</p>
</div>

</div>
