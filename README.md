# TAXISnet — Cyprus tax return skill for Claude

[Русская версия](README.ru.md)

A Claude skill that walks through the Cyprus personal income tax return
(**TD1 / EPR1**) for the previous tax year in [TAXISnet](https://taxisnet.mof.gov.cy)
using a browser, and stops at the self-assessment step so **you** can review and submit.

## What it does

1. Opens TAXISnet and asks **you to sign in** in the browser window.
2. Checks the list of returns for one covering the previous tax year.
3. If there is a draft, opens it; if there is none, creates one
   (after your confirmation); if it's already submitted, stops.
4. Enters the figures from your **T.D.63 (IR63)** certificates — one or several
   employers — after you confirm them (TAXISnet has no automatic IR63 download).
5. Asks you about any other income and deductions, checks them against the rules
   for the tax year (deadline, the 1/5 deduction cap, deductions that only start in
   2026), shows what it will enter, and fills in the form after your "yes".
6. Runs **SELF-ASSESSMENT / CONTRIBUTIONS**, summarises the result and sanity-checks
   it against the tax bands and SDC / GHS rates.
7. Hands over to you: you check every value and submit the return yourself.

## What it will never do

- Ask for, accept or type your username, password or one-time codes.
- Press the final **Submit** / **Υποβολή** button.
- Make payments or delete drafts or documents.
- Invent figures or give tax advice.

## Requirements

- Claude with browser access: the built-in browser in the Claude desktop app, or
  Claude in Chrome.
- A TAXISnet account (individual taxpayer).
- The T.D.63 (IR63) certificate from each employer, and documents for any other
  income and deductions.

## Installation

### Claude Code (plugin)

```
/plugin marketplace add ittermit/taxisnet
/plugin install taxisnet@taxisnet
```

### Claude app (claude.ai / desktop)

1. Download the [`skills/cyprus-tax-declaration`](skills/cyprus-tax-declaration)
   folder (or the whole repository as a ZIP and take that folder out).
2. Zip the `cyprus-tax-declaration` folder.
3. Upload the ZIP in the skills section of Claude's settings.

### Other AI agents (Codex, Gemini, Cursor, etc.)

The skill is plain Markdown, so any agent that can control a browser can follow it.
Give your agent the link to this repository and ask it to apply the skill, for example:

> Read https://github.com/ittermit/taxisnet — use
> `skills/cyprus-tax-declaration/SKILL.md` and its `references/` folder as a skill,
> and follow it to prepare my Cyprus tax return for last year in TAXISnet.

If the agent supports skills or custom instructions, copy the
`skills/cyprus-tax-declaration` folder into its skills directory instead. The skill
mentions Claude's browser tools by name; other agents use their own browser tool
in the same way. The safety rules (you sign in yourself, you press the final
submission yourself) apply whichever agent you use.

## Usage

Ask Claude something like:

> Prepare my Cyprus tax return for last year in TAXISnet.

Claude will open the browser and ask you to sign in, then follow the steps above.

## Repository layout

```
.claude-plugin/
  plugin.json          # plugin manifest
  marketplace.json     # lets Claude Code install it from this repo
skills/
  cyprus-tax-declaration/
    SKILL.md           # the skill instructions
    references/
      official-guide-2025.md # the official 2025 form guide, part by part
      rules-2025.md    # tax year 2025 rules: deadline, bands, deductions, SDC/GHS
      taxisnet-notes.md # how TAXISnet behaves: statuses, prefill, IR63, payment
      checklist.md     # what Claude asks you
      sources.md       # sources for the rules and notes
README.md / README.ru.md
CHANGELOG.md
LICENSE
```

## Known limitations

- The built-in tax rules cover **tax year 2025** only (filed in 2026 in TAXISnet).
  From tax year 2026 returns are filed in Tax For All, which this skill does not cover.
- The form steps follow the official 2025 guide and were checked against the live
  TAXISnet form in October 2026; labels may still differ slightly.
- TAXISnet may log you out after inactivity — Claude will ask you to sign in again.

## Disclaimer

This project is not affiliated with the Cyprus Tax Department or the Ministry of
Finance. It is not tax advice. You are responsible for checking the data and for
submitting the return. Consult a tax advisor if you are unsure what to declare.

## Sources

The rules and notes in `skills/cyprus-tax-declaration/references/` were compiled on
14 October 2026. The official Tax Department material is the primary source; the
other sources were used for context and cross-checking.

Official (Cyprus Tax Department / TAXISnet):
- [Guide for completing the Individual Income Tax Return 2025 (PDF, Greek)](https://www.gov.cy/media/sites/167/2026/06/Guide-for-completion-of-tax-return-2025-EL.pdf)
- [Individual income tax return — Tax Department page](https://www.gov.cy/mof-tax/documents/forologiki-dilosi-eisodimatos-atomoy/)
- [Announcement on the start of 2025 return submissions (18 June 2026)](https://www.gov.cy/oikonomia/anakoinosi-tou-tmimatos-forologias-anaforika-me-tin-enarxi-tis-ypovolis-tis-dilosis-eisodimatos-atomou-gia-to-forologiko-etos-2025/)
- [What to watch out for — common mistakes](https://www.gov.cy/mof-tax/documents/forologiki-dilosi-eisodimatos-atomoy/ti-prepei-na-prosexete-sychna-lathi/)
- [Remote work for an employer outside Cyprus](https://www.gov.cy/mof-tax/documents/forologiki-dilosi-eisodimatos-atomoy/ex-apostaseos-ergasia-se-ergodoti-ektos-tis-dimokratias-i-kai-parochi-ypiresion-ektos-tis-dimokratias/)
- [TAXISnet FAQ — Electronic submission of tax returns](https://taxisnet.mof.gov.cy/displayFaq.do?dispatch=faq5Ird)
- TAXISnet help documents on temporary save vs final submission, form time limits and
  changing a return to temporary (from the Intrastat / VAT instructions in TAXISnet's
  information material)

Deadline, filing obligation, penalties and the 2025 TAXISnet season:
- [C. Markou & Co — 2025 personal income tax return due by 31 October 2026](https://www.cmarkou.com/2025-personal-income-tax-return-due-by-31-october-2026/)
- [Politis — TAXISnet opens for 2025 returns as Cyprus raises late-filing fines](https://en.politis.com.cy/news/economy/1012362/taxisnet-opens-for-2025-returns-as-cyprus-raises-late-filing-fines)
- [Sigmalive — Income tax submission through TAXISnet until 31 October](https://en.sigmalive.com/?p=68186)
- [RegFollower — Cyprus extends 2025 personal income tax filing deadline](https://regfollower.com/cyprus-extends-2025-personal-income-tax-filing-deadline/)
- [Globalserve — Deadline extension for 2025 individual income tax returns](https://www.gstaxconsultants.com/deadline-extension-for-2025-individual-income-tax-returns/)
- [Andersen Cyprus — Submission of 2025 income tax returns](https://cy.andersen.com/news/cyprus-news-submission-of-2025-income-tax-returns/)
- [SPL — Tax Department update on the personal income tax return (T.D.1)](https://splcy.com/tax-alert-update-on-personal-income-tax-return-y2025/)
- [PwC Cyprus — 2024 TD1s: extension to 15 October 2025](https://www.pwc.com.cy/en/publications/direct-tax-updates-2025/dtu-n14-2025.pdf)

Tax rules (bands, deductions, exemptions, SDC, GHS, residency):
- [PwC Tax Summaries — Cyprus: taxes on personal income](https://taxsummaries.pwc.com/Cyprus/Individual/Taxes-on-personal-income)
- [PwC Tax Summaries — Cyprus: deductions](https://taxsummaries.pwc.com/cyprus/individual/deductions)
- [TaxApp — 5 common mistakes to avoid for the 2025 tax filing in Cyprus](https://taxapp.cy/5-common-mistakes-to-avoid-for-the-2025-tax-filing-in-cyprus/)
- [Rightax — Tax incentives for first employment (20% / 50% exemptions)](https://rightax.com.cy/https-rightax-com-cy-cyprus-tax-incentives-highly-paid-first-employment/)
- [Mondaq — Passive income taxation in Cyprus: an update](https://www.mondaq.com/passive-income-taxation-in-cyprus-%E2%80%93-an-update/1755734)
- [KPMG Cyprus — Tax residency and non-dom rules](https://assets.kpmg.com/content/dam/kpmg/cy/pdf/2024/cyprus-tax-residency-and-non-dom-rules.pdf)

TAXISnet usage and practical tips:
- [Abasis — TAXISnet or Tax For All: which portal for the 2025 and 2026 returns](https://cyprustaxcalculator.abasis.ai/guides/which-portal/)
- [Cyprus Tax Life — TAXISnet guide](https://www.cyprustaxlife.com/blog/cyprus-tax-portal-taxisnet)
- [CyExpat — How to file taxes in Cyprus](https://www.cyexpat.com/en/articles/posts/file-taxes-cyprus/)
- [CyEasy — Tax forms guide (TD1, IR63, TD59)](https://cyeasy.tax/en/forms)

Secondary sources can contain mistakes; where they disagreed, the skill uses the
figures confirmed by several of them.

## License

[MIT](LICENSE)
