---
layout: page
title: Tech
permalink: /tech/
---

# Tech Blog

Welcome to my tech blog! Here I'll share my thoughts, experiences, and tutorials about various technologies I work with.

## Recent Posts

{% for post in site.categories.tech %}
  <div class="post-preview">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
  </div>
{% endfor %} 