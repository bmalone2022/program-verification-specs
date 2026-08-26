# Email notifications

Users must be emailed as verification proceeds. Plant mail is **Exchange / internal SMTP relay**, not SendGrid or Gmail. The V2 prototype promised mail and then removed it from `server.js`; production treats mail as part of the job record.

Canonical event keys: [`../schemas/email-events.md`](../schemas/email-events.md).

## Events

| Event | Default recipients | When | PDF attached |
|-------|--------------------|------|----------------|
| `job.received` | Submitter | Inbox written | No |
| `job.queued` | Submitter (optional; user preference) | Ready for CSR_Server | No |
| `job.verifying` | Submitter (optional) | Agent started | No |
| `job.complete.pass` | Submitter; optional quality CC | Parsed pass | Yes |
| `job.complete.fail` | Submitter and quality mailbox | Parsed fail | Yes |
| `job.failed` | Submitter and ops/quality | System error | No (unless partial) |
| `job.stuck` | Ops | SLA exceeded in `verifying` | No |
| `quality.escalation` | Quality mailbox | Human “request quality review” | Yes |

## Body content (all templates)

- Project name and job id
- Intranet link `/jobs/{jobId}`
- Current state
- On complete: three `Test Result` lines and overall pass/fail

## Sending rules

- Windows Service sends mail; IIS only **enqueues** `EmailMessage` rows.
- Idempotent: unique (jobId, eventKey) for non-retryable events; retries increment `attempt`.
- Log success/failure on the job’s email panel.
- From address: plant service account.
- No API keys in git. Prototype `SendGridAPIKey.rtf` must not be copied.

## Preferences (v1 simple)

Default: received + terminal (pass/fail/failed) + stuck (ops). Queued/verifying mails off unless the user enables them, to avoid noise.
