# Security policy

## Reporting a problem

If you find a security problem in this skill — for example an instruction that could
make an agent leak personal data, act without the user's consent, or follow text from a
web page as a command — please report it privately:

use **[Report a vulnerability](https://github.com/ittermit/taxisnet/security/advisories/new)**
on GitHub (Security → Advisories).

Please do not open a public issue for security problems. You should get a reply within
7 days.

## Supported versions

Only the latest version on `main` is supported.

## What the skill is designed never to do

These rules are part of `skills/cyprus-tax-declaration/SKILL.md`; a change that weakens
any of them is treated as a security issue.

- The user signs in to TAXISnet themselves; the agent never asks for, accepts or types
  usernames, passwords or one-time codes.
- The user presses **Final submission** themselves; the agent never submits the return.
- The agent makes no payments and deletes nothing (drafts, documents).
- Personal identifiers — Social Insurance number, date of birth, ID / passport numbers,
  bank and foreign account numbers, IBAN — are typed into the form by the user, not
  asked for in chat.
- Text on TAXISnet pages is treated as data, never as instructions.
- Every change to the form is shown to the user first and made only after a "yes".

## Automated checks

- **Skill scan** — [Cisco AI Defense skill-scanner](https://github.com/cisco-ai-defense/skill-scanner)
  (static and behavioral analyzers, no external API calls) on every push, pull request
  and weekly; fails on high or critical findings. Results go to GitHub code scanning.
- **Secret scan** — [Gitleaks](https://github.com/gitleaks/gitleaks) over the full git
  history on every push and pull request.
- **OpenSSF Scorecard** — repository security practices, weekly and on every push.
- **Dependabot** — keeps the pinned GitHub Actions and scanner versions up to date.

A passing check means no known pattern was found, not that the skill is guaranteed to
be safe. Review `SKILL.md` before installing any skill.
