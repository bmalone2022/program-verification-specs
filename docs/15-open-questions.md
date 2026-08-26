# Open questions

1. **CSR_Server watch path** — exact folder, filename expectations, and whether it can target `inbox\{jobId}` or needs a single flat drop directory.
2. **Intranet URL** — hostname Spirit IT will assign.
3. **SQL Server instance** — local to the IIS box vs shared plant cluster; Express vs Standard.
4. **CATPart size cap** — confirm with IT and real Spirit parts (Cowl is a sample).
5. **Quality mailbox** — distribution list address for fail and escalation.
6. **SLA** — hours before `job.stuck` (default proposed: 4).
7. **GitHub org** — `bmalone2022` vs an AC&E organization for this specs repo and the future app repo.
8. **ITAR / data classification** — whether CATParts on the share need extra controls beyond intranet + SMB ACLs.
9. **IIS max upload** — numeric limit Spirit will allow.
10. **Who operates the Windows Service** — AC&E vs Spirit IT.

Update this list as answers land; do not block phase 0 (this repo).
