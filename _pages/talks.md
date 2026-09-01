---
layout: archive
title: "Talks"
permalink: /talks/
author_profile: true
---

{% include base_path %}

Refereed conference presentations. Papers appear on the
[publications]({{ base_path }}/publications/) page.

{% assign talks = site.talks | sort: 'date' | reverse %}
{% for post in talks %}
  {% include archive-single-talk.html %}
{% endfor %}
