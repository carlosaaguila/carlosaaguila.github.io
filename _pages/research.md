---
layout: page
title: Research
permalink: /research/
nav: true
nav_order: 2
---

My research develops computational tools that extract clinically actionable information from intracranial EEG (iEEG) — electrical recordings made directly from the brain in patients undergoing presurgical epilepsy evaluation.
The central question: can we replace or reduce the need to capture actual seizures by instead analyzing the brain's resting activity?

---

## Mesial-to-Lateral Spike Gradients for TLE Localization

Interictal spikes (IEDs) are brief electrical discharges that occur between seizures and reflect the spatial organization of the epileptogenic network.
I developed a classifier that uses spatial gradient patterns of spike activity — specifically the mesial-to-lateral distribution across hippocampal and neocortical contacts — to localize mesial temporal lobe epilepsy (mTLE) without requiring ictal recordings.

This work was published in _Epilepsia_ (2025): [DOI 10.1111/epi.18462](https://doi.org/10.1111/epi.18462)

**Methods:** Mixed-effects models, automated spike detection with morphology annotation, Python / MATLAB.

---

## Low-Frequency Stimulation and Interictal Spikes as an Excitability Biomarker

Low-frequency stimulation (LFS, 1 Hz) is used therapeutically in epilepsy, but its effects on the underlying epileptogenic network are poorly characterized.
I am building a pipeline to characterize how LFS acutely modulates interictal spike rates across the epileptogenic network — and whether spike rate changes can serve as a real-time biomarker of network excitability.

Preliminary findings show that effects are heterogeneous: mesial temporal structures are more vulnerable to stimulation-induced spike modulation than lateral neocortex, suggesting a network-level excitability gradient that mirrors the spatial patterns in the localization work above.

**Methods:** Time-series analysis, mixed-effects models, stimulation artifact rejection, Python / MATLAB.

**Status:** In preparation.

---

## Automated Seizure Onset Pattern Classification with YOLOv8

Seizure onset patterns (SOPs) — the electrographic signature of the first seconds of a seizure — carry prognostic information about seizure type, localization, and surgical outcome.
Currently, SOPs are classified manually by epileptologists, limiting scalability.

I am training YOLOv8, a real-time object detection model, to classify five SOP classes directly from iEEG image representations, enabling automated large-scale SOP annotation across institutional datasets.

**Methods:** YOLOv8 object detection, transfer learning, iEEG image preprocessing, Python.

**Status:** In preparation.
