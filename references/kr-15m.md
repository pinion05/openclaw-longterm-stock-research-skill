# Korea (KR) checklist (login‑free, filing‑first)

## Goal
Assess whether a Korean stock is investable for mid/long-term holding using public, no-login sources.

## Non‑negotiables (KR)
- **DART filings MUST be opened via the interactive browser tool.**
- Do **NOT** use scripts (`exec`/curl/python) to substitute for reading filings.
- If DART cannot be accessed in-browser: **STOP → return Low confidence** (filing-first is non-negotiable).

## URLs (copy/paste)
- DART: https://dart.fss.or.kr/
- KIND: https://kind.krx.co.kr/
- FnGuide (company): https://comp.fnguide.com/
- Yahoo Finance (KR ticker):
  - KOSPI: `https://finance.yahoo.com/quote/<CODE>.KS`
  - KOSDAQ: `https://finance.yahoo.com/quote/<CODE>.KQ`

## Sources
- DART: primary filings and disclosures
- KIND: exchange notices/events (nice-to-have; may be flaky)
- FnGuide: fundamentals + valuation snapshot (PER/PBR, financial highlights)
- Yahoo Finance: market context (price, market cap, return, basic ratios, cash-flow summaries)
  - KR tickers often use suffix: KOSPI `.KS`, KOSDAQ `.KQ` (e.g., `003720.KS`)

---

## Phase 1 | Ticker confirmation gate (avoid same-name traps)
- Confirm **company name + stock code** first.
- Translate to Yahoo ticker:
  - KOSPI → `NNNNNN.KS`
  - KOSDAQ → `NNNNNN.KQ`
- Record at top of notes: `Target: <회사명> (<코드>, <야후티커>)`.

## Phase 2 | Snapshot gate (Yahoo + FnGuide)
- Yahoo (Summary): price, market cap, 52w range, volume/avg volume, 1Y return.
- Headline cluster:
  - Prefer DART “recent disclosures” titles as the **most reliable KR headline cluster**.
  - Yahoo “news” for KR tickers may be sparse/irrelevant → treat as **weak signal**.
- Valuation snapshot:
  - Prefer FnGuide for **PER/PBR** (Yahoo KR fundamentals can be missing or inconsistent).
  - If Yahoo vs FnGuide valuation metrics diverge materially: **call it out + downgrade confidence**.

## Phase 3 | Growth quality (FnGuide first)
- FnGuide: 5-year trend for revenue, operating income, ROE.
  - Prefer consistency over one-off spikes.
  - Note cyclicality explicitly.

## Phase 4 | Balance-sheet resilience (Yahoo + FnGuide)
- Leverage direction (debt ratio, cash vs debt, current ratio).
- Cash-flow quality:
  - Flag mismatch: earnings up but operating cash flow weak.

## Phase 5 | Filing-first risk scan (DART) — REQUIRED
Review at least 10–20 recent filing headlines.
- Dilution risk: rights offering, CB/BW issuance.
- Governance/legal risk: lawsuits, sanctions, management turbulence.
- Reporting quality risk: corrections/restatements, audit issues.

**Must-open items (when present):**
- Auditor report / 감사보고서: opinion (적정/한정/부적정), going-concern wording, internal-control issues.
- Major M&A / 타법인주식취득: purchase price, funding (cash/borrowings), collateral/guarantees, closing conditions.

**Automation note (practical):**
- DART viewer often renders the main content inside an **iframe**. If you only see header/toc, re-capture iframe content.

## Phase 6 | Event cross-check (KIND) + decision
- KIND: exchange-side events (trading halts, inquiries, warnings) + near-term catalysts.
- If KIND is down:
  - Use DART exchange-origin filings (조회공시요구/답변) as a partial proxy.
  - Explicitly note “KIND unavailable”.

Finalize:
- Pass / Watch / Drop
- One concrete next trigger (earnings, specific filing, guidance, event)

---

## KR-specific red flags
- Frequent correction disclosures.
- Repeated equity-linked dilution.
- Material governance instability.
- Deteriorating operating cash flow despite reported profit.

## Service-outage fallback rules (report this explicitly)
- If **Yahoo fails** → proceed with FnGuide + DART; downgrade confidence.
- If **FnGuide fails** → proceed with Yahoo + DART; downgrade confidence.
- If **KIND fails** → proceed without it; note missing event cross-check.
- If **DART fails** → stop and return **Low confidence**.

## Minimum output (KR)
- Decision + confidence
- 3 supporting reasons (with source tags: DART/FnGuide/Yahoo)
- Red flags list
- Next review trigger/date window
