# Template: Cutover Plan, Go/No-Go, Hypercare

```
# Cutover Plan — <Project> — Go-live <yyyy-mm-dd>
| Cut-off date | | Go-live date | | Freeze legacy from | | Prepared by | |
|---|---|---|---|---|---|---|---|

## Timeline
| ID | When | Task | Owner | Duration | Depends on | Done | Evidence |
|---|---|---|---|---|---|---|---|
| CO-01 | T-14 | Final UAT sign-off; all High bugs closed | PM | | | | UAT sign-off |
| CO-02 | T-10 | Config workbook signed; production DB configured from it | Consultant | | CO-01 | | Workbook Verified |
| CO-03 | T-7 | Final master data validated (0 errors) and imported to production | Consultant | | CO-02 | | validate report |
| CO-04 | T-5 | Users, access rights, email server, report layouts in production | Consultant | | CO-02 | | |
| CO-05 | T-3 | End-user training complete; manuals published | Trainer | | | | Attendance |
| CO-06 | T-1 | Legacy freeze; stock count; AR/AP and TB at cut-off from legacy | Customer | | | | Count sheets, TB |
| CO-07 | T0 | Import opening balances & stock; reconcile (MR/GL/AR/AP/ST checks) | Consultant + Accountant | | CO-06 | | Reconciliation table |
| CO-08 | T0 | Go/No-Go meeting | Steering | | CO-07 | | Minutes |
| CO-09 | T0 | Go-live: first real transactions per process (smoke test) | Key users | | CO-08 | | |
| CO-10 | T+1..T+30 | Hypercare | Support | | | | Ticket log |

## Go / No-Go criteria
| # | Criterion | Status (Go/No-Go) | Comment |
|---|---|---|---|
| 1 | No open Critical/Major defects in go-live scope | | |
| 2 | Opening balances reconcile with legacy (TB, AR, AP, stock) | | |
| 3 | Key users trained and signed off | | |
| 4 | Production backup taken and restore tested | | |
| 5 | Support team & escalation path ready | | |

## Rollback plan
- Trigger: <criteria, e.g. cannot invoice for > 4 hours>
- Steps: stop Odoo use → restore legacy operations → record transactions made in Odoo → decision on re-go-live date.
- Owner / decision maker: <name>

## Hypercare (T+1 … T+30)
| Item | Detail |
|---|---|
| Support hours / channel | |
| Severity & response time | Critical 2h / Major 1 day / Minor 3 days (adjust to contract) |
| Daily check | Open tickets, failed scheduled actions, posting errors, stock negative |
| First month-end close | Assist accountant; compare with legacy period |
| Exit criteria | No Critical for 2 weeks; first close done; handover to support |
```
Use odoo-qa-docs for UAT/bug formats and odoo-data-migration for the CO-03/CO-07 checks.
