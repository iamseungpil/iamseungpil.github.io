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

<strong>"From humans to AI, and from AI back to humans." That is my research motto.</strong>

If I implement humanlike intelligence in AI and test it, I can understand our own intelligence better, and that understanding in turn makes AI more beneficial to people. Over my past research, I have read and evaluated the behavior of models using concepts from cognitive science and psychology, and tried to improve AI through that. From here on too, I want to do research to understand the nature of intelligence better under the same philosophy. Below, I explain why I came to hold this philosophy, what I found in my earlier research, and where my research is heading.

</div>

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-mirror.png" alt="AI as a mirror: cognitive science reads the model, and the insight returns to model design" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>The whole program in one loop: read the model with cognitive science, and return the insight to model design.</em></p>
</div>

## Why This Philosophy

I have always wondered how intelligence works, and from there I also came to wonder how the consciousness and self of the "I" who uses that intelligence work. Along the way, I came across a few books, by Dennett, Hofstadter, Kim, and others, that left a deep mark on me.

I think consciousness and the self are not a soul or spirit sitting separately inside the body, but a special kind of thought pattern (a way in which thinking is put together). The philosopher Daniel Dennett saw the self not as a separate entity but as a story a system keeps telling about itself (a self-description). Douglas Hofstadter described the "I" as a pattern that arises from a loop of symbols in the brain that point back at themselves.

I think thought patterns can be tested through behavior, which lets us compare models and people. This is possible if thought patterns show themselves in behavior, and that is my own assumption. Alan Turing replaced the vague question of whether machines think with a test: can a machine converse in a way that cannot be told apart from a person? That opened a path to testing intelligence through behavior. Jaegwon Kim held that a mind defined by what it does, as beliefs and desires are, can be explained by the function that does it. That is as far as their ideas support me.

This view rests on an assumption and has limits. I assume that a thought pattern is determined not by what it is made of but by how it is put together, and my own research cannot test that assumption. Kim set aside the felt quality of sensation as something function cannot explain, and Francisco Varela argued that mind arises not from computation inside the brain but from the activity of a living body exchanging with its environment. If Varela is right, my assumption shakes. I do not know whether the feel of sensation can be explained as a thought pattern either. So I look only at how much models and people share in thinking that shows itself in speech and judgment, and I leave sensory experience and the activity of the body out of scope.

The self shows itself in speaking and judging about oneself. It is too large a topic to take on at once, so I first carry thinking that shows itself in speech and judgment from people to AI, and then use what I learn from models to ask about human thinking again. The two directions of my motto are these two steps.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <div style="display: grid; grid-template-columns: repeat(4, minmax(0, 140px)); justify-content: center; gap: 1em;">
    <div>
      <img src="/images/rp-book-dennett.jpg" alt="Cover of Consciousness Explained by Daniel C. Dennett" style="width: 100%; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.2);">
      <p style="font-size: 0.78em; color: #666; margin-top: 0.5em; line-height: 1.3;">Daniel C. Dennett<br><em>Consciousness Explained</em> (1991)</p>
    </div>
    <div>
      <img src="/images/rp-book-hofstadter.jpg" alt="Cover of I Am a Strange Loop by Douglas Hofstadter" style="width: 100%; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.2);">
      <p style="font-size: 0.78em; color: #666; margin-top: 0.5em; line-height: 1.3;">Douglas Hofstadter<br><em>I Am a Strange Loop</em> (2007)</p>
    </div>
    <div>
      <img src="/images/rp-book-kim.jpg" alt="Cover of Physicalism, or Something Near Enough by Jaegwon Kim" style="width: 100%; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.2);">
      <p style="font-size: 0.78em; color: #666; margin-top: 0.5em; line-height: 1.3;">Jaegwon Kim<br><em>Physicalism, or Something Near Enough</em> (2005)</p>
    </div>
    <div>
      <img src="/images/rp-book-varela.jpg" alt="Cover of The Embodied Mind by Francisco Varela, Evan Thompson, and Eleanor Rosch" style="width: 100%; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.2);">
      <p style="font-size: 0.78em; color: #666; margin-top: 0.5em; line-height: 1.3;">Varela, Thompson, and Rosch<br><em>The Embodied Mind</em> (1991)</p>
    </div>
  </div>
  <p style="font-size: 0.85em; color: #888; margin-top: 0.8em;"><em>Four of the books behind this view: the self as a story, the self as a loop, mind as function, and mind as the activity of a living body.</em></p>
</div>

## Earlier Research

To explore what thinking is, in my earlier research I split thinking into three areas, reasoning, understanding, and decision-making, and examined the behavior of large language models (models like ChatGPT). I found that in every area, models were excessively influenced by their learned data or by the prompt, a pitfall.

### Reasoning

The models appeared to repeat familiar solutions instead of composing rules. ARC is a collection of puzzles in which you find a visual rule from a few examples. When I gave problems built from the same rule but with a different look, accuracy dropped sharply on many tasks, and models struggled most on tasks that require combining several rules. A model that understood the rule should still solve the problem when the look changes. The frame for evaluation was a cognitive-science hypothesis, the Language of Thought Hypothesis, that human reasoning rests on three properties, logical coherence, compositionality, and productivity, and under this frame the models fell short of people.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q1-reasoning.png" alt="Human reasoning vs LLM reasoning comparison" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>The Language of Thought lens: three properties of human reasoning (left) against how LLMs hold up on each (right).</em></p>
</div>

### Understanding

The models appeared to lean on surface cues more than on understanding. On a test where cues such as a conspicuously long correct option were reduced, the models' accuracy dropped and they fell far behind people. This test turns ARC puzzles into a multiple-choice benchmark, MC-LARC. If a model writes its answer directly, it is hard to tell whether it solved the problem by understanding, but with multiple choice I can vary the options and tell whether the model chose by understanding or by cues.

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q2-mclarc.png" alt="MC-LARC: The benefit of multiple-choice for pinpointing errors" style="max-width: 100%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Generation hides where a model goes wrong; a contrastive multiple-choice format brings the specific mistake into view.</em></p>
</div>

### Decision-Making

The models appeared to be pulled by a bias that resembles gambling addiction. When the model set its own bet amount and goal, risky choices increased. The experiment was a slot machine designed to lose money on average, and each round I compared a condition where the model sets the amount and goal with a condition where they are assigned.

In the model's explanations of its own decisions (its self-description), expressions resembling two concepts from gambling psychology sometimes appeared. The illusion of control is believing you control a chance outcome, and loss chasing is raising your bets to win back lost money. But I could not confirm whether those explanations are the real reasons, and I take up that problem below in "Current Research."

<div style="text-align: center; margin: 2em 0; background-color: #fafbfc; border-radius: 8px; padding: 1em;">
  <img src="/images/rp-q3-gambling.png" alt="LLM gambling addiction research questions" style="max-width: 80%; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <p style="font-size: 0.85em; color: #888; margin-top: 0.5em;"><em>Testing whether a model can drift into gambling-addiction-like behavior.</em></p>
</div>

## Limits and Hypothesis

The failures in all three areas converge. In reasoning the model was pulled toward familiar solutions, in understanding toward surface cues, and in decision-making toward a bias that resembles gambling addiction, and I could not test whether the model noticed that pull on its own.

The two attempts to reduce this pull left the same point open. One aimed at reasoning: to reduce the pull toward familiar solutions, I injected random vectors (bundles of numbers) into the input so the model produces different solutions. When solutions are more varied, a correct one is more likely to appear.

The other was a framework in which an AI agent, one that acts on its own to solve problems, looks back at its own attempt when it gets stuck and rewrites its solving tips (a memo of how to approach problems). In this framework too, whether the reflection was right was judged from outside.

In both attempts, checking whether an answer was right and deciding whether to accept a revised tip was done by people or by external programs. The noticing was done for the model, from outside. That made me wonder whether the model itself knows where it went wrong. I call this ability metacognition, the ability to examine and fix what one is doing, and I formed the hypothesis that this may be what models lack. If the self is seen as a story one tells about oneself, then examining oneself is part of how that story gets made.

## Where I Am Heading

### Current Research

To test this hypothesis, I am working on checking for metacognition inside models. The goal is for a model to notice and correct, on its own, the pull seen in the three areas, and I split this into three questions. Of the three questions below, the first two ask whether a model can notice and fix its own errors without outside verification, and the third asks whether its self-description guides its behavior.

The first is whether a model notices where it may be wrong. I look at whether signals inside the model (values such as how low the probability of its answer is) show where it may go wrong. If they do, the next step is to make the model use those signals itself.

The second is whether a model can fix an error it has noticed. To fix it, I believe the model has to know its own state. But a self-description, what the model says about itself, may not be the real reason but an explanation added to fit the answer it gave. So I split this into two steps. First, I find the parts inside the model that seem to have influenced the answer, compare them with the self-description, and also check that the parts I found are right. If the description captures the real reason, I then test whether the model can fix its error with that description, and if they diverge, I map how they diverge.

The third is a different question from the first two: does a self-description lead to self-awareness? I test in models whether the self-story that Dennett described actually guides behavior, and I call this self-awareness. I rewrite the model's self-description and watch whether its behavior changes with it. But behavior can change after such an edit simply because the model followed a new instruction. Telling those two apart is the hardest part of this question.

### Long-Term Vision

My longer-term goal is to understand how intelligence, and the consciousness and self within it, work. I cannot yet answer that question, and the three questions are a first look at the part that shows itself in speech and judgment.

Going from AI back to people is work that lies ahead. Psychology has found that people sometimes add reasons after making a judgment (Nisbett and Wilson's work is the best known). If I can find the conditions under which a model's self-description and its actual internal parts diverge, I can compare them with this research and ask again how people check their own judgments. But models and people may err in different ways, so I first have to check whether this comparison holds. That comparison is my next goal.

---

## Related Publications

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5em; margin-top: 1.5em;">

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2024-03-18-TIST" style="color: #2c3e50; text-decoration: none;">Reasoning Abilities of Large Language Models: In-Depth Analysis on the Abstraction and Reasoning Corpus</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">ACM TIST, 2025</p>
  <p style="font-size: 0.85em; color: #555;">Analyzed how language models reason on ARC, using the Language of Thought Hypothesis as the frame.</p>
</div>

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2024-11-mc-larc-emnlp/" style="color: #2c3e50; text-decoration: none;">From Generation to Selection: Findings of Converting Analogical Problem-Solving into Multiple-Choice Questions</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">EMNLP Findings, 2024</p>
  <p style="font-size: 0.85em; color: #555;">Proposed MC-LARC, a multiple-choice benchmark for measuring how well language models understand.</p>
</div>

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2025-01-gambling-addiction/" style="color: #2c3e50; text-decoration: none;">Can Large Language Models Develop Gambling Addiction?</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">NeurIPS 2026</p>
  <p style="font-size: 0.85em; color: #555;">In slot-machine experiments, language models showed risk-taking that resembles gambling addiction.</p>
</div>

<div style="border: 1px solid #e5e5e5; border-radius: 8px; padding: 1.2em; background-color: #fafbfc; box-shadow: 0 1px 3px rgba(0,0,0,0.06);">
  <div style="font-weight: bold; font-size: 0.95em; margin-bottom: 0.4em;"><a href="/publication/2026-05-from-noise-to-diversity/" style="color: #2c3e50; text-decoration: none;">From Noise to Diversity: Random Embedding Injection in LLM Reasoning</a></div>
  <p style="font-size: 0.82em; color: #888; margin-bottom: 0.5em;">NeurIPS 2026</p>
  <p style="font-size: 0.85em; color: #555;">Injecting random vectors into the input makes a language model's solutions more varied.</p>
</div>

</div>
