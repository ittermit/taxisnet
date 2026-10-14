# TAXISnet: practical notes

From the Tax Department's 2025 guide and "common mistakes" page, TAXISnet's own FAQ and
general TAXISnet instructions (VAT / Intrastat), plus practitioner guides — see the
sources in the repository README. Exact labels can differ — always read the page.

## Access

- Site: https://taxisnet.mof.gov.cy — use Chrome or Firefox.
- TAXISnet has two separate systems, **VAT** and **Income Tax**, with **different
  credentials**. The return is in the Income Tax system.
- The interface defaults to Greek. Switch with "EN" / "English" in the top bar; some
  screens may switch back to Greek.
- Locked out / forgotten password: the user uses "Forgot password" on the login page
  or contacts the Tax Department (helpline 17700). Never handle credentials yourself.

## Time limit on forms

TAXISnet forms are time-limited (the VAT/Intrastat instructions state **30 minutes**
per form; a temporary save restarts the timer). Unsaved data is lost when the time runs
out. On a long return, suggest a temporary save every section or two — with the user's
agreement.

## Saving and statuses

| Action / status | Greek label | Meaning |
|---|---|---|
| Temporary save | Προσωρινή Φύλαξη | Saved with its own number, still editable, only basic checks. **Not filed.** |
| Temporary receipt | Σε Προσωρινή Παραλαβή | Status of a temporarily saved return. **Not filed.** |
| Final submission | Οριστική Υποβολή | Full validation; if no errors, the return is filed and gets an acceptance number. |
| Submitted | ΥΠΟΒΛΗΘΗΚΕ | The return is filed. Check that this status is shown. |

- A return left only temporarily saved after the deadline counts as **not filed** and
  the late-filing charge applies.
- Final submission is done **only by the user**.
- TAXISnet shows a unique acceptance (receipt) number on final submission; the
  acceptance date is the filing date. An electronic return is as valid as paper — do
  not also send a paper form.

## Menus

- Returns list: "Υποβολή/Προβολή Δηλώσεων" (Submit / View returns) → "Προβολή
  (Ιστορικό δηλώσεων)" (history) → click the return number to open it.
- The skill's direct links:
  - list: https://taxisnet.mof.gov.cy/epr1/processAllEPR1DocumentList.do?dispatch=find&epr1Type=epr1m-declarations
  - new return for a previous year: https://taxisnet.mof.gov.cy/epr1/choosePrevTaxYearsForEPR1.do
- Printing a filed return: open it from the history and use the browser's print.

## Prefilled data

- Social Insurance / Treasury retrieval (first screen) fills pensions, self-employed
  income and contributions — only for SI/Treasury pensioners and registered
  self-employed. Requires SI number, date of birth DD/MM/YYYY (as in the SI register)
  and sex. If retrieval fails, the date of birth is the usual culprit.
- Employer TIC and name, and insurer details are carried over from the previous year's
  return — they may be outdated; fix them from the current T.D.63.
- Self-assessed SDC/GHS payments appear in the calculation automatically and can only
  be reduced.

## Employer data (IR63 / T.D.63)

- **There is no function that downloads IR63 amounts.** The employee gets the
  certificate of emoluments T.D.63 (IR63) from each employer and the figures are
  entered in Part 4A1, one row per employer (see `official-guide-2025.md`).
- If the user does not have their T.D.63, they ask the employer for it. Do not estimate.
- Benefits in kind not subject to Social Insurance → a separate row with code 9.

## Entering numbers

- Whole euros everywhere, except **withheld** tax / GHS / SDC: exact with cents and a
  **comma** as decimal separator.
- TICs: last character is a capital Latin letter.
- Clearing a prefilled row: also clear its code (blank option in the drop-down).
- Blue column headers open explanations — read them when unsure.

## Calculation

- The calculation pages (GHS, income tax / self-assessment, SDC) are reached with
  **SELF-ASSESSMENT / CONTRIBUTIONS** (ΥΠΟΛΟΓΙΣΜΟΣ ΦΟΡΟΥ/ΕΙΣΦΟΡΩΝ).
- Things the user may need to enter there: losses from previous years, foreign tax
  credit on foreign rent, non-dom exemption years for SDC (after form T.D.38).
- If withheld SDC amounts do not match the system's half-year split, refundable cents
  appear and the return cannot be submitted — adjust the withheld amounts to the split.
- Sanity-check the result against `rules-2025.md`.

## After the final submission (done by the user)

- Save the acceptance number.
- Amounts due appear in the Tax Portal (taxportal.mof.gov.cy) under the statement of
  amounts due; the user pays there by 31 October 2026.
- Corrections within the deadline: revert to temporary ("Μεταβολή σε ΠΡΟΣΩΡΙΝΗ"),
  correct, and submit finally again — see `official-guide-2025.md`.
- Keep supporting documents for at least 6 years.
