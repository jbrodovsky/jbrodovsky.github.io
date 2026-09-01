---
title: "A Priori Prediction of Geophysical Anomaly Navigation Fixability via Posterior Cramér-Rao Bounds and Machine Learning"
collection: publications
pubtype: review
status: "Under review"
permalink: /publication/geo-fixability
excerpt: 'Predicting achievable navigation accuracy from trajectory and map characteristics before the mission, using posterior Cramér-Rao bounds and a learned regression model.'
date: 2026-07-01
venue: 'IEEE Transactions on Aerospace and Electronic Systems'
paperurl:
citation: 'Brodovsky, J. &quot;A Priori Prediction of Geophysical Anomaly Navigation Fixability via Posterior Cram&eacute;r-Rao Bounds and Machine Learning.&quot; <i>IEEE Transactions on Aerospace and Electronic Systems</i> (under review).'
---

<!-- TODO(james): the `date` here is a placeholder for sorting only — set it to the actual
     submission date. On acceptance, move pubtype to `journal`, drop `status`, add the DOI. -->

Geophysical map matching works, but not everywhere. This work predicts *where* it will work:
relating vehicle trajectory characteristics and geophysical map properties to achievable
navigation accuracy, using the Fisher information matrix and the posterior Cramér-Rao bound as
theoretical limits and a learned regression model to generalize from them. The result behaves
like a sensor specification — given this trajectory over this map, position is bounded to
within a stated precision — which makes geophysical aiding something that can be budgeted for
in advance rather than tried and measured after the fact.

Supporting code: [geo-fixability]({{ site.url }}/portfolio/geo-fixability).
