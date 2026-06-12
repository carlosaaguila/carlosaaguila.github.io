---
layout: page
title: Seizure Annotation Web App (AWS)
description: A clinician-facing web tool for per-contact seizure onset annotation, deployed end-to-end on AWS with Terraform and CI/CD.
img:
importance: 1
category: Software
github: https://github.com/carlosaaguila/sz-gui
---

**sz-gui** is a tool I built so epileptologists can label seizure onset patterns directly in the browser — no install, no local data handling. It started as a PyQt5 desktop app and I ported it to a full web stack (React + Flask + PostgreSQL) running on AWS. Clinicians log in, scroll intracranial EEG, mark the seizure onset zone, and annotate the onset pattern of each contact; everything saves to a database and resumes where they left off.

The interesting part is the infrastructure. I designed and provisioned the whole cloud stack myself with Terraform and GitHub Actions, deliberately keeping it minimal — five AWS services, ~$10–15/month, reproducible from `terraform apply` + `git push`.

## Architecture

```
Browser
  → CloudFront (CDN, free TLS on *.cloudfront.net)
      → S3 frontend bucket (private, React build, OAC-gated)
      → EC2 t3.micro (nginx :80 → gunicorn :5000 → Flask)
          → localhost PostgreSQL (annotations)
          → S3 EDF bucket (private, instance-role-gated, EEG files)
```

API traffic goes `Browser → CloudFront /api/* → EC2`. CloudFront terminates TLS and forwards the `Authorization` header so JWTs pass through; the EC2 only ever speaks plain HTTP internally.

## Stack

| Layer            | Technology                                      | Notes                                                      |
| ---------------- | ----------------------------------------------- | ---------------------------------------------------------- |
| Frontend         | React (Plotly.js for EEG rendering)             | Single-page app, built to static assets                    |
| Backend          | Flask + gunicorn (1 worker × 4 threads)         | nginx reverse proxy in front                               |
| Database         | PostgreSQL on the EC2 (not RDS)                 | Local DB saves ~$15/mo at this scale                       |
| EEG storage      | S3, private, EC2 IAM role with `GetObject` only | EDFs streamed to disk to avoid OOM on t3.micro             |
| Frontend hosting | S3 + CloudFront, private bucket via OAC (SigV4) | SPA routing handled at the edge                            |
| Infrastructure   | Terraform, `dev` / `prod` workspaces            | Remote state in S3                                         |
| CI/CD            | GitHub Actions — 2 workflows                    | Frontend: S3 sync + invalidation; backend: rsync + systemd |

## Engineering decisions

- **No RDS, no Elastic Beanstalk, no Fargate.** A single EC2 with local Postgres covers 5–10 concurrent clinicians and avoids $15–25/mo of managed-service overhead. Few moving parts, one box to SSH into and debug.
- **Memory hardening on a 1 GB instance.** EDF files are streamed from S3 to local disk rather than loaded into RAM, the EEG cache evicts down to a single recording, and a 1 GB swapfile absorbs spikes — together these eliminated the 502s I was hitting on `t2.micro`.
- **Privacy by default.** Both S3 buckets are private, the database listens only on `localhost`, and IAM follows least privilege. Patient EEG is de-identified with HMAC-SHA256 _before_ upload, with the key kept only on the local machine and no stored mapping — so no coded data ever lands on AWS.
- **Reproducible.** Terraform plus GitHub Actions means the entire environment can be torn down and rebuilt from version-controlled config.

## Status

AWS `dev` environment live; production Terraform workspace and a custom domain are the remaining steps. Built and maintained solo. Repo: [github.com/carlosaaguila/sz-gui](https://github.com/carlosaaguila/sz-gui).
