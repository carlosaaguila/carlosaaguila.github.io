---
layout: page
title: Cortical Stimulation & Evoked Potentials
description: Using 1 Hz stimulation to probe regional excitability, spike entrainment, and effective connectivity in the epileptic brain.
img: assets/img/projects/stim_spikes.png
importance: 2
category: Research
related_publications: false
---

Rather than passively observing the epileptic network, electrical stimulation lets me actively probe it — revealing the excitability, connectivity, and vulnerability that resting-state recordings alone cannot capture. This is the core of my first-author work.

**Stimulation drives spikes through regional excitability.** In 43 patients undergoing intracranial EEG, I showed that 1 Hz low-frequency stimulation (LFS) acutely increases nearby interictal spike rates, and that the size of that increase tracks _intrinsic regional excitability_ — largest in the mesial temporal lobe — rather than epilepsy-specific pathology. Stimulation-evoked spikes do not localize the seizure onset zone better than resting spike rates, but they do shift spike morphology toward broader, higher-amplitude discharges, consistent with recruitment of a wider neuronal population. The practical upshot: stimulation-induced spiking is a real-time readout of network excitability, which is directly relevant to how closed-loop devices should be programmed.

{% include figure.liquid loading="lazy" path="assets/img/projects/stim_spikes.png" class="img-fluid rounded z-depth-1" zoomable=true alt="1 Hz cortical stimulation paradigm: detecting interictal spikes pre, during, and post stimulation and measuring spike rate for every recording-stimulation channel pair." %}

<div class="caption">
  1 Hz, 30 s cortical stimulation trains; interictal spikes are detected pre-, during, and post-stimulation and spike rate is computed for every recording–stimulation channel pair across mesial temporal, neocortical, and other-cortex sites.
</div>

**Cortico-cortical evoked potentials (CCEPs).** I also separate stimulation-_entrained_ spikes from CCEPs — the direct evoked network response — by modeling evoked amplitude, latency, and morphology as a function of inter-electrode distance and brain state. This keeps the entrainment analysis from being confounded by passive evoked potentials and gives a clean measure of effective connectivity between stimulated and recorded regions.

**Preprint:** Aguila et al., _Regional excitability, not epileptic pathology, drives stimulation-evoked interictal spike increases_ — medRxiv (2026). _Link forthcoming._

**Methods:** Peri-stimulation spike detection with artifact interpolation, CCEP rejection, mixed-effects and random-forest models, Python / MATLAB.

Related: see [Spike Entrainment](/projects/spike-entrainment/) for the phase-locking analysis that builds directly on this work.
