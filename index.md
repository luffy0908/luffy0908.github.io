---
layout: default
---

<div>
  <ul class="listing">
  {% for post in site.posts limit: 20 %}
    {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
    {% if year != y %}
      {% assign year = y %}
      <li class="listing-seperator">{{ y }}</li>
    {% endif %}
    <li class="listing-item">
      <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
      <a href="{{ post.url }}" titile="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
  </ul>
  <div class="divider"></div>
  <ul>
    <li class="listing-seperator"><a href="/archive.html">Long ago</a></li>
  </ul>
</div>
