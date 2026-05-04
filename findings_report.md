# CSRD Coherence Audit — Comparative Findings

**Pipeline:** ESRS E1 + EU Taxonomy extraction + cross-disclosure coherence audit using Claude Sonnet 4.6 on AWS Bedrock.

**Companies analyzed:** Unilever (FY2024), Schneider Electric (FY2024). Source: published Annual Reports / Universal Registration Documents.

**Approach:** automated PDF section detection → structured data extraction → LLM-based coherence reasoning across two related disclosures.

---

## Unilever PLC

**Coherence verdict:** LOW

Unilever presents a highly detailed and ambitious ESRS E1 climate narrative — including SBTi-validated targets, a net-zero 2039 commitment, and a multi-lever transition plan — that is structurally disconnected from its EU Taxonomy disclosure, which shows 0% aligned capex, 0% aligned turnover, and 0% aligned opex. The gap between stated decarbonization ambition and Taxonomy-verifiable investment is not adequately explained by the company's sector-framing argument, and the asymmetry in disclosure depth between the two sections suggests they are prepared to different standards of scrutiny. Taken together, the disclosures risk creating a misleading impression of progress: the E1 section reads as a credibility statement while the Taxonomy section reveals an absence of externally verifiable, criteria-tested climate investment.

### Headline numbers

| Metric | Value |
|---|---|
| Scope 1 (tCO2e) | 480000 (p.248) |
| Scope 2 market-based (tCO2e) | 210000 (p.248) |
| Scope 3 total (tCO2e) | 53800000 (p.248) |
| Capex Taxonomy-eligible % | 15.1 (p.266) |
| Capex Taxonomy-aligned % | 0 (p.266) |
| Turnover Taxonomy-aligned % | 0 (p.266) |

### Top coherence findings (6 HIGH severity, 9 total)

**1. Transition Plan Coherence**
The ESRS E1 transition plan identifies solar PV, heat pumps, bioenergy, energy efficiency, and vehicle electrification as key decarbonization levers. All five of these map directly to eligible EU Taxonomy activities (CCM 4.1, 4.16, 4.24, 7.3, and 6.5 respectively) that Unilever itself identifies in its Taxonomy disclosure. Yet aligned capex for every one of these activities is 0%. This means the company acknowledges deploying capital into these activities but cannot or will not demonstrate that it meets the Taxonomy's technical screening criteria for substantial contribution.

**2. Target Vs Investment**
Unilever holds SBTi-validated targets for 100% Scope 1+2 reduction by 2030 (vs. 2015) and 42% Scope 3 E&I reduction by 2030. These are among the most aggressive near-term science-based targets in the FMCG sector. However, the Taxonomy discloses zero euros of climate-aligned capital expenditure in 2024, and zero eligible turnover or opex. The complete absence of Taxonomy-aligned investment in a year when the 2030 target horizon is only six years away represents a material disconnect between stated ambition and verifiable investment behaviour.

**3. Target Vs Investment**
The CNF (Clean Future) transition fund is cited in ESRS E1 as growing from €0.3bn to €0.7bn in commitments since 2020, with €0.4bn added in 2024 for upstream value chain investments. This is presented as evidence of climate-aligned capital deployment. However, none of this spend appears to translate into Taxonomy-aligned capex — suggesting either that CNF spend does not meet Taxonomy technical screening criteria, or that the company has not attempted to map CNF expenditures to Taxonomy activities and document compliance.

**4. Methodology Asymmetry**
The ESRS E1 disclosure is materially more rigorous than the Taxonomy disclosure across every dimension of analytical depth. ESRS E1 includes: KPMG-limited-assured GHG data, twelve Scope 3 category disclosures with data quality flags, SBTi validation references, baseline restatements, and biogenic emission footnotes. The Taxonomy disclosure spans approximately three pages, contains boilerplate DNSH language applied generically rather than per activity, a minimum safeguards statement with no named HRDD process, and a single sentence explanation for zero alignment. This asymmetry is structurally suspicious — it suggests the Taxonomy section has received substantially less internal governance attention.

**5. Red Flag**
Activity CCM 7.7 (Acquisition and ownership of buildings) accounts for 13.3% of the 15.1% total eligible capex — meaning 88% of all eligible capex is concentrated in a passive property-holding activity that requires no operational decarbonization effort. Only 1.8% of total capex is attributed to active climate-transition activities (solar PV, heat pumps, bioenergy, energy efficiency, vehicle electrification, building construction/renovation). This profile is inconsistent with a company executing an ambitious near-term decarbonisation transition plan and raises questions about whether the eligible capex figure is itself substantive or primarily driven by property accounting.

### Disclosure quality flags surfaced

- ESRS E1: 10 flags
- EU Taxonomy: 7 flags
- Coherence cross-check: 9 findings


---

## Schneider Electric

**Coherence verdict:** MEDIUM

Schneider Electric's ESRS E1 and EU Taxonomy disclosures are directionally consistent — both anchor the sustainability narrative around electrical infrastructure, energy efficiency, and decarbonisation of the built environment — but a structural coherence gap exists between the ambition of the E1 transition plan and the relatively low 22% Taxonomy-aligned CapEx ratio. The most significant coherence tension is that 90% of revenues are eligible under the Taxonomy yet only 28% are aligned, a gap that is largely explained by the conservative non-alignment of CE 1.2 (35% of revenues), but which is not adequately cross-referenced or reconciled in the E1 narrative. Methodology depth is notably asymmetric: E1 climate data carries reasonable assurance on Scope 1 and 2 and contains granular GHG accounting, while several Taxonomy DNSH assessments rest on qualitative assertions without activity-level substantiation.

### Headline numbers

| Metric | Value |
|---|---|
| Scope 1 (tCO2e) | 106360 (p.150) |
| Scope 2 market-based (tCO2e) | 37348 (p.150) |
| Scope 3 total (tCO2e) | 55649186 (p.150) |
| Capex Taxonomy-eligible % | 71 (p.161) |
| Capex Taxonomy-aligned % | 22 (p.161) |
| Turnover Taxonomy-aligned % | 28 (p.159) |

### Top coherence findings (5 HIGH severity, 12 total)

**1. Transition Plan Coherence**
E1 discloses EUR 41.6M current CapEx aligned to transition plan decarbonisation levers (primarily electrification EUR 39.8M and SF6 phase-down EUR 14.4M — noting the arithmetic sum exceeds the reported total, itself an internal inconsistency). The Taxonomy reports EUR 161M CapEx aligned to CCM activities in 2024 (21% of EUR 2,421M total CapEx per p.161). These two figures are not reconciled anywhere in the disclosure. The EUR 41.6M is described as transition-plan CapEx for Scope 1 and 2 only, while the EUR 161M Taxonomy-aligned CapEx includes broader manufacturing and product-range investments. The absence of a bridge between these two figures leaves stakeholders unable to verify whether the transition plan investment is a subset of or additive to Taxonomy-aligned CapEx.

**2. Target Vs Investment**
E1 targets a 76% absolute Scope 1+2 reduction by 2030 vs. 2021 (SBTi-validated, 1.5°C-aligned) and EUR 400M in transition CapEx over 2024-2030. At EUR 400M over 6 years (~EUR 67M/year), this represents approximately 2.8% of annual CapEx (EUR 2,421M) dedicated to the own-operations decarbonisation pathway. Given that Scope 1+2 (market-based) is already only 143,708 tCO2eq — 0.26% of total GHG footprint — the absolute emissions reduction from this investment is inherently small relative to the headline net-zero narrative. The Taxonomy 22% aligned CapEx ratio signals that the majority of CapEx flows into potentially aligned but not yet confirmed activities, primarily CCM 7.7 buildings (24% of CapEx, EUR 587M, non-aligned) and CE 1.2 manufacturing (14% of CapEx, non-aligned). This creates a narrative tension: E1 projects transformational decarbonisation ambition while Taxonomy shows less than a quarter of CapEx fully meeting alignment criteria.

**3. Red Flag**
The E1 disclosure reports EUR 41.6M current 2024 CapEx aligned to the transition plan, with a breakdown of EUR 39.8M for electrification and EUR 14.4M for SF6 phase-down. The arithmetic sum of EUR 39.8M + EUR 14.4M = EUR 54.2M exceeds the stated total of EUR 41.6M by EUR 12.6M (approximately 30%). No reconciliation note is provided. This internal arithmetic inconsistency in the E1 transition CapEx disclosure calls into question the reliability of the investment figures used to support the transition plan's financial credibility and makes it impossible to verify whether the EUR 400M 2024-2030 figure is consistently derived.

**4. Red Flag**
The E1 disclosure flags that LTIP 2024 carbon targets were revised mid-cycle in February 2025 because the Scope 3 upstream intensity target was deemed unreachable partly due to expanded CSRD reporting scope. Simultaneously, Scope 3 upstream categories show large year-on-year increases (Category 2 +191%, Category 3 +146%) attributed to methodology changes. These methodology changes, which drove executive compensation target revisions, are not reflected as formal restatements in the Taxonomy disclosure's CapEx or turnover templates. If the expanded CSRD scope changes the boundary of reportable activities, the Taxonomy KPI denominators may also require restatement, but no such restatement or sensitivity analysis is provided in the Taxonomy section.

**5. Red Flag**
The Taxonomy discloses that 14% of revenues are non-aligned due to PPC DNSH non-compliance (RoHS exemptions, REACH candidate substances), yet the E1 disclosure contains no corresponding reference to chemical substance risks as a climate or sustainability risk driver, and the E1 transition plan contains no lever addressing hazardous substance substitution. This creates a one-directional disclosure: Taxonomy acknowledges a material non-alignment driver (14% of revenues, potentially EUR 5.3B) that is entirely absent from the E1 narrative, suggesting the two disclosures were prepared with limited cross-referencing between the ESRS and Taxonomy teams.

### Disclosure quality flags surfaced

- ESRS E1: 8 flags
- EU Taxonomy: 10 flags
- Coherence cross-check: 12 findings


---

## Comparative observations

The same pipeline surfaces fundamentally different *categories* of disclosure issues depending on company profile:

- **Sector-mismatched reporters (Unilever, FMCG):** Failure modes concentrate around transition-plan-vs-alignment gaps, contradictory sector-framing explanations, and 0%-aligned activities that map to stated transition levers.
- **Sector-aligned reporters (Schneider, industrial electrification):** Failure modes concentrate around intra-disclosure arithmetic errors, cross-team coordination gaps, methodology denominator inflation, and missing reconciliation between framework-specific quantifications of the same underlying activities.

Both verdicts (LOW for Unilever, MEDIUM for Schneider) are substantively defensible. Total compute cost: under $1.00 per company.
