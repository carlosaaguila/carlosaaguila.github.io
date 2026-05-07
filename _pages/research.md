---
layout: page
title: Research
permalink: /research/
nav: true
nav_order: 2
---

My research develops computational tools that extract clinically actionable information from intracranial EEG (iEEG) — electrical recordings made directly from the brain surface in patients undergoing presurgical epilepsy evaluation. The overarching goal: reduce the time, cost, and risk of epilepsy surgery workups while improving surgical outcomes.

---

## Interictal Spike Analysis for Surgical Planning

The central thread of my PhD. Interictal spikes (IEDs) are brief electrical discharges that occur between seizures and encode spatial information about the epileptogenic network. I have developed machine learning models that use spike morphology, rate, and spatial gradient patterns to localize the seizure onset zone — the region of brain responsible for generating seizures.

This work asks: can automated, large-scale analysis of resting brain activity replace or reduce reliance on capturing actual seizures during monitoring? If so, it could shorten hospital stays and reduce the need for high-risk ictal recordings.

**Key contributions**: mesial-to-lateral spike gradient classifier for mesial temporal lobe epilepsy; analysis of how stimulation acutely modulates spike rates across the epileptogenic network; large-cohort analysis of the relationship between spike burden and seizure frequency.

---

## Epileptic Network Mapping

Epilepsy is a network disease — seizures emerge from distributed brain circuits, not isolated regions. I characterize these networks using both spontaneous interictal activity and ictal (seizure) recordings, applying unsupervised deep learning, graph-theoretic connectivity measures, and normative atlases to identify abnormal network signatures.

**Key contributions**: collaboration on a spatiotemporal transformer for characterizing seizure onset at scale across hundreds of patients; normative iEEG atlas localizing epileptic abnormalities across sleep/wake states; characterization of how preprocessing choices affect network-based biomarkers.

---

## Cortical Stimulation & Evoked Potentials

Electrical stimulation allows us to _probe_ the epileptic network rather than passively observe it. I build analysis pipelines for cortico-cortical evoked potentials (CCEPs) and low-frequency stimulation trials, studying how the epileptogenic network responds to perturbation and how stimulation devices interact with interictal activity.

---

## Scalable Clinical Tools & Next-Generation Devices

Translating research findings into tools and devices that work at clinical scale. This includes automated seizure onset pattern classification using computer vision (YOLOv8 on iEEG images), electrode montage reduction for sub-scalp wearable devices, scalp EEG biomarkers for non-invasive lateralization, and an implantable device that uses conversational AI to co-manage epilepsy with patients.

---

## Selected Publications

See the [Publications](/publications/) page for a full list.

- **Aguila CA** et al. (2025). Mesial-to-lateral gradients of epileptiform activity to localize mesial temporal lobe epilepsy. _Epilepsia_. [DOI: 10.1111/epi.18462](https://doi.org/10.1111/epi.18462)
- Conrad EC, Lucas A, Ojemann WKS, **Aguila CA** et al. (2024). Interictal intracranial EEG asymmetry lateralizes temporal lobe epilepsy. _Brain Communications_.
- Pattnaik AR, Ong IZ, **Aguila CA** et al. (2025). Normative Intracranial EEG Localizes Epileptic Abnormalities Across States of Wakefulness. _Annals of Neurology_.
