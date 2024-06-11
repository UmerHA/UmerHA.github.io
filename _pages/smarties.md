---
layout: archive
title: "Smarties"
permalink: /smarties/
author_profile: true
---

{% include base_path %}

Smarties are little nuggets of technial knowhow I picked up from experience. They're inspired by [Simon Willison's TILs](https://til.simonwillison.net/).

{% for post in site.smarties reversed %}
  {% include archive-single.html %}
{% endfor %}
