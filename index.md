---
layout: default
search_omit: true
---

{% assign sorted_cats = site.categories | sort %}
{% include search-results.html %}

<div id="content-container">
  <div class="row">
  {% for category in sorted_cats %}
    {% assign sorted_posts = category[1] | sort: 'title' %}
    <div class="col-md-6">
      <h3 id="{{category[0] | uri_escape | downcase }}">{{category[0] | capitalize}}</h3>
      <ul>
        {% for post in sorted_posts %}
        <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
  </div>
</div>