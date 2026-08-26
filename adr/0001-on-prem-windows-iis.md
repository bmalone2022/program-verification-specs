# ADR 0001: On-prem Windows Server + IIS

## Status

Accepted

## Context

Production will run inside the Spirit / Boeing manufacturing plant. CSR_Server is already a Windows-side agent. Users need a website, not a cloud Drive drop.

## Decision

Host the portal on **Windows Server + IIS**. Do not use Cloud Run, App Engine, or a public PaaS as the production runtime.

## Consequences

- Deploy as a published ASP.NET site plus static SPA files.
- Network is plant LAN; firewall and HTTPS follow Spirit IT.
- Cloud prototype (Drive, Cloud Run, Vertex) is reference only.
