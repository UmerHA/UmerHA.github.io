---
layout: archive
title: "Essays and Observations"
permalink: /essays/
author_profile: true
---

{% include base_path %}

{% for post in site.essays reversed %}
  {% include archive-single.html %}
{% endfor %}
