---
layout: page
title: Epileptic Network Mapping
description: Characterizing distributed epileptogenic networks using unsupervised deep learning and normative iEEG atlases.
img:
importance: 2
category: Research
related_publications: false
---

Epilepsy is a network disease. Seizures emerge from distributed brain circuits — not a single point — making characterization of the full network essential for surgical planning and device therapy.

I contribute to projects that map these networks using both spontaneous (interictal) and ictal (seizure) recordings:

**Seizure embedding map:** A spatiotemporal transformer trained on 882 seizures from 110 patients that learns a continuous representation of seizure onset patterns, enabling unsupervised clustering and within-patient tracking of ictal evolution over time.

**Normative iEEG atlas:** A normative dataset of 106 seizure-free subjects used to identify which brain regions in an epilepsy patient fall outside the normal range — with sleep state as a critical moderating variable.

**Neural dynamic divergence:** An unsupervised approach to modeling ictal state transitions, achieving AUROC 0.87 for detecting seizure onset without manual annotation.

**Preprocessing robustness:** Systematic analysis of how re-referencing and connectivity choices affect network-based biomarkers across 48 pipelines and 125 patients.

**Methods:** Spatiotemporal transformers, graph-theoretic connectivity, unsupervised clustering, normative modeling, Python / TensorFlow.
