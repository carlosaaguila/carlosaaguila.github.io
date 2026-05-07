---
layout: page
permalink: /cv/
title: CV
nav: true
nav_order: 3
---

<div class="cv-toggle mt-3 mb-4">
  <button id="btn-cv" class="btn btn-sm z-depth-0 cv-btn active" onclick="showDoc('cv')">CV</button>
  <button id="btn-resume" class="btn btn-sm z-depth-0 cv-btn" onclick="showDoc('resume')">Résumé</button>
  <a id="download-link" href="/assets/pdf/Aguila_CV.pdf" class="btn btn-sm z-depth-0 cv-btn ml-3" target="_blank">Download</a>
</div>

<iframe id="cv-frame" src="/assets/pdf/Aguila_CV.pdf" width="100%" height="900px" style="border: none;">
  Your browser does not support PDFs.
  <a href="/assets/pdf/Aguila_CV.pdf">Download the CV</a>.
</iframe>

<style>
  .cv-toggle { display: flex; gap: 0.5rem; align-items: center; }
  .cv-btn { border: 1px solid var(--global-theme-color) !important; }
  .cv-btn.active {
    background-color: var(--global-theme-color) !important;
    color: #fff !important;
  }
</style>

<script>
  function showDoc(type) {
    var pdf = type === 'cv' ? '/assets/pdf/Aguila_CV.pdf' : '/assets/pdf/Aguila_Resume.pdf';
    document.getElementById('cv-frame').src = pdf;
    document.getElementById('download-link').href = pdf;
    document.getElementById('btn-cv').classList.toggle('active', type === 'cv');
    document.getElementById('btn-resume').classList.toggle('active', type === 'resume');
  }
</script>
