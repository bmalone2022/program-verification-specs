# Cowl 4 golden test

Local files (not committed; CATPart is binary and large):

`/Users/bmalon14/Documents/AC&E/Spirit/Program Verification/Program Verification Cowl 4 Test/`

| Role | File |
|------|------|
| CAD | `cowl.CATPart` |
| Program | `Test Case 4 Code.rmcd` |
| Tools | `tool_list.txt` (`T8 WSC22-00515-002`, `T12 WSC22-00530-002`, `T16 WSC22-00313-003`) |
| ETR | `Engineering Tool Request WK061725_V4.pdf` |
| Annotated | Cowl screenshot with red boxes on excluded hole groups (and yellow origin marker) |

ETR summary: bottom section drill 0.500" first ten holes from yellow origin, skip red-box holes; top section 0.625" all except last five in the red box.

## Pass criteria (when the app exists)

1. Login as demo user.
2. Submit all five artifact types (four files + screenshot).
3. Job appears on the status page as `queued` then `verifying` then `complete` or `failed`.
4. Probe/drill/trim badges match parsed `Test Result:` lines from CSR_Server (or mock).
5. PDF downloadable and includes screenshots.
6. Submitter has `job.received` and a terminal email in the job email log.

Sample historical engine output (Windows paths) lives under `6_nov_23_td` as `ace_verification_results_*.txt` — use as the mock payload shape, not necessarily Cowl 4’s actual run.
