---
layout: page
title: Seizure Annotation Web App (AWS)
description: A browser-based tool for clinicians to label seizure onset patterns, deployed on AWS to crowdsource a multi-site annotation dataset.
img:
importance: 1
category: Software
github: https://github.com/carlosaaguila/sz-gui
---

**sz-gui** is a tool I built so epileptologists can label seizure onset patterns directly in the browser — no install, no local data handling. Clinicians log in, scroll intracranial EEG, mark the seizure onset zone, and annotate the onset pattern of each contact; everything saves to a database and resumes where they left off. It started as a PyQt5 desktop app, and I ported it to a full web stack so it can be shared with collaborators anywhere.

## Architecture

I designed and provisioned the whole stack on AWS with Terraform and GitHub Actions, kept deliberately minimal — five services, reproducible from `terraform apply` + `git push`.

```
Browser
  → CloudFront (CDN, TLS)
      → S3 frontend bucket (private, React build)
      → EC2 (nginx → gunicorn → Flask)
          → PostgreSQL (annotations)
          → S3 EDF bucket (private, EEG files)
```

A React single-page app is served from a private S3 bucket through CloudFront; API calls route through CloudFront to a Flask/gunicorn backend on EC2, which reads EEG from a private S3 bucket and writes annotations to PostgreSQL. Patient EEG is de-identified before it ever leaves the local machine, and both S3 buckets stay private.

## The plan

The web app exists to solve a data problem: seizure onset patterns are read by eye, one clinician at a time, so labeled data is scarce and single-site. The goal is to **annotate ~400 seizures with epileptologists from different institutions across the country** and assemble the result into a multi-site **seizure onset pattern dataset** — ground truth for training and validating automated onset-pattern classifiers.

Repo: [github.com/carlosaaguila/sz-gui](https://github.com/carlosaaguila/sz-gui).
