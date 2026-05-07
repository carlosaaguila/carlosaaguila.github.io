# CLAUDE.md — aguila-website

## About the Owner

Carlos Aguila. PhD candidate, Bioengineering, UPenn (expected Fall 2026). Computational neuroscience + ML + clinical epileptology. This repo is his personal GitHub website.

## Primary Knowledge Source

**Career wiki**: `/Users/carlosaguila/Documents/career-wiki/`

Use this as ground truth for anything about Carlos — bio, publications, research themes, voice/style, collaborators, institutions, career goals.

| Need | Go to |
|------|-------|
| Full bio, CV, experience | `wiki/people/carlos-aguila.md` |
| Writing voice for first-person content | `wiki/people/carlos-voice.md` — **read before drafting any personal-voice text** |
| Research themes & papers | `wiki/overview.md` or `wiki/papers/` |
| Career goals / job targets | `wiki/career/` |
| Concepts (iEEG, spikes, SOZ, etc.) | `wiki/concepts/` |
| All wiki entry points | `wiki/index.md` |

If wiki lacks info: **ask Carlos directly**.

---

## Cross-Repository Work Protocol

This repo (aguila-website) may need content, copy, or data from other repos or the career wiki. Follow this system:

### 1. Read Before Writing
Before drafting any bio, blurb, project description, or personal statement — read `wiki/people/carlos-voice.md` and `wiki/people/carlos-aguila.md`. Never invent facts.

### 2. Sourcing Hierarchy
```
1. wiki/               ← canonical facts, voice, publications
2. raw/                ← source documents (CV PDFs, letters, etc.)
3. Ask Carlos          ← anything absent or ambiguous
```

### 3. Linking Across Repos
When pulling content from the wiki into this website:
- Treat wiki files as read-only source of truth — do not edit them here
- If you update a fact in the website, flag that the wiki may need updating too
- Path convention: always use absolute paths when referencing wiki (`/Users/carlosaguila/Documents/career-wiki/...`)

### 4. Content Freshness
Wiki `log.md` tracks last-ingest dates. If a wiki page's last-updated date is stale relative to what Carlos tells you, ask him to update the wiki first, then build from it.

### 5. When to Ask vs. When to Read
- **Read wiki**: publications, dates, affiliations, technical details, writing style
- **Ask Carlos**: opinions, priorities, current feelings on a topic, anything the wiki marks as "TBD" or "in prep"

---

## Repo Purpose

Personal GitHub website. Likely content: bio, research summary, publications list, CV/resume link, contact. Should reflect Carlos's professional identity as a computational neuroscientist and PhD candidate.
