# ADR 0003: SMB/NTFS, not cloud object storage

## Status

Accepted

## Context

CSR_Server consumes files from disk. CATParts are large. Google Drive is abandoned. S3/MinIO would add a service and likely outbound cloud access the plant will not allow.

## Decision

Store artifacts on a dedicated **NTFS volume** (optionally a **SMB/UNC share**). SQL Server stores metadata and checksums only.

## Consequences

- Inbox/outbox layout is the integration API with CSR_Server.
- Backup of `D:\ProgramVerification` is part of plant backup, not a cloud bucket lifecycle policy.
- No Drive folder IDs in configuration.
