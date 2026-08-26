# ADR 0004: React SPA + ASP.NET Core API

## Status

Accepted

## Context

The prototype UI is React. Plant servers should not run Node. A pure Blazor app would ease IT (C# only) but would throw away the existing UI language.

## Decision

- **UI:** React + TypeScript SPA, built on developer workstations, copied to IIS `wwwroot`.
- **API:** ASP.NET Core LTS, same IIS site, `/api`.

Node is a **build-time** dependency, not a production runtime.

## Consequences

- Spirit IT installs the .NET Hosting Bundle on IIS, not Node.
- Frontend and API version together as one published site.
- Blazor remains a fallback if IT later bans a JavaScript SPA.
