---
layout: page
title: Photo Gallery
permalink: /gallery/
---

# Photo Gallery

Explore our collection of images across different categories.

## AI Generated Art

<div class="gallery-grid">
{% for image in site.static_files %}
    {% if image.path contains 'gallery/ai-generated' and image.extname == '.jpeg' %}
    <div class="gallery-item">
        <img src="{{ image.path | relative_url }}" alt="{{ image.basename }}" loading="lazy">
        <div class="image-title">
            {% assign filename = image.basename | append: image.extname %}
            {{ site.data.image_titles.ai-generated[filename] | default: image.basename | replace: '-', ' ' | capitalize }}
        </div>
    </div>
    {% endif %}
{% endfor %}
</div>

## Travel Photos

<div class="gallery-grid">
{% for image in site.static_files %}
    {% if image.path contains 'gallery/places' and image.extname == '.jpeg' %}
    <div class="gallery-item">
        <img src="{{ image.path | relative_url }}" alt="{{ image.basename }}" loading="lazy">
        <div class="image-title">
            {% assign filename = image.basename | append: image.extname %}
            {{ site.data.image_titles.places[filename] | default: image.basename | replace: '-', ' ' | capitalize }}
        </div>
    </div>
    {% endif %}
{% endfor %}
</div>

## Technology

<div class="gallery-grid">
{% for image in site.static_files %}
    {% if image.path contains 'gallery/tech' and image.extname == '.jpeg' %}
    <div class="gallery-item">
        <img src="{{ image.path | relative_url }}" alt="{{ image.basename }}" loading="lazy">
        <div class="image-title">
            {% assign filename = image.basename | append: image.extname %}
            {{ site.data.image_titles.tech[filename] | default: image.basename | replace: '-', ' ' | capitalize }}
        </div>
    </div>
    {% endif %}
{% endfor %}
</div>

<style>
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
    margin: 40px 0;
}

.gallery-item {
    position: relative;
    overflow: hidden;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
}

.gallery-item:hover {
    transform: translateY(-5px);
}

.gallery-item img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    display: block;
}

.image-title {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0,0,0,0.7);
    color: white;
    padding: 10px;
    text-align: center;
    font-size: 0.9em;
}

@media (max-width: 768px) {
    .gallery-grid {
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    }
}
</style>

<!-- Debug information -->
<div style="display: none;">
{% for image in site.static_files %}
    {% if image.path contains 'gallery' %}
    Found image: {{ image.path }}<br>
    {% endif %}
{% endfor %}
</div> 