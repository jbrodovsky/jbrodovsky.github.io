---
permalink: /about/
title: "About me"
author_profile: true
redirect_from: 
  - /about.html
---

{% include base_path %}

I'm James Brodovsky, a navigation and estimation engineer. I work on inertial navigation,
sensor fusion, and position estimation in GNSS-denied environments — the problem of knowing
where you are when satellite navigation is jammed, spoofed, blocked, or simply not there.

My work sits at the intersection of three things: strapdown inertial navigation on cheap,
noisy MEMS-grade sensors; recursive Bayesian estimation, particularly particle filters and
nonlinear Kalman variants; and geophysical map matching, where the Earth's own gravity,
magnetic, and bathymetric anomaly fields act as the map. The through-line is making
navigation work on hardware and in environments where the textbook assumptions don't hold.

An abbreviated CV follows. For the full picture, see
[publications]({{ base_path }}/publications/), [talks]({{ base_path }}/talks/), and
[projects]({{ base_path }}/portfolio/).

## Education

* Ph.D. in Mechanical Engineering, Temple University, 2026 (expected)
* M.S. in Mechanical Engineering, Temple University, 2019
* B.S. in Mechanical Engineering, Drexel University, 2014

## Experience

<!--
TODO(james): add date ranges to each entry below — I deliberately left them out rather
than guess. Two other things to decide here:
  1. The current role is listed without an employer, matching the site-wide choice to
     position by role rather than company. Google Scholar already lists "Senior Navigation
     Engineer, Mach Industries" publicly, so this is the only surface that omits it.
     Either name it here or accept the inconsistency knowingly.
  2. Confirm the Penn State ARL and Tergeo entries are how you want them framed.
-->

* **Senior Navigation Engineer** — navigation, guidance, and estimation software for
  autonomous air vehicles.
* **Adjunct Instructor**, Robotics Engineering, Worcester Polytechnic Institute — graduate
  course on advanced robotic navigation.
* **Research Associate**, Boni Lab, Temple University — spatial individual-based simulation
  of malaria drug-resistance evolution.
* **Research & Development Engineer**, Applied Research Laboratory, Pennsylvania State
  University — particle filtering and geophysical map matching for undersea navigation.
* **Founder**, Tergeo Technologies — early-stage hardware venture; NSF I-Corps.

## Technical focus

* **Navigation** — strapdown INS mechanization, MEMS and tactical-grade IMU error modeling,
  GNSS/INS integration, geophysical map matching (gravity, magnetic, bathymetric anomaly)
* **Estimation** — particle filters, extended and unscented Kalman filters, multi-target
  tracking (PHD filter, MHT), observability and fixability analysis
* **Software** — Rust, Python, C++, MATLAB; numerical methods, simulation, and research
  tooling built to be reused rather than thrown away

## Publications

  {% assign publications = site.publications | sort: 'date' | reverse %}
  <ul>{% for post in publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
## Talks

  {% assign talks = site.talks | sort: 'date' | reverse %}
  <ul>{% for post in talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
  
## Teaching

  {% assign teaching = site.teaching | sort: 'date' | reverse %}
  <ul>{% for post in teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
