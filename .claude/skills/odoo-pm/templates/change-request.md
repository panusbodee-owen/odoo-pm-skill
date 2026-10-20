# Template: Change Request (CR)

```
# Change Request <CR-NNN> — <title>
| Project | | Requested by | | Date | | Status | Draft / Submitted / Approved / Rejected |
|---|---|---|---|---|---|---|---|

## 1. Request
- Description: <what the customer wants>
- Reason / business value: <why>
- Related: <REQ ID / BUG ID / meeting>

## 2. Baseline vs change
| | Agreed scope (baseline) | Requested change |
|---|---|---|
| Function | | |
| Document / reference | <BRD/FSD version> | |

## 3. Impact analysis
| Area | Impact | Detail |
|---|---|---|
| Effort | <MD> | from estimate.py |
| Cost | <THB> | MD × rate |
| Timeline | <days / milestone moved> | |
| Other modules / data | | |
| Testing / UAT | <TC to add/re-run> | |
| Risk | Low / Medium / High | |

## 4. Options
| Option | Description | MD | Recommendation |
|---|---|---|---|
| A | Implement as requested | | |
| B | Workaround with standard/config | | |
| C | Defer to phase 2 | 0 | |

## 5. Decision & approval
| Role | Name | Decision | Signature | Date |
|---|---|---|---|---|
| Customer Project Owner | | | | |
| Implementer PM | | | | |
```
Rules: no work starts before approval; every CR gets an ID in the CR log (CR ID | Title | MD | Status | Decision date); approved CRs update the requirement list and baseline.
