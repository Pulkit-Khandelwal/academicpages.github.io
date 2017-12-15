---
layout: archive
title: "Reading List"
permalink: /booklist/
author_profile: true
---

{% include base_path %}

{% for post in site.booklist reversed %}
  {% include archive-single.html %}
{% endfor %}
