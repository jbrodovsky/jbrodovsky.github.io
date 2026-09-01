---
title: "geo-fixability — When is a geophysical map good enough to navigate on?"
collection: portfolio
permalink: /portfolio/geo-fixability
excerpt: 'A study relating trajectory characteristics and geophysical map properties to achievable navigation accuracy, via Fisher information, the posterior Cramér-Rao bound, and a Rao-Blackwellized particle filter.'
---

{% include base_path %}

[Repository](https://github.com/jbrodovsky/geo-fixability)

Geophysical map matching works — sometimes. The open question is when. This project builds a
predictive model relating vehicle trajectory characteristics and geophysical map properties to
achievable navigation accuracy, so the question becomes answerable before you fly the mission
rather than after: *if I traverse this area at this speed and heading, how much will my
navigation solution actually improve?*

The approach:

* Generate synthetic scalar fields — terrain, magnetic, gravity — with controllable and
  classifiable information content.
* Simulate INS trajectories across a range of speed and heading profiles.
* Estimate with a Rao-Blackwellized particle filter aided by the anomaly field.
* Compute theoretical bounds — the Fisher information matrix and the posterior Cramér-Rao
  bound — and measure filter efficiency against them.
* Extract the trajectory and map features that predict performance, and regress
  (trajectory, map) → uncertainty reduction.
* Validate against real data: SRTM15+, WDMAM, KITTI.

The useful output is a *fixability* metric that behaves like a sensor specification: given
these trajectory parameters over this map, I know my position to within some bound. That
turns geophysical aiding from something you try into something you can budget for.

<!-- TODO(james): link the resulting journal paper and dissertation chapter once they're out. -->
