---
title: "strapdown-rs — Strapdown inertial navigation in Rust"
collection: portfolio
permalink: /portfolio/strapdown-rs
excerpt: 'A Rust library and simulator for strapdown INS: WGS84 mechanization, EKF/UKF navigation filters, and simulation of GNSS degradation, spoofing, and outage. On crates.io; JOSS submission in review.'
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
  forward mechanization, and navigation filters (EKF, UKF) for estimating position, velocity,
  and attitude from IMU data.
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

<!-- TODO(james): the JOSS submission is in review
     (https://joss.theoj.org/papers/5079592cc860d1435482a4a7764edcd4).
     Once it's accepted, add the DOI and a citation block here, and add the paper to
     _publications/. -->
