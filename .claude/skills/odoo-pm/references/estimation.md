# Estimation baseline (man-days, MD)

Starting point only — replace with your team's actuals after 2–3 projects (edit `BASE` in `scripts/estimate.py`).

| Fit | S | M | L | XL | Meaning |
|---|---|---|---|---|---|
| Standard | 0.25 | 0.5 | 1 | 2 | Works out of the box; demo + training only |
| Config | 0.5 | 1 | 2 | 4 | Settings, master config, access rights |
| Studio | 0.5 | 1 | 2 | 4 | Fields/views/automations via Studio (EE) |
| Custom | 1 | 3 | 6 | 12 | Custom module development incl. unit tests |
| Report | 1 | 2 | 4 | 6 | QWeb PDF / Excel report (Thai forms are usually M–L) |
| Integration | 3 | 6 | 12 | 20 | API/EDI/bank/e-Tax per interface |
| Migration | 1 | 2 | 4 | 8 | Per object incl. template, validation, 2 test loads |
| Out of scope | 0 | 0 | 0 | 0 | Listed for transparency |

Complexity guide: S = one field/setting/screen; M = one process change; L = cross-module or approval logic; XL = new process/heavy calculation/unknown external system.

Overheads (defaults in script): QA 25% of build items, PM 15% of subtotal, contingency 15%. Training, data cleansing by customer, and hypercare are separate lines — add them as rows with an explicit Effort (MD).

Rules
- Never present the estimate as a quote without stating assumptions and exclusions.
- Any requirement with unclear scope → Complexity one step higher or list as assumption.
- Odoo version upgrade of custom modules is a separate estimate (use odoo-dev `check_compat.py` hit count as input).
