---
layout: archive
title: "Projects"
permalink: /portfolio/
author_profile: true
---

{% include base_path %}

Open-source navigation software, datasets, and tooling. Most of this exists because I needed
it for research and there wasn't a maintained version I could use — which is also why it's
public. Everything below is on [GitHub](https://github.com/jbrodovsky).

{% for post in site.portfolio %}
  {% include archive-single.html %}
{% endfor %}
