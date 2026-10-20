---
name: odoo-pm
description: Odoo implementation project management, any version (16, 17, 18, 19, 20+) — requirement lists (BRD) with Fit classification (Standard/Config/Studio/Custom/Report/Integration/Migration), functional specs (FSD), man-day estimates and cost to Excel, Change Requests with impact analysis, cutover plans, Go/No-Go checklists, rollback and hypercare plans. Use when the user asks for BRD, FSD, requirement list, fit-gap classification with effort, estimate, man-day, ประเมิน MD, quotation effort, change request, CR, cutover, go-live plan, go/no-go, or hypercare for an Odoo project.
---

# Odoo PM (version-aware, token-efficient)

## Token rules
1. Load only the template for the requested output; `references/estimation.md` only when estimating or explaining effort.
2. Numbers come from `scripts/estimate.py`; never add up man-days by hand in chat.
3. Write deliverables to files (`docs/pm/<TYPE>_<project>_<yyyymmdd>.md`) and reply with path + key figures + open assumptions (≤3 bullets).
4. Status updates for management: use `product-management:stakeholder-update` or `management-talk` if installed; don't duplicate them here.

## Pick the template
| User asks for | Load | Then |
|---|---|---|
| Requirement list / BRD / fit with effort | `templates/requirements.md` | `estimate.py` |
| FSD for a custom item | `templates/requirements.md` (FSD part) | hand to odoo-dev / odoo-qa-docs |
| Estimate / man-day / cost | `references/estimation.md` | `estimate.py` |
| Change Request | `templates/change-request.md` | `estimate.py` for impact |
| Cutover / go-live / go-no-go / hypercare | `templates/cutover.md` | |

## Scripts (run, do not read)
```bash
S=.claude/skills/odoo-pm/scripts   # or ~/.claude/skills/odoo-pm/scripts
python3 $S/estimate.py docs/pm/REQ_<project>.md --qa 25 --pm 15 --contingency 15 [--rate 6000]
python3 $S/export.py docs/pm/<file>.md [--xlsx] [--docx]     # any template → Excel/Word
```
Needs `openpyxl`; Word export needs `pandoc`.

## Rules
- Fit = lowest option that meets the need; Custom requires a one-line reason. Version matters: check with odoo-dev `references/versions.md` whether a feature is standard in the target version; tag unsure items `(verify)`.
- Estimates are baselines: always state assumptions, exclusions and the overhead % used. Rates/costs only if the user gives a rate.
- Every scope change after sign-off becomes a CR; no build before CR approval.
- Keep IDs consistent across skills: REQ-xx (pm) → TC-xx (odoo-qa-docs) → BUG-xx → CR-xx.
- Thai projects: documents default to Thai labels with English Odoo terms; amounts in THB.
