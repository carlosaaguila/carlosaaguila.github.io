---
layout: page
title: Interictal Spike Analysis
description: ML models using spatial spike patterns to localize the seizure onset zone without capturing seizures.
img: assets/img/projects/spike_gradient.png
importance: 1
category: Research
related_publications: true
---

Drug-resistant epilepsy affects roughly one-third of patients with the condition. For those who qualify for surgery, identifying _where_ to resect requires capturing actual seizures during an inpatient hospital stay — a process that is slow, costly, and sometimes inconclusive.

My work asks whether the brain's resting activity — specifically brief electrical discharges called **interictal spikes** — can replace or reduce this reliance on ictal recordings. Spikes happen continuously between seizures and encode spatial information about the epileptogenic network.

**Key findings:**

- Mesial-to-lateral spike gradient patterns distinguish mesial temporal lobe epilepsy from other epilepsy subtypes
- Spike asymmetry on scalp EEG can non-invasively lateralize temporal lobe epilepsy across large cohorts
- Spike rates are not meaningfully modulated by anti-seizure medication taper, making them a stable biomarker
- Spike burden correlates with seizure frequency in a large multi-site cohort (n > 3,000)

**Methods:** Mixed-effects classifiers, logistic regression, survival analysis, automated spike detection with morphology annotation, Python / MATLAB / R.

**Status:** Two first-author papers published; additional co-authored work published and in submission.

{% cite aguila2025mesial %}
