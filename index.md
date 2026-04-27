---
layout: default
title: Home
---

{% assign posts_by_category = site.posts | group_by: "category" %}

{% for category in posts_by_category %}
  <section class="category-group">
    <h2>{{ category.name | capitalize }}</h2>
    <ul class="post-list">
      {% for post in category.items %}
        <li>
          <span class="post-date">{{ post.date | date: "%b %d" }}</span>
          <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </section>
{% endfor %}
