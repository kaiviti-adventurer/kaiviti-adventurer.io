---
layout: page
title: Places
permalink: /places/
---

# Travel & Places

Join me on my adventures around the world! Here I'll share stories, tips, and experiences from the places I've visited.

## Recent Travel Posts

{% for post in site.categories.places %}
  <div class="post-preview">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
  </div>
{% endfor %} 