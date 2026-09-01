---
title: "mems-nav-dataset — An open benchmark for MEMS-grade navigation"
collection: portfolio
permalink: /portfolio/mems-nav-dataset
excerpt: 'Long-duration GPS/IMU/INS trajectories from ubiquitous MEMS-grade smartphone sensors, plus processed GNSS degradation, duty-cycling, and spoofing scenarios for evaluating alternative navigation algorithms.'
---

{% include base_path %}

[Repository](https://github.com/jbrodovsky/mems-nav-dataset)

Existing navigation datasets tend to fall into two camps. The robotics and unmanned systems
community publishes short, small-scale laboratory or field collections. The marine and
aerospace communities publish long trajectories, but on high-end sensors most people will
never touch. Neither is a good benchmark for the case that actually dominates in practice:
long-duration navigation on cheap, noisy, MEMS-grade hardware.

This dataset splits the difference. It is collected on what is plausibly the most ubiquitous
sensor configuration in existence — the MEMS IMU and GNSS receiver in a modern smartphone —
over trajectories long enough to be comparable to marine and aerospace collections.

Raw collections include accelerometer, gyroscope, magnetometer, gravity, barometer,
orientation, and WGS84 GNSS fixes, downsampled and time-synchronized. On top of those, the
repository ships processed scenarios generated through
[strapdown-sim]({{ base_path }}/portfolio/strapdown-rs) covering the failure modes that
alternative-PNT research actually needs to test against:

| Scenario | What it models |
|---|---|
| `baseline` | Standard closed-loop INS with GNSS updates, no degradation |
| `sched_10s`, `duty_10on_2of` | Fixed-interval and duty-cycled GNSS availability |
| `degraded_fullrate`, `degraded_5s` | Correlated measurement noise and inflated covariance |
| `slowbias`, `slowbias_rot` | Slow drifting bias, with and without platform rotation |
| `hijack` | Spoofing: a constant offset injected over a fixed interval |
| `combo`, `combo_duty_hijack` | Combined degradation, intermittency, and spoofing |

The intent is that this is usable both as a teaching dataset and as a shared baseline, so that
GNSS-denied and GNSS-degraded navigation results become comparable across papers.

### Citation

<!-- TODO(james): mint a DOI for this — Zenodo will archive a GitHub release and issue one in
     about five minutes, and a citable DOI is most of what makes a dataset get cited rather
     than reimplemented. Then replace the `note` field below with `doi`. -->

```bibtex
@misc{brodovsky_mems_nav_dataset,
  author = {Brodovsky, James},
  title  = {{MEMS Navigation Dataset}},
  year   = {2025},
  howpublished = {\url{https://github.com/jbrodovsky/mems-nav-dataset}},
  note   = {Zenodo DOI forthcoming}
}
```
