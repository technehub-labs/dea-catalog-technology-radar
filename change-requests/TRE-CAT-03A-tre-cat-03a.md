# TRE-CAT-03A: TechnologyRadarEntry Candidate Corpus

**Status**: Landed (this PR)
**Layer**: Catalog content (candidate corpus intake)
**Owner**: Emmanuel A. Otchere
**Date**: 2026-11-15
**Admission authority**: candidate corpus only (canonical admission remains the evidence-gated step; FOUNDATIONS D-4/D-5)
**Trigger**: Catalog population programme (2026-11 owner directive): advance 10 foundational skeleton catalogs with evidence-backed candidate corpora (>=1,000 each) through a gated intake workflow. Technology-radar is third: the CNCF Landscape (cncf/landscape hosted YAML) is the candidate seed source named per FOUNDATIONS §7.
**Carrier**: Single PR on feature branch `feat/tre-cat-03a`. PR review, not direct push.
**Lands against**: `main`
**Depends on**: TRE-CAT-02 (ingestion groundwork).

## 1. What this CR lands

**2442 TechnologyRadarEntry candidate submissions** in `contributions/queue/<shard>/<slug>.yaml` from 1 evidence bank(s):

| Bank | Source | Records |
|---|---|---|
| cncf-landscape.json | CNCF Landscape (cncf/landscape hosted YAML) | 2442 |

Provenance in `ingestion/manifest.yaml` (bank sha256s, source URLs, retrieval dates, mapping note). Every submission carries `source_ref`, a `published-document` evidence citation, and published description prose. Provisional field mappings are documented per record and in the manifest; per-organization values are canonical-admission decisions.

> Correction note: an earlier CR-TRE-CAT-03 (PR #5) landed with 0 submissions — the evidence bank was empty at generation time (fetcher defect, fixed). This CR supersedes it with the populated corpus; CR-TRE-CAT-03's text is immutable (landed CRs are not edited).

## 2. What changes

- `contributions/queue/<shard>/` — 2442 intake submissions (`status: queued`)
- `ingestion/manifest.yaml` — corpus provenance record (new)
- No `CATALOG.yaml` change (queue ≠ index)
- This CR file and the index row

## 3. Verification

- `check_contributions.py`: CONFORMANT (2442 queue files)
- No directory holds 800+ entries (slug-prefix distribution)
- Spot-checks: records trace to their published source identifiers

## 4. NOT-List

- NOT record admission (nothing under `entities/` changes; admission follows in TRE-CAT-04+).
- NOT a modification of gates, schemas, or intake tooling.
- NOT an authoritative assessment of provisional mapped values.

## 5. Acceptance criteria

1. 2442 gate-CONFORMANT submissions; manifest carries bank sha256s + source URLs.
2. Submissions carry no `id`; `status: queued`; `submitted_by: Emmanuel A. Otchere`.
3. `CATALOG.yaml` counts unchanged.
