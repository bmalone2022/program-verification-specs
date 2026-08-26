# Users and roles

## v1 (demo)

A single configured demo user (email + password from IIS/environment, not hardcoded in the client). After login, that user can submit jobs and see **all** jobs on the status page so a plant walkthrough is useful.

Session: HTTP-only cookie. All `/api` calls require a valid session. The V2 prototype’s client-only password check is not sufficient.

## Roles to model now (enforce later)

| Role | Capabilities |
|------|----------------|
| Programmer | Submit jobs; see own jobs; receive job email |
| Quality | See all jobs; receive fail and escalation mail |
| Ops | No product UI required; SMTP/SMB/IIS |

SQL `User` table includes nullable `WindowsSid` / UPN so Active Directory can replace demo login without a schema rewrite.

## Recipients

Each job stores `notifyEmails[]` (defaults to the submitter). Quality mailbox is a plant-wide config value, not typed per job unless the submitter adds CC.
