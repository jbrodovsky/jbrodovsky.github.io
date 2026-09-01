---
title: "strapdown-rs — Strapdown inertial navigation in Rust"
collection: portfolio
permalink: /portfolio/strapdown-rs
excerpt: 'A Rust library and simulator for strapdown INS: WGS84 mechanization, full-state UKF and particle filter implementations, and simulation of GNSS degradation, spoofing, and outage. On crates.io; software paper under review at JOSS.'
---

{% include base_path %}

[Repository](https://github.com/jbrodovsky/strapdown-rs) ·
[Documentation](https://www.strapdown.rs) ·
[API docs](https://docs.rs/strapdown-core) ·
[crates.io](https://crates.io/crates/strapdown-core)

`strapdown-rs` is a strapdown inertial navigation system implementation in Rust, built for
research, teaching, and integration into real systems. It targets the low size, weight, and
power domain — phones, drones, small UAVs and UUVs — where MEMS-grade sensors and their error
characteristics dominate the navigation problem.

The project is organized as four crates:

* **`strapdown-core`** — the library: a WGS84 Earth model, the standard nine-state strapdown
  forward mechanization, and full-state navigation filters — an unscented Kalman filter and a
  particle filter — for estimating position, velocity, and attitude from IMU data.
* **`strapdown-sim`** — a command-line INS simulator. Runs open-loop dead reckoning or
  closed-loop filtering, and simulates the GNSS conditions that actually matter: intermittent
  availability, duty cycling, correlated-noise degradation, slow bias, and spoofing.
* **`strapdown-data`** — smartphone-collected MEMS IMU and GNSS data.
* **`strapdown-geonav`** — geophysical anomaly aiding (gravity and magnetic), built behind a
  feature flag. This is the active research edge.

Design priorities are correctness, numerical stability, and extensibility — the base
mechanization and filters are meant to be a foundation you build aiding algorithms on top of,
not a black box. It is deliberately not a full-featured INS: there is no raw IMU or GNSS
signal processing, and the integration is loosely coupled.

```bash
cargo add strapdown-rs        # library
cargo install strapdown-sim   # simulator
```

Planned: an error-state formulation, plus C and Python bindings.

The accompanying software paper is
[under review at JOSS]({{ base_path }}/publication/strapdown-rs-joss).
