# Changelog

## 1.2.0 — 2026-10-14

- New `official-guide-2025.md`: the Tax Department's official 2025 form guide, part by
  part (first-screen retrieval, Part 4A1 columns and employment codes 1–14, rent,
  interest, dividends, other income, Part 5 deductions, Part 6, GHS / tax / SDC
  calculation pages, IBAN, payment codes, correction procedure).
- Corrected: TAXISnet has **no automatic IR63 download** — figures are entered from the
  employee's T.D.63 certificates. SKILL.md step 4 rewritten accordingly.
- Rules updated from the official guide: 1/5 cap on net income, 2% cap for medical funds
  and private health insurance, life-insurance details, official exemption codes and
  conditions (20% / 50% / 25% talent repatriation), interest and dividends not subject
  to income tax, SDC refund for incomes up to €12,000, non-dom (T.D.38) handling,
  short-term rentals, GHS 4% on self-employed profit, IBAN and personal details only via
  Tax For All.
- TAXISnet notes: Greek status labels (temporary save vs final submission,
  "ΥΠΟΒΛΗΘΗΚΕ"), form time limit, number formats, correcting after final submission.
- The user ticks the Part 6 declaration themselves.
- README: official sources added.

## 1.1.0 — 2026-10-14

- Added reference files to the skill:
  - `rules-2025.md` — deadline (31 October 2026), filing threshold, 2025 tax bands,
    deductions and the 1/5 cap, 2026-only deductions to avoid, 20% / 50% exemptions,
    SDC and GHS rates, residency, payment via the Tax Portal;
  - `taxisnet-notes.md` — language, session timeouts, temporary vs final submission,
    prefilled data, IR63, calculation, after submission;
  - `checklist.md` — questions to ask the user.
- SKILL.md now uses these files: deadline check, rule checks on deductions, sanity
  check of the calculation, handling of "temporary submission" returns, Tax For All
  note for tax year 2026+.
- README: sources section, updated layout and limitations.

## 1.0.0 — 2026-10-14

- Initial release: `cyprus-tax-declaration` skill for preparing the TD1 / EPR1 return
  for the previous tax year in TAXISnet via the browser (user sign-in, IR63 retrieval
  for one or more employers, form filling with confirmation, self-assessment, user
  submits).
- Claude Code plugin and marketplace manifests.
- English and Russian README.
