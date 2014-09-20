---
layout: page
title: PyCon JP 2014
tagline: Joined Reports.
---
{% include JB/setup %}

* **September 13 (Sat)**


{% for post in site.posts %}
  {% if post.implementation == "2014-09-13" %}
    {{ post.time }} &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
  {% endif %}
{% endfor %}

* **September 14 (Sun)**

{% for post in site.posts %}
  {% if post.implementation == "2014-09-14" %}
    {{ post.time }} &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
  {% endif %}
{% endfor %}

* **More topic**

{% for post in site.posts %}
  {% if post.section == "more-topic" %}
    &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
  {% endif %}
{% endfor %}

* **Photos**

{% for post in site.posts %}
  {% if post.section == "photos" %}
    &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
  {% endif %}
{% endfor %}
