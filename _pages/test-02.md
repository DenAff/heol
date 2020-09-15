---
title: Test-02
permalink: test-02.html
---

<ul class="docs-nav">
{% assign posts_list = site.posts | sort:"title" %}
{% assign last_cat = "" %}
{% for posts in posts_list %}
    {% if posts.title != "" %}
        {% for category in posts.categories limit:1 %}
            {% if category != last_cat %}
    <li><strong>{{ category | replace: "-", " " | capitalize  }}</strong></li>
            {% endif %}
            {% assign last_cat = category %}
        {% endfor %}
    <li><a href="{{ posts.slug }}" class="cc-active">{{ posts.title }}</a></li>
    {% endif %}
{% endfor %}
</ul>