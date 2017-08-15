---
layout: misc
title: News
permalink: /news/
---
{% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}

<div class="home">

  <h1 class="page-heading text-center">News</h1>
  <hr />

  <!-- <ul class="post-list"> -->
  <dl class="row post-list">
    {% for post in site.posts %}
        <dt class="col-md-2 post-meta text-md-right text-muted"><small>{{ post.date | date: date_format }}</small></dt>
        <dd class="col-md-10">
          <div class="post-item">
            {% if post.im %}<div><img class="img-responsive mr-3" src="{{ post.im }}" alt="" height="100px"></div>{% endif %}
            <div>
              <h3>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
              </h3>
              <div class="text-muted">
                {{ post.excerpt }}
              </div>
            </div>
          </div>
          <!-- <hr /> -->
        </dd>
    {% endfor %}
  </dl>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>

</div>