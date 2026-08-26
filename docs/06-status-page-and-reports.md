# Status page and reports

The status page is the **home screen after login**, not a secondary “history” tab.

## List

Filters:

- Date range (submitted)
- State (`queued`, `verifying`, `complete`, `failed`)
- Overall result (pass / fail / unknown)
- Submitter
- Project / part name (contains)

Columns:

- Project name (link to detail)
- Submitted at
- Submitter
- State
- Probe / drill / trim badges (valid / failed / n/a)
- Screenshot count
- Report PDF (download when present)
- Duration (submitted → terminal)
- Last email state (sent / failed / none)

Paging and newest-first default. Quality (later) sees all jobs; demo user sees all jobs.

## Job detail (`/jobs/{jobId}`)

- Timeline of `JobEvent`s
- Downloads: CATPart, RMCD, tool list, ETR PDF, annotated images, raw results text, report PDF
- Parsed check summaries
- Email log for this job (template, recipients, success/error)
- Shareable intranet URL for pasting into Outlook

## Live updates

While `queued` or `verifying`, the page polls every 5–10 seconds **or** uses SignalR. The browser is never the worker.

## Reports

The PDF is generated from CSR_Server text by the existing ReportLab approach (Python CLI sidecar invoked by the Windows Service). It must include:

- Programmer / project / date
- Summary of test results (color pass/fail)
- Detail useful to correct the program
- Annotated screenshots
- Control to request quality review (in-app action preferred over a bare `mailto:`)
