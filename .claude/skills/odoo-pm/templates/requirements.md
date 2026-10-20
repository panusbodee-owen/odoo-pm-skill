# Template: Requirement list (BRD) + Functional Spec (FSD)

## Requirement list — one row per requirement
```
# Requirement List — <Project> — Odoo <ver>
| REQ ID | Process | Requirement | Priority | Fit | Complexity | Solution | Effort (MD) | Owner | Status | Remark |
|---|---|---|---|---|---|---|---|---|---|---|
| REQ-SO-001 | Sales | Credit limit block when overdue > 30 days | Must | Custom | M | Extend sale.order confirm check | | | Open | Standard only warns [CONFIG] |
```
- REQ ID `REQ-<MOD>-<NNN>`; Priority MoSCoW (Must/Should/Could/Won't).
- Fit: Standard | Config | Studio | Custom | Report | Integration | Migration | Out of scope. Prefer the lowest that meets the need; say why when choosing Custom.
- Leave Effort empty to use the baseline table; fill it to override.
- Then run `scripts/estimate.py` on the file.

## FSD — only for Custom / Report / Integration rows
```
## FSD <REQ ID> — <title>
| Item | Detail |
|---|---|
| Business need | <1–2 lines> |
| Current Odoo behaviour | <standard behaviour in this version> |
| Proposed solution | <models/fields/views/logic, in functional terms> |
| Users / access | <groups> |
| Fields | Name / Type / Required / Rule (table if > 3 fields) |
| Process flow | step 1 → 2 → 3 (or mermaid) |
| Reports / outputs | <layout ref, sample> |
| Validation & errors | <messages> |
| Out of scope | <explicit> |
| Acceptance criteria | Given / When / Then (map to TC IDs in odoo-qa-docs) |
| Dependencies / risks | |
| Estimate | <MD, from estimate.py> |
```
Hand the FSD to odoo-dev for build and to odoo-qa-docs for test cases (same REQ ID in Remark).
