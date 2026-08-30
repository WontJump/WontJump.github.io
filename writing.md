---
layout: page
title: Dolor
permalink: /writing/
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
---

<p class="page-intro">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>

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
