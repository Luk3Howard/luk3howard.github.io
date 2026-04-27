---
layout: default
title: Tags
permalink: /tags/
---

<h1>Posts by Tag</h1>

{% assign tags = site.tags | sort %}

<div class="tag-index">
  {% for tag in tags %}
    <section id="{{ tag[0] | slugify }}" class="tag-section">
      <h2>#{{ tag[0] }}</h2>
      <ul class="post-list">
        {% for post in tag[1] %}
          <li>
            <span class="post-date">{{ post.date | date: "%b %d, %Y" }}</span>
            <a href="{{ post.url }}">{{ post.title }}</a>
          </li>
        {% endfor %}
      </ul>
    </section>
  {% endfor %}
</div>
