# CSRD Coherence Audit

**An LLM pipeline that audits coherence between ESRS E1 climate disclosures and EU Taxonomy disclosures in published CSRD reports.**

Most automated CSRD tooling focuses on extracting numbers from disclosures. This project explores a different question: **do the numbers, narratives, and methodology choices in different parts of the same report tell a coherent story?**

The pipeline ingests a published CSRD-aligned annual report, extracts structured data from both the ESRS E1 (climate change) section and the EU Taxonomy section, then runs an LLM-based coherence audit across the two — surfacing contradictions, methodology asymmetries, and ambition-vs-investment gaps that human reviewers typically catch only after hours of careful reading.

Built with Claude Sonnet 4.6 on AWS Bedrock.

---

## Why this matters

CSRD compliance is becoming the dominant European sustainability disclosure regime — ~11,700 companies in wave 1 alone. The bottleneck isn't extraction (which is increasingly a commodity capability); it's **whether disclosures hold up under scrutiny**. Auditors, activist investors, and regulators read these reports forensically. Sustainability teams typically don't, because the cost of doing so manually is prohibitive.

This pipeline brings that forensic audit capability inside the reach of any sustainability team's pre-publication QA process.

**Two framings, same tool:**
- *External research framing:* point it at published reports → identify disclosure quality issues for analysts, investors, NGOs.
- *Customer-facing framing:* point it at draft disclosures before publication → surface the specific questions auditors and activist investors will ask, with page references, while there's still time to fix or prepare answers.

The customer-facing framing is the more interesting product opportunity. The cost economics (under $1.00 per company per audit) make it practical to run continuously across a customer's entire CSRD draft cycle.

---

## What it does

For any company's CSRD-aligned report, the pipeline:

1. **Extracts text** from the PDF and identifies ESRS E1 and EU Taxonomy sections via keyword scoring.
2. **Calls Claude** to extract structured data + self-reported quality flags from each section. Both prompts request page citations on every numeric value and refuse to guess.
3. **Cross-references the two outputs** in a third call, asking Claude to evaluate coherence: do transition levers in E1 correspond to Taxonomy-aligned activities? Do aggressive 2030 targets show up in current Taxonomy-aligned capex? Is one section meaningfully more rigorous than the other?
4. **Returns a verdict** (HIGH / MEDIUM / LOW coherence) plus specific findings, evidence, and a list of follow-up questions an analyst would put to management.

Total cost per company: **$0.30–$0.66** depending on report size.

---

## Findings on two real companies

Both companies analyzed using the same pipeline, no custom logic:

### Unilever PLC (FY2024) — Coherence: LOW
- 305-page Annual Report
- 0% Taxonomy-aligned capex despite a detailed, SBTi-validated transition plan
- 9 specific coherence findings (6 HIGH severity)
- Flagged: same activities (solar PV, heat pumps, vehicle electrification) named as transition levers in E1 but 0% aligned in Taxonomy. Two contradictory explanations for non-alignment on the same page. 88% of "eligible" capex is passive building ownership.

### Schneider Electric (FY2024) — Coherence: MEDIUM
- 676-page Universal Registration Document
- 22% Taxonomy-aligned capex, 28% aligned turnover
- 12 specific coherence findings (5 HIGH severity)
- Flagged: arithmetic inconsistency in transition capex breakdown (€39.8M + €14.4M ≠ €41.6M). 14% of revenue non-aligned due to chemical substance compliance issues, completely absent from the E1 transition plan narrative — strongly suggesting the ESRS and Taxonomy teams worked in isolation.

**The comparative insight:** the two companies fail coherence in *fundamentally different categories*. Sector-mismatched reporters (Unilever, FMCG) fail on transition-plan-vs-alignment gaps and contradictory sector-framing. Sector-aligned reporters (Schneider, industrial) fail on intra-disclosure arithmetic and cross-team coordination. Different risk profiles call for different audit-readiness checks. The same pipeline catches both.

See `findings_report.md` for the full comparative report.

---

## How it's built

Deliberately simple. No vector DB, no RAG, no agent framework. The point was to understand the data problem before reaching for fancy infrastructure.

The three prompts are the engineering work. They are saved as numbered `.txt` files in this repo for inspection.

---

## Repo contents

- `notebook.ipynb` — the full pipeline as a Colab notebook
- `01_esrs_e1_extraction.txt`, `02_eu_taxonomy_extraction.txt`, `03_coherence_crosscheck.txt` — the three Claude prompts as standalone text files
- `findings_report.md` — the comparative findings report across both companies
- `*_e1.json`, `*_taxonomy.json`, `*_crosscheck.json` — structured extractions for each company analyzed
- `requirements.txt` — Python dependencies

---

## Limitations and what I'd build next

This is a weekend prototype, not a production tool. Real limitations:

1. **Keyword-based section detection is brittle.** Different report formats (Universal Registration Document vs. Annual Report vs. standalone Sustainability Report) structure these sections differently. A production version would use document layout analysis or an LLM-based section classifier.
2. **Two extractions, one cross-check.** Real CSRD coherence audit would extend across all 12 ESRS standards plus Taxonomy plus the financial statements. Same pipeline shape, more pairings.
3. **No evaluation framework.** I have anecdotal evidence the cross-check produces useful findings on two companies. Production deployment requires a benchmark dataset of disclosures with known issues, and systematic measurement of recall on those issues.
4. **No audit trail logging.** Production sustainability tooling needs full reproducibility — model version, prompt version, source document hash, every reasoning step. Trivial to add.

If I were continuing this in a customer-facing role, the highest-leverage extensions would be (a) building the eval benchmark, (b) extending coverage to all ESRS standards, and (c) integrating with sustainability teams' pre-publication review workflows so findings can be triaged and routed to the right disclosure owner.

---

## About this project

Built as a portfolio piece by Ketki Sawant ([LinkedIn](https://www.linkedin.com/in/ketki-sawant-335aba1b5/)). I spent two years at Morningstar Sustainalytics on EU Taxonomy and reporting frameworks, and I'm now pursuing a Master of Quantitative Economics at UCLA. This project sits at the intersection of those two things: domain depth on the disclosure regimes, plus AI tooling for the parts of the workflow that don't scale with human effort.
