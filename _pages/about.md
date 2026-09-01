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
magnetic, and bathymetric anomaly fields act as the map. The through-line is making navigation
work on hardware and in environments where the textbook assumptions don't hold.

An abbreviated CV follows. For the full picture, see
[publications]({{ base_path }}/publications/), [talks]({{ base_path }}/talks/), and
[projects]({{ base_path }}/portfolio/).

## Education

* **Ph.D., Mechanical Engineering**, Temple University — expected December 2026<br>
  Dissertation: *Robust Inertial Navigation in GNSS-Denied Environments Using MEMS Grade
  Sensors and Passive Geophysical Aiding*. Advisor: Philip Dames.
* **M.S., Mechanical Engineering**, Temple University, 2019<br>
  Thesis: *A Comparison of the Probability Hypothesis Density Filter and the Multiple
  Hypothesis Tracker for Tracking Targets of Multiple Types*
* **B.S., Mechanical Engineering**, Drexel University, 2014

## Experience

<!--
TODO(james): the current role is listed without an employer, matching the site-wide choice to
position by role rather than company. Your CV, LinkedIn, and Google Scholar all name Mach
Industries, so this page is now the only surface that omits it. Either name it here or accept
the inconsistency knowingly — but it is a choice, not an oversight.
-->

* **Senior Navigation Engineer** — *Jan 2026 – present*<br>
  Led a ground-up rewrite of the platform's navigation filter, replacing a legacy EKF with a
  modular, state-agnostic Kalman filtering library and a proper strapdown INS mechanization
  with tightly-coupled GNSS integration. Contributed to a clean-sheet, safety-first flight
  software architecture in Rust built around deterministic real-time behavior and strong
  module boundaries. Led research and development of magnetic and geophysical alternative-PNT
  algorithms for GNSS-denied operation, integrated and validated in SITL and HITL.

* **Research Associate**, Boni Lab, Institute for Genomics and Evolutionary Medicine, Temple
  University — *Dec 2024 – Dec 2025*<br>
  Built and maintained a Python HPC simulation and analysis pipeline for malaria transmission
  and drug-resistance modeling, used to produce calibrated scenario analyses for several
  African national health agencies. Standardizing the pipeline cut calibration time and made
  it usable by researchers who hadn't written it.

* **Research and Development Engineer**, Navigation R&D Division, Applied Research Laboratory,
  Pennsylvania State University — *May 2019 – Nov 2024*<br>
  Researched and developed autonomous navigation for military submarines in GNSS-denied
  environments. Led development of a particle filter localization method using sonar and
  bathymetric maps, which met accuracy requirements more often than the legacy method with a
  20% reduction in time-to-fix. The software is deployed on U.S. Navy submarines in an
  observer capacity.

* **Chief Executive Officer and Robotics Engineer**, Tergeo Technologies — *Jul 2021 – Sep 2023*<br>
  Co-founder. Ran business development, customer discovery, contractor management, and
  fundraising, and designed and prototyped the product: a ROS-based litter-sweeping robot with
  a custom chassis and a Mask R-CNN vision model for litter perception. The company closed
  for failure to reach product-market fit.

* **Research Assistant**, Temple Robotics and Artificial Intelligence Laboratory, Temple
  University — *Aug 2018 – May 2019*

* **Mechanical Engineer**, McKean Defense Group — *Nov 2016 – Oct 2018*<br>
  Design and integration of shipboard hull, mechanical, and electrical system upgrades.

* **Design Engineer**, Macron Dynamics — *Jun 2016 – Nov 2016*

* **Student Naval Aviator**, Training Wing 5, United States Navy — *Jun 2014 – Jul 2016*<br>
  Honorable discharge due to a reduction in force.

## Teaching

* **Adjunct Teaching Professor**, Robotics Engineering Department, Worcester Polytechnic
  Institute — *Aug 2023 – present*<br>
  Developed and teach a graduate-level online asynchronous course on autonomous robotic
  navigation, covering basic Bayesian filtering through marine-grade inertial navigation.
* **Teaching Assistant**, Mechanical Engineering Department, Temple University —
  *Aug 2018 – May 2019*

## Funding and awards

* **Principal Investigator**, *A Machine Learning Approach to Geophysical Map-Matching
  Fixability* — Penn State Applied Research Laboratory Internal Research and Development
  Grant, $50,000, Jul 2024 – Dec 2024

## Technical focus

* **Navigation** — strapdown INS mechanization, MEMS and tactical-grade IMU error modeling,
  loosely- and tightly-coupled GNSS/INS integration, geophysical map matching (gravity,
  magnetic, bathymetric anomaly)
* **Estimation** — particle filters, extended and unscented Kalman filters, multi-target
  tracking (PHD filter, MHT), observability and fixability analysis
* **Software** — Python and MATLAB (advanced), Rust and C++ (intermediate), ROS; numerical
  methods, simulation, and research tooling built to be reused rather than thrown away

## Professional memberships

Institute of Navigation (ION) · IEEE · IEEE Robotics and Automation Society

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
  
## Teaching activity

  {% assign teaching = site.teaching | sort: 'date' | reverse %}
  <ul>{% for post in teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
