---
layout: default
title: Home
description: Will Jump is a PhD student in computer science working at the boundary of mathematics and computation.
---

<section class="intro">
  <p class="eyebrow">PhD student · Computer science</p>
  <h1>Will Jump</h1>
  <p class="lede">I work at the boundary of computer science and mathematics, with a particular interest in category theory, probability, and the structures that connect them.</p>
  <div class="intro-links">
    <a class="text-link" href="{{ '/research/' | relative_url }}">Research</a>
    <a class="text-link" href="{{ '/cv/' | relative_url }}">Curriculum vitæ</a>
    <a class="text-link" href="mailto:{{ site.author.email }}">Email</a>
  </div>
</section>

<section class="home-section">
  <div class="section-heading">
    <h2>Recent writing</h2>
    <a href="{{ '/writing/' | relative_url }}">All posts</a>
  </div>
  {% if site.posts.size > 0 %}
  <ol class="post-list">
    {% for post in site.posts limit:5 %}
      <li>
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d %b %Y" }}</time>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ol>
  {% else %}
  <p class="muted">Notes and essays will appear here.</p>
  {% endif %}
</section>

<section class="home-section note">
  <h2>About this site</h2>
  <p>This is a working notebook for research ideas, explanations, and occasional observations about academic life. Posts support inline mathematics such as \(P(A \mid B)\) and displayed equations.</p>
</section>

