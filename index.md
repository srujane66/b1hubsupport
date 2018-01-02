---
layout: default
search_omit: true
---

{% assign cat_array = 'general, application, hub, troubleshoot, chatbot, lighting, audio, curtain-controllers, dual-load-switches, in-wall-dimmers, outlets, switches, color-controllers, cameras, motion-sensors, multi-sensors, open-close-sensors, range-extender, shock-sensors, sirens, door-locks, smoke-co-detectors, water-sensor, thermostats, energy-management, insteon-devices, trackers, voiceact, remotes' | split: ', '  %}

{% include search-results.html %}

<div id="content-container">
  <div class="row">
  {% for category in cat_array %}
    {% assign sorted_posts = site.categories[category] | sort: 'postid' %}
    <div class="col-md-6">
      <h3 id="{{category | uri_escape | downcase }}"><a href="{{ site.baseurl}}/{{ category }}/">{{ category | capitalize | replace: '-', ' ' }}</a> <small>({{ site.categories[category].size }})</small></h3>
      <ul class="page-title-list">
        {% for post in sorted_posts | limit:5 %}
          <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
        <li class="view-all"><a href="{{ site.baseurl}}/{{ category }}/"><small>View all</small></a></li>
      </ul>
    </div>
  {% endfor %}
  </div>
</div>