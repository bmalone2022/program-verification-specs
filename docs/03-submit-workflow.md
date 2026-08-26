# Submit workflow

## Screen: New verification

Fields:

- Project / part name (required)
- Notification email(s) (required; default to logged-in user)
- CATPart file (required, `.CATPart`)
- RMCD program (required, `.rmcd`)
- Tool list (required, `.txt`)
- Engineering tool request (required, `.pdf`)
- Annotated screenshots (required, one or more; `.png` `.jpg` `.jpeg` `.webp`)
  - Optional caption per image (zone name, “do not drill”, “do not trim”)

Submit is disabled until all required fields and files are present. Show upload progress; CATParts may be large. Enforce documented size caps (see [12-security.md](12-security.md)).

## Optional escape hatch

If the engineering request has **no** visual exclusions, the user may check **No visual exclusions** and skip screenshots. That flag is stored on the job for audit. Default path: screenshots required.

## After submit

1. API creates the SQL `Job` row (`submitted`).
2. Files written to `inbox\{jobId}\` with `manifest.json` and `annotated\`.
3. Status becomes `queued` when the inbox folder is complete.
4. User is redirected to the job detail / status page.
5. `job.received` email is queued (sent by the Windows Service, not the HTTP request).

Do not run CSR_Server, PDF generation, or SMTP on the IIS request thread.
