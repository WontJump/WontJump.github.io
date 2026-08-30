---
layout: page
title: Writing
permalink: /writing/
description: Essays and research notes by Will Jump.
---

<p class="page-intro">Research notes, explanations, and longer-form thoughts.</p>

<ol class="post-list post-list--full">
  {% for post in site.posts %}
    <li>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d %b %Y" }}</time>
      <div>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {% if post.description %}<p>{{ post.description }}</p>{% endif %}
      </div>
    </li>
  {% endfor %}
</ol>

