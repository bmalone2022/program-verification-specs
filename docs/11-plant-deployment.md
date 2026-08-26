# Plant deployment

## Hosts

- **IIS site:** HTTPS (internal CA if required), SPA in `wwwroot`, API as ASP.NET Core module, binding on the intranet hostname (e.g. `https://progverif.plant.local`).
- **SQL Server:** same box or nearby; dedicated database `ProgramVerification`; backups per plant DBA policy.
- **Data volume:** `D:\ProgramVerification\` (or UNC). Grant the IIS app-pool identity write to `inbox`, the CSR_Server service account read on `inbox` and write on `outbox`, the Windows Service full control of both.
- **CSR_Server:** existing plant install; configure its watch path to the share.
- **SMTP:** authenticated relay to Exchange; From = service mailbox.

## IIS settings to plan for

- Max request length large enough for CATPart + screenshots (document a number with Spirit IT; start from 512 MB unless they cap lower).
- Request timeout for upload only; verification must not use that timeout.
- App pool: do **not** treat recycle as a job runner. Worker is a Windows Service.
- Firewall: site reachable on plant LAN only. No `--allow-unauthenticated` public endpoint.

## Email from inside the plant

CSR_Server does not send programmer mail. The portal worker does, using the relay Spirit already uses for other internal apps. If outbound internet is blocked, that is fine as long as Exchange is reachable.

## Secrets

IIS environment variables or Windows Credential Manager. Never git. Never copy prototype Drive JSON or SendGrid RTF files onto the plant server as “config.”

## Build pipeline

Developers build the SPA (`npm run build`) and publish the ASP.NET app on a machine that **may** have internet. Artifacts (static files + published .NET) are copied to IIS. Plant servers should not `npm install` at runtime.
