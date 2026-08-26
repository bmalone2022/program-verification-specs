# Product overview

**Name:** Program Verification portal (working title; UI may still say CimStation / Spirit Program Verification).

**One sentence:** Spirit programmers submit CAD, program, tools, engineering request, and annotated exclusion screenshots; the plant portal queues CSR_Server and returns pass/fail plus a PDF, with a durable status page and email trail.

## Why a rebuild

The V2 prototype is a Create React App talking to an unauthenticated Cloud Run service that uploads to Google Shared Drive. Email and result polling were stripped from the live server. Status is “a Drive file whose name contains `ace_verification_results`.” That cannot be the production system of record on a manufacturing network.

## What the programmer experiences

1. Log in (demo credentials from server config, not shown in the UI placeholder).
2. Open **Status** (past runs) or **New verification**.
3. Fill project name, notification email(s), and upload:
   - CATPart
   - RMCD program
   - Tool list
   - Engineering tool request PDF
   - One or more annotated screenshots
4. Submit. Immediate confirmation on screen and `job.received` email.
5. Watch the job move queued → verifying → complete/failed.
6. Open the report PDF and raw CSR_Server text. Failures CC quality.

## What happens behind the portal

- SQL Server stores the job, events, check summaries, and email log.
- Files land on an NTFS volume exposed as SMB for CSR_Server.
- A Windows Service watches the outbox, parses results, builds the PDF, sends mail.
- CSR_Server is unchanged in this phase: it reads `*.rmcd` and related inputs from the inbox folder.
