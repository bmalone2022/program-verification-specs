# ADR 0002: SQL Server, not PostgreSQL

## Status

Accepted

## Context

Jobs, history, email logs, and check summaries need a real database. The V2 prototype used Drive folders as a database.

## Decision

Use **SQL Server** (Express or Standard per IT). Do not introduce PostgreSQL on the plant unless Spirit already standardizes on it (they do not, per this evaluation).

## Consequences

- EF Core / ADO.NET in the future app.
- Backups and Windows authentication are familiar to plant DBAs.
- Developer machines may use LocalDB or SQL Server in Docker as a shim.
