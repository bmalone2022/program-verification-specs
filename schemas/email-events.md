# Email event catalog

Used as `EmailMessage.eventKey`. Templates live in the future app; keys must stay stable.

| eventKey | Default on | Recipients | PDF |
|----------|------------|------------|-----|
| `job.received` | always | submitter | no |
| `job.queued` | preference | submitter | no |
| `job.verifying` | preference | submitter | no |
| `job.complete.pass` | always | submitter; optional quality | yes |
| `job.complete.fail` | always | submitter + quality | yes |
| `job.failed` | always | submitter + ops/quality | no |
| `job.stuck` | always | ops | no |
| `quality.escalation` | on action | quality | yes |

Idempotency key: `(jobId, eventKey)` except retries of a failed send (same key, incremented `attempt`).

All bodies include project name, job id, and intranet URL `/jobs/{jobId}`.
