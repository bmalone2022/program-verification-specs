# Security

## Network

- Intranet only. No public Cloud Run equivalent.
- HTTPS with plant certificates.
- SMB share not exposed off-site.

## Authentication (v1)

- Demo user from configuration.
- HTTP-only, Secure, SameSite session cookie.
- Every API requires the session. UI login is not a substitute for API auth (V2 failure mode).

## Authentication (later)

- Windows / Active Directory via IIS or OpenID Connect against plant IdP.
- Schema already has `WindowsSid` / UPN.

## Uploads

- Extension allowlists: `.CATPart`, `.rmcd`, `.txt`, `.pdf`, image types for annotations.
- Size caps per file and per job.
- Store outside the IIS `wwwroot`. Serve downloads through authenticated API, not static anonymous paths.

## Secrets and prototype residue

Do not import:

- `SendGridAPIKey.rtf`
- `google-credentials.json` / Drive folder IDs
- Hardcoded `joe.smith@test.com` / `demo123` in client bundles

## Audit

`JobEvent` + `EmailMessage` + artifact checksums are the audit trail for “who submitted what, who was told, what CSR_Server said.”
