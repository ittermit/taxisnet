# Official form guide 2025 — part by part

Summary (in our own words) of the Tax Department's "Guide for completing the
Individual Income Tax Return 2025" (Οδηγός Συμπλήρωσης Δήλωσης Εισοδήματος Ατόμου
2025, 24 pages, June 2026) and its "What to watch out for — common mistakes" page.
Links are in the repository README. The guide is informational and does not replace
the law. Greek labels are given so you can find them on the page.

## General entry rules

- **Amounts are rounded to whole euros**, without decimals — **except** amounts of tax,
  GHS (ΓεΣΥ) and SDC (ΕΑΕ) **withheld**, which are entered exactly, with cents, using a
  **comma** as decimal separator (e.g. `1234,56`), not a dot.
- Tax identification numbers (ΑΦΜ / TIC) of employers, banks etc.: the **last
  character is a capital Latin letter**.
- Most column headers are blue links with explanations and examples — read them when a
  field is unclear.
- To remove a prefilled row you disagree with, also clear its **code** (pick the blank
  option in the drop-down), not only the amounts.
- Sanity limits checked by the system: tax withheld must not exceed 35% of the declared
  income; GHS withheld on salary must not exceed 2.65% of it.

## First screen — Social Insurance / Treasury retrieval (ΑΝΑΚΤΗΣΗ ΣΤΟΙΧΕΙΩΝ ΥΚΑ/ΓΛ)

- Answer **Yes** only if the user receives a pension from Social Insurance (ΥΚΑ) or the
  Treasury (ΓΛ), or is registered as self-employed with Social Insurance. Otherwise
  **No**.
- If Yes, the user's Social Insurance number, date of birth (DD/MM/YYYY, same as in the
  Social Insurance register) and sex are needed; the system then fills pension (4Β1),
  self-employed income, GHS and Social Insurance contributions (5Γ).
- If "No" was chosen by mistake, double-click "ΑΝΑΚΤΗΣΗ ΣΤΟΙΧΕΙΩΝ ΥΚΑ/ΓΛ" at the top
  of the return to go back.
- Self-employed income retrieved this way makes Part 4Θ mandatory.

## Parts 1–2 — Personal details and representative

- Not editable in the return. Address, phone, email and representatives are changed
  **only in Tax For All** (profile, or form T.D.2003 via "Inbox → New message").

## Part 3 — Tax residency and GHS

- **3A Residency.** Resident if more than 183 days in Cyprus in 2025, or the 60-day
  rule (≥60 days, permanent home owned/rented in Cyprus, not >183 days and not tax
  resident elsewhere, business/employment/office in Cyprus not terminated by
  31/12/2025). Residents declare income from **inside and outside** Cyprus;
  non-residents only Cyprus income and choose their country of residence.
- **3B1** is filled automatically (from the retrieval above).
- **3B2 Insured in another EEA country / Switzerland / exempt organisation:** choose
  the country and the document giving the GHS exemption (S1, A1, other certificate).
- **3B3** GHS-type contributions paid to another country's health scheme in 2025 — for
  the corresponding relief.

## Part 4 — Income

### 4A1 Employment (from the employer's certificate T.D.63 / IR63)

One row per employer:

| Column | What to enter |
|---|---|
| 1 Employer TIC | The **employer's** TIC from T.D.63, not the user's own. Fix it if last year's prefilled value is wrong. Not needed for code 5 (unemployed) or employers abroad (codes 2, 4). |
| 2 Employer name | As on T.D.63; "ΑΝΕΡΓΟΣ" if unemployed. |
| 3 Code | See codes below. |
| 4 Office holder | "Yes" only for directors/secretaries etc. for pay not subject to Social Insurance. |
| 5 Months | Months worked for that employer (13th salary is not a month). |
| 6 Gross pay in Cyprus | Whole euros. Benefits in kind not subject to Social Insurance go in a **separate row with code 9**. |
| 7 Gross pay abroad | For codes 2 and 4. |
| 8 Tax withheld | Exact, with cents, comma. |
| 9 GHS withheld | Exact, with cents, comma. |
| 10–11 | Employment period, only for code 12 started in 2025. |

Employment codes:

- **1** — employment in Cyprus (normal case).
- **2** — employment abroad with physical presence abroad (remote work done while in
  Cyprus is **not** code 2).
- **3** — 20% exemption (max €8,550), employment started **up to 25/07/2022**, non-
  resident in the year before; 5 years.
- **4** — work abroad for a non-resident employer (or a PE abroad) for more than 90
  days in the year — exempt.
- **5** — unemployed periods (do not enter unemployment benefit here).
- **6** — 50% exemption, old rule (pay over €100,000, employment started up to
  25/07/2022), 10 years.
- **7** — benefit from loans to directors/shareholders.
- **8** — carried interest / performance fees (8%, minimum tax €10,000).
- **9** — benefits in kind on T.D.63 not subject to Social Insurance (car, rent…).
- **12** — 50% exemption, employment started 01/01/2022–29/06/2023 (non-resident ≥10
  years before; pay over €55,000; up to 17 years), plus transitional cases.
- **13** — 50% exemption, employment started from 30/06/2023 (non-resident and no
  Cyprus employment for 15 consecutive years before; pay over €55,000; up to 17 years),
  plus transitional cases.
- **14** — 20% exemption (max €8,550), first employment started **from 26/07/2022**,
  after at least 3 consecutive years working abroad for a non-resident employer; 7
  years from the year after the start.

Remote work for a foreign employer while resident in Cyprus is taxable in Cyprus and
goes in 4A1 with code 1 (or 3/6/12/13/14 if an exemption applies). Employer TIC is not
needed if a GHS exemption type is chosen in 3B2 or foreign social insurance is entered
in 5Γ code 6.

### 4A2 Income with codes 3, 6, 12, 13, 14

Mandatory when one of those codes is used: date of settling in Cyprus, date employment
started (and departure date for codes 3/6), days outside Cyprus in the year before (codes
3/6), and the questions for the code chosen. The exemption amount is filled
automatically and must **not** be claimed again in Part 5.

### 4A3 / 4Β2 Arrears

Mainly public servants and public-service pensioners; mandatory to answer if income is
declared.

### 4Β Pensions

Social Insurance / Treasury pensions come from the retrieval. Others are entered
manually (TIC, name, code, gross amount, tax and GHS withheld). Foreign pension: code 2
(reduced 5% rate above €3,420, not added to other income) or code 8 (normal rates) — all
foreign pensions use the same code.

### 4Γ Rent

- Long-term rent in Cyprus and abroad. **Short-term rentals (Airbnb, Booking…) are not
  here** — they go in 4Θ.
- Per property: title registration number, property code (gives the capital allowance
  rate: 3% office/shop/flat/house; 4% warehouse/factory/hotel; 0% land, parking, other),
  completion and acquisition dates, acquisition cost of the building **without land**
  and not the Land Registry valuation, area in m², tenant TIC (only for companies /
  state, as on form E.Πρ.614/2019), tenant name, ownership share %, ownership at
  31/12/2025.
- **Gross** annual rent (Cyprus / abroad) for the user's share; the 20% expense
  deduction is applied automatically (not for land/parking/other codes).
- Loan interest for buying/building the rented property is fully deductible.
- Foreign tax paid on foreign rent (exact, with cents).
- SDC and GHS withheld by company/state tenants only (codes 614/714); self-assessed SDC
  and GHS paid for individual tenants come in automatically — do not enter them here.
- SDC: 3% on 75% of gross rent, paid half-yearly (30 June, 31 December). GHS: 2.65% on
  gross rent.

### 4Δ Listed (preserved) building

Only with the completion certificate from the Town Planning Department.

### 4Ε Interest received

- Residents declare Cyprus and foreign interest. Interest is **not** subject to income
  tax, only to SDC and GHS.
- Codes: 1 loans/other (17%, not withheld); 2 government and corporate bonds (3%
  withheld); 3 bank deposits etc. (17% withheld); 4 other securities (17% withheld);
  5 foreign sources (17%, not withheld).
- User's share of gross interest per bank/debtor; foreign tax (code 5); SDC and GHS
  withheld (exact); date received; for foreign interest also country, account type and
  account number.
- If total income (including interest) is **not more than €12,000**, the SDC withheld on
  deposit interest is refunded automatically — only if this part is filled in.

### 4ΣΤ Dividends

- Residents declare Cyprus and foreign dividends: not subject to income tax, but to SDC
  and GHS.
- Codes: 1 Cyprus companies; 2 foreign companies; 3 tonnage-tax shipping (exempt); 4
  dividends credited in 2025 from 2023 profits with GHS withheld.
- Gross dividend, SDC withheld (per the dividend voucher), GHS withheld, foreign tax
  (code 2), date received. Self-assessed SDC is carried in automatically.

### 4Ζ Surrender of a life insurance policy

Only if surrendered within 6 years: 30% (within 3 years) or 20% (years 4–6) of the
premium relief previously granted is added back to income.

### 4Η Income exempt from income tax but subject to GHS (articles 8, 36(3))

### 4Θ Any other income

- Mandatory if self-employed income was retrieved. Social Insurance category 1A–16 →
  GHS 4%; otherwise "Δ/Ε" (not applicable) → GHS 2.65%.
- Short-term rentals (Airbnb, Booking…): declared here; no SDC, GHS 2.65% or 4%.
- Partnership profits, agricultural subsidies.
- Minimum guaranteed income, maternity/paternity and other non-taxable allowances are
  declared for information with codes 3, 4, 5.
- Systematic trading income, even alongside a salary → the self-employed return
  (T.D.1 Self-employed) is required instead.

### 4Ι Total income — automatic.

## Part 5 — Deductions and exemptions

### 5A Various deductions (outside the 1/5 cap)

From T.D.63 or receipts: trade union subscriptions; professional subscriptions **only
if needed to earn the declared income** (not for pension-only income); donations
(keep receipts); public-sector pay reduction; contributions to political parties up
to €50,000 (with receipts); allowed expenses of community leaders and customs
officers; commission expenses (5/10/20%); professional liability insurance;
**25% talent-repatriation exemption** (art. 8(21B)); "Renovate–Rent" scheme
depreciation.

25% talent-repatriation exemption (max €25,000 a year, 7 years): not resident for the
7 years before starting work/business in Cyprus but resident at some earlier time;
start between 1/1/2025 and 31/12/2030; pay over €30,000 in the first 12 months (and in
each year claimed); and either a recognised degree plus at least 36 months full-time
for a foreign employer in the 84 months before, or 84 months full-time for a foreign
employer.

### 5B Investment in innovative SMEs

### 5Γ Life insurance, Social Insurance, pension and provident funds etc.

- Whole euros. The **total is capped at 1/5 of net income** in the calculation.
- Fund names and codes are picked with the icon in column 2.
- Code 1 approved pension / provident funds; code 2 Social Insurance (auto for
  self-employed); code 3 life insurance (insurer TIC and name, policy date, whose life,
  sum insured — premium relief capped at **7% of the sum insured**; spouse's life only
  for policies from before 31/12/2002; for joint policies from 2003 only the policy
  owner gets relief); code 4 medical funds and **private health insurance** (declared
  here, **not** as life insurance; capped at **2% of gross income**; GHS is **not**
  entered here); code 5 widows' pension fund; code 6 foreign social insurance.

## Part 6 — Declaration

A mandatory checkbox confirming the return is complete and true, plus some register
details. **The user ticks it themselves.**

## Calculation pages (ΥΠΟΛΟΓΙΣΜΟΣ)

### GHS (ΓεΣΥ)

- Calculated automatically: 2.65% on all income types, 4% on self-employed profit;
  income capped at €180,000 a year, counted in the order shown in the return.
- GHS paid by self-assessment appears automatically and can only be reduced.
- **Any amount on line 10B, even 1 cent, becomes payable** and appears in the Tax
  Portal.

### Income tax (self-assessment)

- Filled automatically, including deductions — except: losses from previous years,
  certain widow's pension pay reductions, and **foreign tax credit on foreign rent**,
  which the user calculates and enters (net rent × tax on chargeable income / net
  income; circular 2011/14).
- Additional 10% tax on rent and on self-employed income is calculated automatically.

### SDC (ΕΑΕ)

- Automatic, for rent, interest and dividends, split into two half-years.
- Withheld SDC amounts carried over must match the system's half-year split, otherwise
  tiny differences (refundable cents) appear and **the return cannot be submitted**.
- Self-assessed SDC appears automatically and can only be reduced.
- **Non-doms** who filed form T.D.38: enter the exemption years and delete the income
  and deduction amounts from the SDC calculation.
- Foreign tax on rent, interest and dividends is moved here automatically (can be
  adjusted or moved to the income tax calculation for foreign rent).

### IBAN for refunds

Shows the IBAN on file. To add or change it: form T.D.2008 **only via Tax For All**
("Inbox → New message → Forms → Bank account – IBAN (ΤΦ 2008)") with a bank
certificate showing the IBAN.

## Payment

After the **final** submission the amounts due go automatically to the **Tax Portal →
Statement of amounts due**, under these codes: 0300 income tax; 0315 GHS on salary,
office-holder and other income; 0313 GHS on self-employed profit; 0314 GHS on pensions;
0316 GHS on interest, dividends, rent; 0604 SDC on rent; 0612 SDC on interest; 0613 SDC
on dividends.

## Correcting a return after final submission

Within the filing deadline: TAXISnet → "ΥΠΟΒΟΛΗ/ΠΡΟΒΟΛΗ ΔΗΛΩΣΕΩΝ" → "Προβολή
(Ιστορικό δηλώσεων)" → the return number → "Μεταβολή σε ΠΡΟΣΩΡΙΝΗ" → "Μεταβολή" →
"Υποβολή (Συμπλήρωση δήλωσης)" → correct and submit finally again. The user does this
themselves; if it is reverted to temporary and not resubmitted before the deadline, it
counts as not filed.
