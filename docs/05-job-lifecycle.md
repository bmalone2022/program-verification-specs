# Job lifecycle

```
submitted → queued → verifying → complete
                              ↘ failed
```

| State | Meaning |
|-------|---------|
| `submitted` | SQL row exists; files still landing |
| `queued` | Inbox folder complete; waiting for CSR_Server |
| `verifying` | Agent has the job (heartbeat, lock file, or first outbox activity) |
| `complete` | `ace_verification_results*.txt` ingested; PDF built; overall pass/fail set |
| `failed` | System/agent error — not the same as a program that **failed checks** |

A program that CSR_Server ran and found invalid is **`complete`** with `overallResult = fail`. Reserve `failed` for “could not verify” (missing files, agent crash, timeout).

## Overall result

Parsed from CSR_Server lines matching `Test Result:` (probe, drill, trim). `overallResult` is `pass` only if every present check is valid; otherwise `fail`. `unknown` if the results file has no parseable summary.

## Events

Every transition appends a `JobEvent` (fromState, toState, at, message). The status page timeline is this table. Email is keyed off the same events ([07-email-notifications.md](07-email-notifications.md)).

## Stuck jobs

If a job remains `verifying` longer than the SLA (default 4 hours, configurable), emit `job.stuck` to ops and show a warning on the status page. Do not auto-fail without a human/ops rule.
