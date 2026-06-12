---
layout: page
title: iEEG Spike Detector & Morphology
description: A Python package for detecting interictal spikes and quantifying their morphology, tuned for low-frequency stimulation studies.
img:
importance: 2
category: Software
github: https://github.com/carlosaaguila/spike_detector
---

A single Python package for the two things every spike-based analysis I run depends on: **detecting** interictal epileptiform discharges in intracranial EEG, and **quantifying their morphology**. Detection is validated against epileptologist review (PPV ≈ 0.90 on the cohort used in the _Epilepsia_ paper) and the parameters are tuned for low-frequency stimulation experiments, where spikes have to be separated cleanly from stimulation artifact.

The morphology side extracts the features that change as epileptiform activity propagates from mesial to lateral temporal structures — sharp-wave rising/falling amplitude and slope, sharpness, line length, and slow-wave amplitude and width. These are the inputs to the mesial-to-lateral gradient classifier for localizing mesial temporal lobe epilepsy, and to the stimulation and entrainment work.

**Repo:** [github.com/carlosaaguila/spike_detector](https://github.com/carlosaaguila/spike_detector)
