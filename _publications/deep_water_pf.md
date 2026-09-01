---
title: "A Deep Water Bathymetric Particle Filter for Position Estimation in GNSS-Denied Environments"
collection: publications
permalink: /publication/deep-water-pf
excerpt: 'A particle filter that provides operationally relevant navigation aiding to an inertial navigation system via bathymetric map matching, on long-duration open-ocean missions rather than short shallow-water ones.'
date: 2024-06-05
venue: 'ION Joint Navigation Conference'
paperurl:
citation:
---

<!--
TODO(james): this entry needs a decision. It sat on the site for over a year as
"Paper currently under review" against a 2024-01-01 date, with an empty paperurl and
citation, which means _includes/archive-single.html rendered no link at all.

I have set date/venue to the JNC 2024 presentation, which is the one thing I can verify.
Pick whichever is true and fill in paperurl + citation:
  - published in NAVIGATION: Journal of the ION  -> update venue, date, DOI, citation
  - published in the JNC 2024 proceedings        -> add the ION digital library URL
  - still under review                           -> say where, and give it a real date
  - withdrawn / superseded by the dissertation   -> delete this file
-->

This work assesses the viability of a particle filter to provide long-term, operationally
relevant navigation aiding to an inertial navigation system via bathymetric map matching.
Prior work demonstrated accurate position estimation from bathymetric depth measurements on
small autonomous platforms, but typically in shallow coastal water over short missions. This
implementation produces useful position estimates for long-duration open-ocean missions,
recovering position from a de-localized inertial navigation system at maximum drift error and
at times estimating position below the map-pixel resolution.
