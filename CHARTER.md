# Charter

## Problem

Spirit programmers need an independent check that a machining program matches the CAD part, the engineering tool request, and explicit **do-not-machine** regions. Today that check is a desktop AC&E / CimStation flow plus a brittle web prototype that drops files in Google Drive.

## Outcome

A plant-hosted web portal where a programmer:

1. Signs in (demo account for now).
2. Submits the required package, including annotated screenshots of exclusion zones.
3. Sees the job on a **status page** with past runs and reports.
4. Receives **email** as the job is accepted, runs, passes, fails, or gets stuck.
5. Opens a PDF that states what to correct.

CSR_Server, already on the plant network, performs the actual `*.rmcd` verification. The portal does not reimplement probe/drill/trim simulation.

## Users (v1)

- Programmer (submit, own jobs, email)
- Quality reviewer (later role; v1 demo user can see all jobs so walkthroughs work)
- Plant ops (SMTP/SMB/IIS; not a product login)

## Success for the Cowl 4 golden test

Submit the four Cowl files plus the annotated cowl screenshot. The job appears on the status page, CSR_Server (or the mock agent) writes results, probe/drill/trim badges populate, a PDF is stored, and the submitter is emailed.

## Non-goals (this charter)

- Rewriting CSR_Server
- ENOVIA CATPart extraction / CATProduct KBE macros
- Google Workspace, Cloud Run, Vertex/Gemini
- Public internet hosting
- Building the application in this repository
