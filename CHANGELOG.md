# Changelog

## 1.3.1 — 2026-10-14

- Personal identifiers (SI number, date of birth, account numbers, ID numbers) are typed
  into the form by the user, never asked for in chat; Claude only checks the fields.
- The View errors page is marked read-only.
- New `references/sources.md` inside the skill, so the source links travel with it
  (references no longer point to the repository README).
- Browser skill names are examples only (`built-in-browser`, `chrome-browser`,
  `claude-in-chrome`); a missing browser skill no longer blocks step 0.

## 1.3.0 — 2026-10-14

- New step 7 in SKILL.md: check for errors after filling in — run Calculation of
  TOTALS, compare every entered figure with the T.D.63 certificates, read the GHS /
  tax / SDC calculation (line 10B, caps), report one list of problems and fix them
  after the user's "yes", then repeat until nothing is left.
- Step 8: after the user presses Final submission, read the result; if TAXISnet shows
  errors, fix them and ask the user to submit again; confirm the status in the history.
- Navigation checked on the live site: direct `/epr1/...` links give "Invalid flow";
  go via Returns → View (history, read-only) or Submit (edit mode). Buttons and their
  behaviour documented in `taxisnet-notes.md`, plus errors TAXISnet does not catch.
- README: how to use the skill with other agents (Codex, Gemini, Cursor…).
- How TAXISnet reports errors (ERRORS IN THE RETURN → View errors pop-up → Continue);
  code-9 rows keep the months column empty; T.D.63 euros and cents in separate columns.

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
