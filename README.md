# Program Verification — specifications

Specs and contracts for the **Spirit Program Verification** portal. This repository is documentation only. It is not the application.

Programmers upload a machining package (CATPart, RMCD program, tool list, engineering request, and annotated exclusion screenshots). The portal stores the job, emails stakeholders, hands a folder to **CSR_Server** (Rick’s on-network RMCD verifier), and publishes pass/fail plus a PDF report.

**Target production host:** Windows Server + IIS inside the Spirit / Boeing manufacturing plant. CSR_Server stays on the plant LAN. Email goes out through internal Exchange / SMTP so users receive status and reports.

## New machine / Cursor

Open [HANDOFF.md](HANDOFF.md) first. It is the transfer document: clone, open this folder in Cursor, and a prompt to paste into a new Agent chat.

## Read this first

1. [HANDOFF.md](HANDOFF.md) — new Mac / Cursor setup
2. [CHARTER.md](CHARTER.md) — purpose, non-goals, golden test
2. [docs/00-index.md](docs/00-index.md) — document map
3. [docs/10-architecture.md](docs/10-architecture.md) — plant stack decision
4. [docs/09-file-and-job-contract.md](docs/09-file-and-job-contract.md) — inbox/outbox CSR_Server must implement
5. [docs/13-phasing.md](docs/13-phasing.md) — specs now, application later

## Prototype references (do not extend)

- https://github.com/bmalone2022/CSR_Portal_Client_V2
- https://github.com/bmalone2022/CSR_Portal_Server_V2

Those apps proved the workflow. They used Google Drive, Cloud Run, and a public API. Production replaces that with IIS, SQL Server, SMB, and Exchange.

## What this repo is not

- Not Twin
- Not CSR_Server source
- Not application code, Docker Compose, or a deployable site
