# U.S. (US) checklist (login‑free, filing‑first)

## Goal
Assess whether a U.S. stock is investable for mid/long-term holding using public, no-login sources.

## Non‑negotiables (US)
- **SEC EDGAR filings MUST be opened via the interactive browser tool.**
- Do **NOT** use `web_fetch` on `sec.gov`.
- Do **NOT** use `exec`/curl/python scraping to substitute for reading filings.
- If you cannot access filings in-browser: stop and return **Low confidence**.

## Sources
- SEC EDGAR: primary filings (10-K, 10-Q, 8-K, S-3/F-3, 424B* prospectus supplements, DEF 14A)
- Yahoo Finance: broad financial and market snapshot
- Finviz: screening metrics and cross-checks

## Phase 1 | Snapshot gate
- Market cap, valuation context, and recent headline concentration.
- Confirm business category/sector and peer context quickly.

## Phase 2 | Growth quality
- Multi-year trend for revenue and operating/net profitability.
- Prefer stable compounding patterns over volatile spikes.
- Note margin durability if visible.

## Phase 3 | Financial resilience
- Debt load vs cash-generation quality (FCF direction).
- Flag prolonged weak FCF with rising leverage.
- Avoid relying on one metric alone.

## Phase 4 | Filing-first risk scan (EDGAR) — REQUIRED
Open and scan in-browser (minimum coverage):
1. **Latest 10-K** (risk factors, liquidity, dilution, share count, SBC, warrants/convertibles)
2. **Latest 10-Q** (updated cash burn, share count changes, financing)
3. **Recent 8-Ks** (material events; acquisitions; guidance; auditor matters)
4. **Capital-raising / dilution trail**: S-3/F-3 + 424B* (ATM, shelf, prospectus supplements)
5. **DEF 14A** (governance/comp/related-party signals)

Keyword scan (search within filing page if possible):
- going concern
- material weakness
- at-the-market / ATM
- shelf registration / S-3
- dilution / equity offering
- warrant / convertible
- litigation / investigation

## Phase 5 | Decision
- Finalize Pass / Watch / Drop.
- Record a specific next trigger (earnings call, filing, guidance update).

## US-specific red flags
- Going-concern or severe internal-control weakness.
- Repeated equity issuance without visible operating improvement.
- Material legal/regulatory overhang with unclear resolution path.

## Minimum output (US)
- Decision + confidence
- 3 supporting reasons (each tagged: Filing/Yahoo/Finviz)
- Red flags list
- Next review trigger/date window
