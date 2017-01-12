---
layout: category
title: Web Programming
category: web_programming
---

{% assign curr_size = site.categories[page.category] | size %}
{% unless curr_size > 0 %}
  {% assign word = page.category %}
  <h3> {% localize no_related_post %} {% localize word %} </h3>
{% endunless %}

{% if curr_size > 0 %}
<ul class="post-list">
    {% assign posts = site.categories[page.category] | sort:"date" | reverse %}
    {% for post in posts %}
    <li class="post-list-enclosure-2pr">
      <div class="card-details">
        <div class="card-details-header">
          <span class="card-details-header-title">{{post.title}}</span>
        </div>
        <div class="card-details-readmore">
          <a href="{{post.url}}"> More > </a>
        </div>
      </div>
    </li>
    {% endfor %}
</ul>
{% endif %}