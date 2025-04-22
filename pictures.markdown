---
layout: page
title: Pictures
permalink: /pictures/
---

# Photo Gallery

A collection of my favorite photos from my travels and daily life.

## Recent Photos

{% for post in site.categories.pictures %}
  <div class="photo-preview">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
    {% if post.image %}
      <img src="{{ post.image }}" alt="{{ post.title }}" class="photo-thumbnail">
    {% endif %}
    <p>{{ post.excerpt }}</p>
  </div>
{% endfor %} 