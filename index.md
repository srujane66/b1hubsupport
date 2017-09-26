---
layout: default
search_omit: true
---

{% assign sorted_cats = site.categories | sort %}
{% include search-results.html %}

<div id="content-container">
  <div class="row">
  {% for category in sorted_cats %}
    {% assign sorted_posts = category[1] | sort: 'postid' %}
    <div class="col-md-6">
      <h3 id="{{category[0] | uri_escape | downcase }}"><a href="{{ site.baseurl}}/{{ category[0] }}/">{{ category[0] | capitalize | replace: '-', ' ' }}</a> <small>({{ category[1].size }})</small></h3>
      <ul class="page-title-list">
        {% for post in sorted_posts | limit:5 %}
        <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
        <li class="view-all"><a href="{{ site.baseurl}}/{{ category[0] }}/"><small>View all</small></a></li>
      </ul>
    </div>
  {% endfor %}
  </div>
</div>