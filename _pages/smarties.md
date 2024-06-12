---
layout: archive
title: "Smarties"
permalink: /smarties/
author_profile: true
---

{% include base_path %}

Smarties are little nuggets of technical knowhow I picked up during my work. They're inspired by [Simon Willison's TILs](https://til.simonwillison.net/).

{% for post in site.smarties reversed %}
  {% include archive-single.html %}
{% endfor %}
