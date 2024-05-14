---
permalink: /about/
title: "About me"
author_profile: true
redirect_from: 
  - /about.html
---

Hi, I'm James. I'm a robotics engineer. You can find an abreiviated version of my CV below.

Education
======
* Ph.D in Mechanical Engineering, Temple University, 2026 (expected)
* M.S. in Mechanical Engineering, Temple University, 2019
* B.S. in Mechanical Engineering, Drexel University, 2014

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  