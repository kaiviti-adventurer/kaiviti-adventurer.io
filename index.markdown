---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
---

# Welcome to My Blog!

I'm a tech enthusiast and travel lover. This is where I share my experiences, thoughts, and adventures.

## Recent Posts

### Tech
{% for post in site.categories.tech limit:3 %}
  <div class="post-preview">
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
  </div>
{% endfor %}
[View all tech posts](/tech/)

### Places
{% for post in site.categories.places limit:3 %}
  <div class="post-preview">
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
  </div>
{% endfor %}
[View all travel posts](/places/)

### Latest Photos
{% for post in site.categories.pictures limit:3 %}
  <div class="photo-preview">
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    {% if post.image %}
      <img src="{{ post.image }}" alt="{{ post.title }}" class="photo-thumbnail">
    {% endif %}
  </div>
{% endfor %}
[View all photos](/pictures/)
