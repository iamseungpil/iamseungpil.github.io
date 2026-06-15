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

A large language model can pass the bar exam, write pages of fluent prose, and explain ideas most people would struggle with, and then miss a simple visual pattern a child catches in seconds. That gap is the interesting part. It says these systems think in ways that overlap with us and break from us, and I want to map exactly where.

So I work in two directions at once. I read a model's behavior and its internals in the language of cognitive science and psychology, to make sense of the system. Then I carry what that turns up, about reasoning, error, and bias, back into how the next system gets built. Cognitive science gives me sharper ways to probe a model; the places a model succeeds or breaks hand me a new angle on human thinking that was hard to reach before. The two keep feeding each other.

</div>

## Research Program: Three Questions

My work so far has followed three questions about machine thinking, each one growing out of the last. They run from how a model reasons, to what it actually understands, to why it sometimes works against its own interest.

### Question 1: How Does LLM Reasoning Differ from Human Reasoning?

To get a handle on the difference, I borrowed the Language of Thought Hypothesis (LOTH) from cognitive science. It says human reasoning rests on three properties: logical coherence, compositionality, and productivity.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q1-reasoning.png" alt="Human reasoning vs LLM reasoning comparison" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>The Language of Thought lens: three properties of human reasoning (left) against how LLMs hold up on each (right).</em></p>
</div>

Then I pointed that lens at the Abstraction and Reasoning Corpus (ARC), François Chollet's visual reasoning benchmark. The models turned out to be surprisingly brittle. Show the same rule under a different surface pattern, and 57.8% of the time the model treated it as a brand-new problem. When a task needed several transformations combined, even the best model topped out at 29%. The takeaway was hard to miss: these models match surface patterns instead of composing rules the way people do. This work appeared in <strong>ACM Transactions on Intelligent Systems and Technology (TIST, 2024)</strong>.

### Question 2: What Do LLMs Understand and What Don't They?

That first study left me with a method problem. When a model gets something wrong, where exactly did its understanding break? Standard generation-based tests don't really say. You see a wrong answer and the cause stays hidden.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q2-mclarc.png" alt="MC-LARC: The benefit of multiple-choice for pinpointing errors" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Generation hides where a model goes wrong; a contrastive multiple-choice format brings the specific mistake into view.</em></p>
</div>

So I built MC-LARC. It turns analogical reasoning problems into multiple choice, where every wrong option is written to catch a specific kind of mistake. People scored about 90% on it; the best models, about 60%. And the format mattered as much as the questions. How you test a model shapes what you are even able to learn about it. This work was published at <strong>EMNLP Findings 2024</strong>.

### Question 3: Why Do AI Systems Exhibit Irrational Behavior?

The first two questions were about gaps in reasoning. The third one caught me off guard. Models don't just reason badly sometimes; they can act *irrationally*, in the same shapes as well-known human biases.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q3-gambling.png" alt="LLM gambling addiction research questions" style="max-width: 80%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Testing whether a model can drift into gambling-addiction-like behavior.</em></p>
</div>

I looked at whether a model could slide into something like gambling addiction. It could. In a slot-machine setup, the models showed the illusion of control, chased their losses, and fell for the gambler's fallacy, and this was not just parroting the training data. The gap between fixed and variable betting ran about 20%, steady enough that the bias looks built in rather than random. Using Sparse Autoencoders (SAE), I could even find the internal features that lit up when a model made these calls.

## Methodology

<div style="background-color: #f8f9fa; border-left: 4px solid #3498db; border-radius: 8px; padding: 20px; margin: 1.5em 0;">

All three projects work the same way. I take a frame from cognitive science, point it at a model, and watch where the model lines up with human thinking and where it pulls apart. That two-way move, cognitive science to read AI and AI to read cognition, is really the whole of how I work.

</div>

## Future Directions

Those three questions were one question wearing different clothes: what is it to think? Each time I came at it from the same three angles, the **benchmark** that measures a skill, the **training** that shapes it, and the **architecture** that holds it. Now I want to aim those same three tools at a harder question: what would it take for a model to be aware of its own thinking?

I don't mean an inner spark of experience. I mean **metacognition**, the ordinary work a mind does keeping tabs on itself. Sensing when its own answer is shaky. Checking that answer against what it actually represents inside. Catching the spot where the reasoning slipped. Carrying its failures forward instead of forgetting them. Holding a rough self-model of how it tends to think.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-future-consciousness.png" alt="From thinking to self-consciousness: the same benchmark, training, and architecture approach, aimed at machine metacognition" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>The same three tools (benchmark, training, architecture), aimed from thinking toward self-consciousness.</em></p>
</div>

Why think this is buildable rather than mystical hand-waving? Because of a deflationary reading I borrow from Daniel Dennett. On his Multiple Drafts Model there is no single inner stage where consciousness happens. The self that seems to sit behind our thoughts is really a **"center of narrative gravity,"** a story a system keeps telling about itself. If that is what selfhood amounts to, then a habit of self-description is something you can actually measure, train, and design for. That is the bet behind the three directions below. All of them are early, and a few are honestly still sketches.

- **A benchmark for holding onto who you are.** Self-reports are cheap. A model will tell you it is careful and consistent whether or not it is. So I would rather watch behavior. Can a model work out its own operating principles, its values and priorities, from how it has acted, and stick to them when the setting shifts and the pressure climbs? Stay consistent across very different situations and that consistency is the evidence. Fall apart, and the self-model was never really there.
- **Training a model to check its own work.** Most correction comes from outside: a reward, a label, a human saying "wrong." I want the checking to move inside, so a model lays out its own doubts and fixes as part of reasoning, not after the fact. Getting a model to stop being so sure of itself is the easy half. Getting it to do that without giving up accuracy is the hard half, and the part I don't have yet.
- **Building the self-monitoring in, not bolting it on.** A model that revises itself needs somewhere to keep what it learns mid-task and some way to go back over an answer before it commits. I'm drawn to designs that update memory while the model is still thinking and let it pass over its own output again in place. Under all three directions sits the same tool, mechanistic interpretability: reading the internal circuits to check whether self-monitoring is really happening, or whether the model just learned to say it is.

None of this stays inside the machine, and that is why it matters to me. The arrows run both ways. Going from AI to people, a model that watches its own thinking becomes a kind of lab bench for the human questions I care about: how we reason, how addiction takes hold, how memory and self-awareness work. Over a longer horizon I would like that to reach into medicine, counseling, and education. Going the other way, I want the work out in the open: evaluation protocols, data, and code that anyone can rerun and pick apart, audits that catch risks to vulnerable people early, while a harm like gambling or a cognitive bias is still forming inside the model, and Korean-language resources for the parts of my own context that English-first benchmarks quietly skip. A model that can check itself knows its own problem better, and can stop or back up when what it says drifts from what it represents. Memory is what turned a reasoning system into an agent. A steady habit of self-description might be what turns an agent into one that knows, even a little, that it is thinking at all.

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
