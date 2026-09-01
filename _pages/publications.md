---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

{% assign conference = site.publications | where: 'pubtype', 'conference' | sort: 'date' | reverse %}
{% assign journal    = site.publications | where: 'pubtype', 'journal'    | sort: 'date' | reverse %}
{% assign inreview   = site.publications | where: 'pubtype', 'review'     | sort: 'date' | reverse %}
{% assign theses     = site.publications | where: 'pubtype', 'thesis'     | sort: 'date' | reverse %}

{% if journal.size > 0 %}
<h2 class="archive__subtitle">Journal Articles</h2>
{% for post in journal %}{% include archive-single.html %}{% endfor %}
{% endif %}

{% if conference.size > 0 %}
<h2 class="archive__subtitle">Conference Proceedings</h2>
{% for post in conference %}{% include archive-single.html %}{% endfor %}
{% endif %}

{% if inreview.size > 0 %}
<h2 class="archive__subtitle">In Review</h2>
{% for post in inreview %}{% include archive-single.html %}{% endfor %}
{% endif %}

{% if theses.size > 0 %}
<h2 class="archive__subtitle">Theses</h2>
{% for post in theses %}{% include archive-single.html %}{% endfor %}
{% endif %}
