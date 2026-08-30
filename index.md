---
layout: default
title: Lorem
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
---

<section class="intro">
  <p class="eyebrow">Lorem ipsum · Dolor sit amet</p>
  <h1>Lorem ipsum</h1>
  <p class="lede">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante venenatis dapibus posuere velit aliquet.</p>
  <div class="intro-links">
    <a class="text-link" href="{{ '/research/' | relative_url }}">Lorem</a>
    <a class="text-link" href="{{ '/cv/' | relative_url }}">Ipsum dolor</a>
    <a class="text-link" href="mailto:{{ site.author.email }}">Sit amet</a>
  </div>
</section>

<section class="home-section">
  <div class="section-heading">
    <h2>Lorem ipsum</h2>
    <a href="{{ '/writing/' | relative_url }}">Dolor sit</a>
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
  <p class="muted">Lorem ipsum dolor sit amet.</p>
  {% endif %}
</section>

<section class="home-section note">
  <h2>Consectetur adipiscing</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed posuere consectetur est at lobortis. Donec ullamcorper nulla non metus auctor fringilla.</p>
</section>
