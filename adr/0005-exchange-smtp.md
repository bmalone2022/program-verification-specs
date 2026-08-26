# ADR 0005: Exchange / internal SMTP

## Status

Accepted

## Context

Users must be emailed when jobs are received, complete, fail, or get stuck. SendGrid and Gmail require internet SaaS and API keys the plant should not depend on. CSR_Server sits inside the network; mail still has to reach Outlook.

## Decision

Send all product email through the plant **Exchange SMTP relay** (or IIS SMTP pickup if that is the local standard). Persist every attempt in SQL (`EmailMessage`).

## Consequences

- From-address is a service mailbox Spirit IT provisions.
- Attach PDF on terminal and escalation events.
- Dev uses Mailhog/Papercut; production never uses SendGrid unless IT later mandates an approved relay.
