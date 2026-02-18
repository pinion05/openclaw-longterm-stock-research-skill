---
name: longterm-stock-research
description: Run a login-free, evidence-first long-term stock research workflow for Korean and U.S. equities. Use when a user asks for structured stock due diligence, KR/US 15-minute research routines, pass/watch/drop decisions, or reusable checklists that prioritize fundamentals, filings, and risk flags over short-term price action.
---

# Longterm Stock Research

## Overview
Evidence-first long-term stock research for KR/US equities.

**Default mode is meticulous.** The “15m” framing is a *minimum baseline*, not a reason to stop early.

## Non‑negotiables
### 1) Filings must be opened in a browser (no exceptions)
- **SEC EDGAR (US) and DART (KR) filings MUST be accessed via the interactive `browser` tool** (headful).
- **Never use `web_fetch` for `sec.gov`** (commonly 403-blocked).
- **Never use `exec`/curl/python scraping as a substitute** for opening filings.
- If filings cannot be opened in the browser: **STOP → return `Decision: Drop` + `Confidence: Low`** and state the access failure.

### 2) Depth over speed
- Ignore time pressure. Always do the full checklist + filing risk scan.
- If data is missing, say so explicitly and downgrade confidence.

## Workflow
1. Identify market (`KR` or `US`).
2. Open primary filings **in the browser** (see market checklist for what to prioritize).
3. Follow the market checklist:
   - KR: `references/kr-15m.md`
   - US: `references/us-15m.md`
4. Score the company with `references/scoring-template.md`.
5. Apply hard-stop overrides.
6. Output using the contract below.

## Evidence rules
- Prefer primary filings over commentary.
- For each key point, label the source: `Filing` (EDGAR/DART) vs `Financial statements` vs `Secondary`.
- Treat severe governance/accounting/dilution signals as override risks even when headline growth looks strong.
- If key metrics disagree across sources (e.g., Yahoo vs FnGuide valuation), call it out and downgrade confidence.

## Hard-stop risk overrides
Apply immediate **Drop** (or equivalent) when any of these appear and are unresolved:
- Auditor or going-concern red flags.
- Material internal-control weakness without credible remediation.
- Repeated dilutive financing that undermines long-term shareholder value.
- Major unresolved legal/regulatory risk likely to impair operations.

## Output contract
Always end with:
1. `Decision:` Pass / Watch / Drop
2. `Confidence:` High / Medium / Low
3. `Top 3 Reasons:`
4. `Red Flags:`
5. `Next Review Trigger:` (earnings, filing, guidance, or event)

## References
- `references/kr-15m.md` — Korea checklist (DART/KIND/FnGuide/Yahoo Finance).
- `references/us-15m.md` — U.S. checklist (EDGAR/Yahoo/Finviz).
- `references/scoring-template.md` — 100-point weighting and decision thresholds.
