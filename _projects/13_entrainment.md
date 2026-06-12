---
layout: page
title: Spike Entrainment
description: Do interictal spikes phase-lock to 1 Hz stimulation? Treating the epileptic cortex as a driven oscillator.
img: assets/img/projects/entrainment_polar.png
importance: 5
category: Research
related_publications: false
---

This is my current first-author project. It asks a sharper question than "does stimulation change spike rates": **do interictal spikes become _phase-locked_ to the stimulation pulse train?** If they do, the epileptic cortex is behaving like a driven oscillator, and the degree of locking becomes a physiologically grounded measure of excitability — one that connects clinical low-frequency stimulation to the entrainment literature in Parkinson's disease and to the physics of forced oscillators.

I measure phase concentration of each spike relative to the 1 Hz pulse cycle using **pairwise phase consistency (PPC)**, an N-unbiased phase-locking metric, aggregated hierarchically up to one value per patient per period (pre / during / post / inter-stim). Cortico-cortical evoked potentials are removed first so that passive evoked responses cannot masquerade as entrainment.

{% include figure.liquid loading="eager" path="assets/img/projects/entrainment_ppc.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Patient-level pairwise phase consistency is highest during 1 Hz stimulation compared with pre, post, and inter-stimulation periods." %}

<div class="caption">
  Patient-level spike-to-pulse phase consistency (PPC) rises sharply during 1 Hz stimulation and returns to baseline afterward (during ≫ inter, Wilcoxon p ≈ 3.5 × 10⁻⁶).
</div>

**Key findings so far:**

- **Spikes entrain.** Spike-to-pulse PPC is far higher _during_ stimulation than at any other period, robust across spike-count thresholds.
- **Distance, not pathology, sets the response.** Stimulation-to-spike latency is governed by inter-electrode distance (~0.3–0.5 m/s conduction), and entrainment is _not_ a global marker of epileptic pathology.
- **The seizure onset zone entrains _less_.** Within patients, SOZ channels show weaker locking than non-SOZ channels — concordant with the idea that pathological tissue is already locked to its own endogenous rhythms.
- **A minimal model is sufficient.** A driven excitable unit (Poisson firing + refractory period + a post-pulse excitability kick), fit on rate and geometry alone — never on phase — reproduces the observed during ≫ inter locking, the latency–distance slope, and cross-patient variation.

{% include figure.liquid loading="lazy" path="assets/img/projects/entrainment_polar.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Polar histograms of spike phase within the pulse cycle: concentrated during stimulation, near-uniform inter-stimulation." %}

<div class="caption">
  Spike phase within the 1 Hz pulse cycle, pooled across pairs. During stimulation (left) phases concentrate near a preferred angle (mean PLV 0.379, PPC 0.081); between stimulation trains (right) the distribution is far closer to uniform (PPC ≈ 0).
</div>

**Methods:** Circular statistics (PPC, PLV, Rayleigh), hierarchical aggregation, Monte-Carlo surrogate nulls, CCEP latency rejection, forced-oscillator and phase-oscillator (Adler / Arnold-tongue) modeling, Python.

**Status:** In progress. Builds directly on the [Cortical Stimulation & Evoked Potentials](/projects/cortical-stimulation-evoked-potentials/) work.
