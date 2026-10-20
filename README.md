# odoo-pm — Claude Skill for Odoo Project Management (all versions)

Covers the project-management documents of an Odoo implementation, with numbers produced by a script instead of mental arithmetic.

| Task | How |
|---|---|
| Requirement list (BRD) + Fit | `templates/requirements.md` — Fit = Standard / Config / Studio / Custom / Report / Integration / Migration / Out of scope, MoSCoW priority |
| Functional spec (FSD) | `templates/requirements.md` (FSD part) → hand-off to odoo-dev and odoo-qa-docs |
| Estimate (man-days, cost) | `scripts/estimate.py` → Excel (lines + summary by Fit) with QA %, PM %, contingency %, optional THB rate; baseline table in `references/estimation.md` |
| Change Request | `templates/change-request.md` — baseline vs change, impact (MD, cost, timeline, risk), options, approval |
| Cutover / Go-live | `templates/cutover.md` — T-14…T+30 timeline, Go/No-Go criteria, rollback, hypercare |
| Export | `scripts/export.py` — any Markdown deliverable → Excel and Word (Thai font) |

```bash
python3 .claude/skills/odoo-pm/scripts/estimate.py docs/pm/REQ_demo.md --rate 6000
python3 .claude/skills/odoo-pm/scripts/export.py docs/pm/CR_001.md --docx
```

The man-day table is a starting baseline — replace it with your team's actuals (`BASE` in `estimate.py`).

Status: estimator tested on a sample requirement list (totals checked by hand; invalid rows reported and skipped); export tested to xlsx/docx.

## Installation

**claude.ai / Claude Desktop** — zip the `odoo-pm` folder (the zip must contain `odoo-pm/SKILL.md`), then Settings → Capabilities → Skills → Upload skill.

**Claude Code (all projects)**
```bash
git clone https://github.com/panusbodee-owen/odoo-pm-skill.git
mkdir -p ~/.claude/skills
cp -r odoo-pm-skill/.claude/skills/odoo-pm ~/.claude/skills/
```
Requirements: `pip install openpyxl` and `pandoc` for Word export.

## Related skills
[odoo-qa-docs](https://github.com/panusbodee-owen/odoo-qa-docs-skill) · [odoo-dev](https://github.com/panusbodee-owen/odoo-dev-skill) · [odoo-data-migration](https://github.com/panusbodee-owen/odoo-data-migration-skill) · [odoo-config](https://github.com/panusbodee-owen/odoo-config-skill) · [odoo-pm](https://github.com/panusbodee-owen/odoo-pm-skill)
