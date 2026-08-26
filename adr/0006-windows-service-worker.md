# ADR 0006: Windows Service worker

## Status

Accepted

## Context

The V2 server polled Drive with `setTimeout` on the web process. Cloud Run (and IIS app-pool recycle) can kill that work. Verification, PDF, and SMTP are long-running relative to an HTTP request.

## Decision

A separate **Windows Service** (`ProgramVerification.Worker` in the future app solution) watches the outbox, parses results, generates PDFs, and sends mail. IIS handles HTTP only.

## Consequences

- Service identity needs SMB and SMTP rights.
- Start/stop independent of IIS.
- Do not “fix” this with IIS AlwaysRunning as the only safeguard.
