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

One idea sits under everything I do: <strong>AI is a mirror for the human mind.</strong>

A large language model can pass the bar exam, write pages of fluent prose, and explain ideas most people would struggle with, and then miss a simple visual pattern a child catches in seconds. That gap is the interesting part. It says these systems think in ways that overlap with us and break from us, and I want to map where.

That splits my work in two directions at once. I read a model's behavior and its internals in the language of cognitive science and psychology, to make sense of the system. Then I carry what that turns up, about reasoning, error, and bias, back into how the next system gets built. Cognitive science gives me sharper ways to probe a model; the places a model succeeds or breaks hand me a new angle on human thinking that was hard to reach before. The two keep feeding each other.

</div>

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-mirror.png" alt="AI as a mirror: cognitive science reads the model, and the insight returns to model design" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>The whole program in one loop: read the model with cognitive science, and return the insight to model design.</em></p>
</div>

## Research Program: Three Questions

My work so far has followed three questions about machine thinking, each one growing out of the last. They run from how a model reasons, to what it actually understands, to why it sometimes works against its own interest.

### Question 1: How Does LLM Reasoning Differ from Human Reasoning?

To get a handle on the difference, I borrowed the Language of Thought Hypothesis (LOTH) from cognitive science. It says human reasoning rests on three properties: logical coherence, compositionality, and productivity.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q1-reasoning.png" alt="Human reasoning vs LLM reasoning comparison" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>The Language of Thought lens: three properties of human reasoning (left) against how LLMs hold up on each (right).</em></p>
</div>

Then I pointed that lens at the Abstraction and Reasoning Corpus (ARC), François Chollet's visual reasoning benchmark. The models turned out to be surprisingly brittle. Show the same rule under a different surface pattern, and 57.8% of the time the model treated it as a brand-new problem. When a task needed several transformations combined, even the best model topped out at 29%. The takeaway was hard to miss: these models match surface patterns instead of composing rules the way people do. This work appeared in <strong>ACM Transactions on Intelligent Systems and Technology (TIST, 2025)</strong>.

### Question 2: What Do LLMs Understand and What Don't They?

That first study left me with a method problem. When a model gets something wrong, where exactly did its understanding break? Standard generation-based tests don't really say. You see a wrong answer and the cause stays hidden.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q2-mclarc.png" alt="MC-LARC: The benefit of multiple-choice for pinpointing errors" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Generation hides where a model goes wrong; a contrastive multiple-choice format brings the specific mistake into view.</em></p>
</div>

So I built MC-LARC. It turns analogical reasoning problems into multiple choice, where every wrong option is written to catch a specific kind of mistake. People scored about 90% on it; the best models, about 60%. And the format mattered as much as the questions. How you test a model shapes what you can learn about it at all. This work was published at <strong>EMNLP Findings 2024</strong>.

### Question 3: Why Do AI Systems Exhibit Irrational Behavior?

The first two questions were about gaps in reasoning. The third one caught me off guard. Sometimes the problem isn't bad reasoning at all. Models can act *irrationally*, in the same shapes as well-known human biases.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q3-gambling.png" alt="LLM gambling addiction research questions" style="max-width: 80%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Testing whether a model can drift into gambling-addiction-like behavior.</em></p>
</div>

I looked at whether a model could slide into something like gambling addiction. It could. In a slot-machine setup, the models showed the illusion of control, chased their losses, and fell for the gambler's fallacy, and this was not just parroting the training data. The gap between fixed and variable betting held near 20% across runs — steady, not a fluke. Using Sparse Autoencoders (SAE), I could even find the internal features that lit up when a model made these calls.

## What the Three Questions Converged On

<div style="background-color: #f8f9fa; border-left: 4px solid #3498db; border-radius: 8px; padding: 20px; margin: 1.5em 0;">

Lay the three diagnoses side by side and they say one thing. A model mistakes a familiar-looking rule for the one it memorized, and picks its answer from surface cues instead of real understanding. Its biases, meanwhile, are wired into the circuits — not just the outputs. In every case the model is being <strong>pulled by its priors into a familiar pit</strong> — and it never notices, because nothing inside it is watching. I read the root of all three failures as the same missing piece: <strong>metacognition</strong>. A model that cannot inspect its own generation cannot resist the pull. More training data can move where the pit sits; it never teaches the model to feel itself sliding in.

</div>

## Future Directions

That diagnosis sets the agenda. I am exploring the fix at three points where a system can intervene on itself, and the three prescriptions converge on one capability.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-pitfall-three.png" alt="One disease, three prescriptions: a model without metacognition is pulled into familiar pitfalls; interventions at inference, training, and the agent loop converge on metacognition" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>One disease, three prescriptions — and where they converge.</em></p>
</div>

- **At inference: inject diversity before the path hardens.** In recent work (co-first author, spotlighted at an ICML workshop) we showed that injecting fresh random vectors into a model's input — with zero training — opens up early token choices that temperature sampling almost never surfaces, so repeated attempts explore genuinely different reasoning paths. The next step is to let the model's own uncertainty signals decide *when* to branch, turning indiscriminate diversity into selective exploration.
- **In training: reward the self-checks that hold up.** Ask a model to double-check itself and it learns to *perform* checking without fixing anything. I am building training signals that measure whether a self-check really moved the model's belief toward the right answer, and pay reward only for that movement. Early experiments show it curbs overconfidence, and the gains cluster on the hardest problems — where the pull of priors is strongest. The harder half, still open, is teaching the model *when* to check.
- **In the agent loop: accumulate only verified knowledge.** When priors are the contamination, an external harness can do the watching: treat every dead-end as a signal, mine candidate skills from it, and let only the candidates that survive real execution enter the library. The harness becomes a growing cognitive structure rather than a crutch — and the next question is whether skills verified in one world transfer to another.

The three prescriptions meet in a model that can **watch its own thinking**: notice when its answer and its internal representations disagree, and stop or repair itself. That is metacognition — the ordinary work a mind does keeping tabs on itself — and it is where this program points next: catching the moment its answer and its own internals disagree, and remembering that failure the next time around. Under all three prescriptions sits one shared tool — mechanistic interpretability — reading the internal circuits to tell whether the model is really monitoring itself or has only learned to say it is.

This could sound like mystical hand-waving. It isn't, and the reason is a deflationary reading I borrow from Daniel Dennett. On his Multiple Drafts Model there is no single inner stage where consciousness happens. The self that seems to sit behind our thoughts is really a **"center of narrative gravity,"** a story a system keeps telling about itself. Read that way, the self-narrative — not selfhood as such — is something I can measure, train, and design for, and self-consciousness becomes an empirical target rather than a mystery. The question that began as metacognition quietly grows into it.

None of this stays inside the machine, and that is why it matters to me. The arrows run both ways. Going from AI to people, a model that watches its own thinking becomes a kind of lab bench for the human questions I care about: how we reason, and how something like addiction takes hold in a mind. Over a longer horizon I would like that to reach into medicine, counseling, and education. Going the other way, I want the work out in the open: evaluation protocols, data, and code that anyone can rerun and pick apart, audits that catch risks to vulnerable people early, while a harm like gambling or a cognitive bias is still forming inside the model, and Korean-language resources for the parts of my own context that English-first benchmarks quietly skip. A model that can check itself knows its own weak spots better. Memory is what turned a reasoning system into an agent. A steady habit of self-description might be what turns an agent into one that knows, even a little, that it is thinking at all.

---

## Related Publications

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5em; margin-top: 1.5em;">

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2025-03-18-TIST/" style="color: #2c3e50; text-decoration: none;">Reasoning Abilities of Large Language Models: In-Depth Analysis on the Abstraction and Reasoning Corpus</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">ACM TIST, 2025</p>
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

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2026-05-from-noise-to-diversity/" style="color: #2c3e50; text-decoration: none;">From Noise to Diversity: Random Embedding Injection in LLM Reasoning</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">ICML MI Workshop (Spotlight), 2026</p>
  <p style="font-size: 0.85em; color: #555;">Training-free random embedding injection widens early-token diversity and Pass@N — the inference-time prescription.</p>
</div>

</div>
