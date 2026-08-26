# CSR_Server integration

**CSR_Server** is Rick’s on-network application that performs verification of the `*.rmcd` file against the CAD part and tools (probe, drill, trim). It is **not** this portal and is **not** this specs repo.

This phase does not require CSR_Server source. The portal implements a **folder contract**. Point the agent at the SMB inbox when ready.

## Responsibilities

| Component | Does |
|-----------|------|
| Portal API | Accept uploads, write inbox, record SQL job |
| CSR_Server | Read inbox, run AC&E/CimStation verification, write results |
| Windows Service | Detect outbox results, parse, PDF, email, update SQL |

## How the agent is expected to behave

1. Notice a new `inbox\{jobId}\` with complete `manifest.json`.
2. Run verification (existing desktop/server behavior).
3. Write `outbox\{jobId}\ace_verification_results*.txt` (today’s filename convention).
4. Optionally write `outbox\{jobId}\status.json` and screenshots.

If CSR_Server only understands a flat watch folder, an adapter can copy one job at a time from `inbox` into the agent’s legacy path. Document that adapter when Rick’s drop folder is known.

## Mock agent (application phase, not this repo)

A mock copies a checked-in sample `ace_verification_results_*.txt` into the outbox after a delay so Cowl 4 can be demoed without the Windows verifier.

## What the portal must never assume

- Google Drive webView links
- Polling from Cloud Run `setTimeout`
- Invoking CSR_Server via HTTP in v1 (folder only unless Rick later adds an API)
