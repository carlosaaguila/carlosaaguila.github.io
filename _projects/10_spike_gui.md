---
layout: page
title: Spike Annotation GUI
description: A PyQt5 tool for clinicians to manually mark interictal spikes around stimulation, used to validate the automated detector.
img: assets/img/projects/spike_gui.png
importance: 3
category: Software
---

A desktop annotation tool I built so epileptologists can manually mark interictal spikes in peri-stimulation iEEG — the ground truth I use to validate and tune the automated [spike detector](/projects/ieeg-spike-detector-morphology/). It generates de-identified annotation clips (10 s pre / 30 s during / 11 s post stimulation, bipolar montage, 60 Hz notch + 1–70 Hz bandpass), serves them in a reviewer-friendly interface, and exports per-channel spike labels for analysis.

{% include figure.liquid loading="eager" path="assets/img/projects/spike_gui.png" class="img-fluid rounded z-depth-1" zoomable=true alt="Spike Annotation GUI: a 15-second bipolar iEEG window with red dashed 1 Hz stimulation markers and blue triangles marking annotated spikes." %}

<div class="caption">
  The annotation interface (from the supplement of the stimulation study). Red dashed lines mark the 1 Hz stimulation pulses; blue triangles are reviewer-marked spikes. A toggle switches between the raw signal and the interpolated signal the detector actually sees.
</div>

**Features:** bipolar montage rendering, raw-vs-interpolated signal toggle, adjustable gain, click-to-mark spikes, scrollable 15 s window over the full clip, automatic resume from the first uncompleted file, and JSON export with per-period breakdown.

**Code:** part of my stimulation-responses project (private). Available on request.
