---
permalink: /
title: "Welcome"
excerpt: "Portfolio Website"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Nice to meet you. I study AI in two directions: understanding people from AI, and improving AI from people. So far, all of my work has circled a single question. What is it to think? I probe how large language models reason, understand, and decide, and where each of those breaks down. I read them in the language of cognitive science. I first chased that question under [Prof. Sundong Kim](https://sundong.kim/), working through ARC-AGI, a benchmark of abstract visual reasoning that plays like an IQ test, and these days I carry that question forward as a research intern at Microsoft Research Asia.

<div class="content-container">
  <img src="images/20241115_161350(1).jpg" alt="profile">
</div>

Lay those breakdowns side by side and they share one crack: nothing inside the model is watching it think. Lately that has turned me toward a harder question: what would it mean for a model to be self-aware? Daniel Dennett gives me a way in. On his Multiple Drafts Model, consciousness is not a separate inner substance but the running product of many parallel processes, and the self that seems to sit behind it is a "center of narrative gravity," a useful fiction spun from a system's own self-description. Read that way, metacognition stops being an irreducible mystery and becomes something I can measure, train for, and build. I once aimed that inquiry at thinking, at how models reason, understand, and decide. Now I aim it beyond, at consciousness itself. If you are curious how I think about all this, my [Research Philosophy](/research-philosophy/) lays out the fuller arc. And away from research, I am also a passionate fiction writer; some of my stories live under [Writing](/press/).

<div class="image-grid">
  <img src="images/diagonal-flip.gif" alt="diagonal flip">
  <img src="images/horizontal-align.gif" alt="horizontal align">
  <img src="images/tetris.gif" alt="tetris">
</div>

<hr style="height:1px; border:none; background-color:#e5e5e5;">

{% include base_path %}

# Publications
{% for post in site.publications reversed %}
  {% if post.type != "domestic-conference" %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

# Domestic Conference
{% for post in site.publications reversed %}
  {% if post.type == "domestic-conference" %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
