# Moat UAT regression set (public-company 10-Ks)

Frozen answer key from the 2026-10-09 run of `find-your-moat` (thin pass) and `strategic-moat` (full pass) against five latest 10-Ks. Skills under test were main @ `5c34cb9`.

This folder is the regression set. It is not a worked moat write-up. Do not commit raw 10-K `.htm` / `.txt` filings or blind-run transcripts here.

## Companies

| File | Ticker | Filing-stated primary moats (hypothesis) |
|---|---|---|
| [atlassian.md](atlassian.md) | TEAM | Platform / ecosystem, Teamwork Graph, PLG scale |
| [visa.md](visa.md) | V | Credentials × acceptance, brand, security / reliability, value-added services |
| [costco.md](costco.md) | COST | Volume / scale economics, membership loyalty, Kirkland / brand |
| [intuitive-surgical.md](intuitive-surgical.md) | ISRG | Ecosystem (system + instruments + training + service), IP / FDA |
| [duolingo.md](duolingo.md) | DUOL | Gamified engagement, data / learning flywheel, brand, learner scale |

Together the hypotheses cover all 8 moat types. In all five, at least one filing-stated primary moat sat in a type the old thin pass marked not assessed (ecosystem, scale, brand, or regulatory).

## Baseline (2026-10-09, original rubric)

One blind run per company. The runner graded its own outputs. Treat scores as directional.

| Company | Thin /14 | Full /14 | Thin C4 | Thin C7 |
|---|---|---|---|---|
| Atlassian | 11 | 14 | 2 | 1 |
| Visa | 11 | 13 | 1 | 0 |
| Costco | 9 | 13 | 0 | 0 |
| Intuitive Surgical | 10 | 13 | 0 | 1 |
| Duolingo | 11 | 13 | 2 | 0 |
| **Average** | **10.4** | **13.2** | **1.0** | **0.4** |

Thin-pass averages on the other criteria: C1 1.4 · C2 2.0 · C3 1.8 · C5 1.8 · C6 2.0.

Full-pass C4 average was 1.8 (Intuitive scored 1). Full-pass C7 was 2.0 on every company.

## Rubric (7 criteria, 0–2 each, max 14)

- **C1 Primary moat.** Did it name the moat(s) the filing itself describes?
- **C2 Ratings.** Were the ratings directionally right?
- **C3 Competitors.** 2 = names the filing's top named rival, or at least two competitor categories the filing stresses. 1 = only one segment. 0 = none.
- **C4 Most at-risk vs risk factors.** Does the most-at-risk bullet line up with Item 1A? The 2026-10-09 baseline scored the old "Weakest" bullet under this same criterion.
- **C5 Unsupported claims.** 2 = none. 1 = minor unsupported specifics. 0 = material fabrication. A number with no `[user]`, `[public web]`, or `[filing §Item X]` tag is an unsupported claim.
- **C6 Do this week.** Is it sensible?
- **C7 Coverage.** Full pass: 2 = all 8 types rated. Thin pass: use the re-run rule below. The baseline column used the original rule.

**Original thin-pass C7 (baseline only).** 2 = every filing-stated primary moat is among the four scored types. 1 = a primary moat is outside those four but still appears as rated evidence in another row. 0 = a primary moat is outside those four and is not surfaced. That rule cannot reach 2 for Costco, Visa, Intuitive, or Duolingo once the thin pass keeps a fixed scored four and only screens the rest. Baseline averages stay on this rule.

**Re-run thin-pass C7 (the bar going forward).** 2 = every filing-stated primary moat is either scored, or screened Yes, and any screened primary moat has the so-what lead `Your strongest moat may be <type> — run strategic-moat to score it.` 1 = a primary moat is only mentioned inside another row, or it is screened Yes but the lead sentence is missing. 0 = a filing-stated primary moat is screened No or absent.

**Re-run C4.** 2 = the most-at-risk moat is a dependency the business relies on, and it matches an Item 1A heading. 1 = partial match. 0 = the bullet is a None (or a screened No) the business does not rely on, or it matches no Item 1A heading. `N/A, not a dependency` on a row the business does not use is correct, and it must not be the most-at-risk bullet.

## Targets

After a skill change, re-run the thin pass on all five. The set passes when:

- average **C7 ≥ 1.5**
- average **C4 ≥ 1.5**

Full-pass C7 should stay 2.0. Do not lower a rating scale to invent a "double-edged" rating; that was out of scope for this set.

## How to re-run

1. Read the current `find-your-moat` and, for a full pass, `strategic-moat`.
2. For each company, answer the skill's intake from the company site, press, and earnings headlines. Do not open that company's file in this folder, and do not open the 10-K, until the blind write-up is saved outside the repo.
3. Let public-company mode fetch the latest filing (User-Agent required; `data.sec.gov` submissions JSON, then the archives document). The accession in each company file is the filing this key was graded against. If a newer 10-K has superseded it, grade against the newer filing and write down the new accession. Do not treat the quotes below as exhaustive for a later year.
4. Score C1–C7. Compare with the baseline table. A thin-pass regression passes at the targets above.
5. Keep raw filings and full transcripts out of git. Record the date, accessions, and seven scores in the PR or review note.

Quotes in the company files are verbatim from the graded 10-K text, with whitespace collapsed. Inner quotation marks are kept as in the filing.
