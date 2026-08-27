# Machine transfer — Program Verification specs

Use this file to stand up **this repo** on a new Mac and continue in Cursor. This repository is **specifications only**. It is not Twin, not CSR_Server, and not the application.

**GitHub:** https://github.com/bmalone2022/program-verification-specs  
**Clone (SSH):** `git@github.com:bmalone2022/program-verification-specs.git`

---

## 1. On the new Mac (before Cursor)

### GitHub access

1. Sign in to GitHub as **bmalone2022** (or an account that is a collaborator — Rick was invited separately).
2. Confirm SSH works:

```bash
ssh -T git@github.com
```

You should see: `Hi bmalone2022!` (or your collaborator username). If not, add an SSH key: GitHub → Settings → SSH and GPG keys.

3. Clone:

```bash
mkdir -p "$HOME/Documents/AC&E"
cd "$HOME/Documents/AC&E"
git clone git@github.com:bmalone2022/program-verification-specs.git
cd program-verification-specs
git status
```

You want `main` matching `origin/main`. Golden files should exist under `testdata/cowl-4-golden/`.

HTTPS alternative if SSH is not set up:

```bash
git clone https://github.com/bmalone2022/program-verification-specs.git
```

### Open in Cursor

1. Cursor → **File → Open Folder…**
2. Select `…/AC&E/program-verification-specs` (this folder, not Twin).
3. Confirm the Explorer root is this specs repo.
4. Open a new **Agent** chat. Attach or `@` this file: `HANDOFF.md`.

Do **not** open the Twin project as the workspace if you intend to continue Program Verification specs.

---

## 2. Paste into a new Cursor Agent chat

Copy everything inside the following block as the first message on the new machine:

```text
You are continuing the Spirit Program Verification project. Read HANDOFF.md, CHARTER.md, docs/00-index.md, docs/10-architecture.md, docs/09-file-and-job-contract.md, and docs/13-phasing.md before doing anything else.

This workspace is the specs repo only (program-verification-specs). Do not scaffold the application unless I explicitly ask. Do not modify Twin. Do not use Google Drive, Cloud Run, SendGrid, or MinIO as the production design.

Locked decisions:
- Production: Windows Server + IIS inside the Spirit/Boeing plant
- UI: React + TypeScript SPA built on a developer machine, static files on IIS (no Node runtime on plant servers)
- API: ASP.NET Core LTS on the same IIS site
- DB: SQL Server
- Files: NTFS + SMB inbox/outbox for Rick’s CSR_Server
- Worker: Windows Service (not IIS request thread, not Cloud Run setTimeout)
- Email: Exchange / internal SMTP; log every send in SQL
- Auth for now: demo login; model AD later
- Annotated exclusion screenshots are required on submit
- Status page is the home screen (past runs + reports)
- Golden test files are in testdata/cowl-4-golden/

Prototypes (reference only, do not extend):
- https://github.com/bmalone2022/CSR_Portal_Client_V2
- https://github.com/bmalone2022/CSR_Portal_Server_V2

CSR_Server is Rick’s on-network RMCD verifier. We do not have its source in this repo. Integration is a folder contract (inbox/outbox). Rick has been invited as a GitHub collaborator on this specs repo.

Current phase: 0 (specs). Next is application only after I say to build.

Confirm you have the workspace root and summarize the architecture and next phase in a short paragraph, then wait for my instruction.
```

---

## 3. What this project is

Spirit programmers submit a machining package. The portal stores it, emails status, hands a job folder to **CSR_Server** (Rick), and shows **pass/fail plus a PDF**. Quality can open past runs.

Required package:

- CATPart
- `*.rmcd` program
- Tool list
- Engineering tool request PDF
- One or more **annotated screenshots** (regions not to machine)

Golden files (in git): [testdata/cowl-4-golden/](testdata/cowl-4-golden/)

Read order after this handoff:

1. [CHARTER.md](CHARTER.md)
2. [docs/00-index.md](docs/00-index.md)
3. [docs/10-architecture.md](docs/10-architecture.md) and [adr/](adr/)
4. [docs/04-annotated-screenshots.md](docs/04-annotated-screenshots.md)
5. [docs/06-status-page-and-reports.md](docs/06-status-page-and-reports.md)
6. [docs/07-email-notifications.md](docs/07-email-notifications.md)
7. [docs/09-file-and-job-contract.md](docs/09-file-and-job-contract.md)

---

## 4. What is *not* on GitHub

Copy separately only if you still need them. They are not required to continue specs work.

| Item | Typical path on the old Mac |
|------|-----------------------------|
| Twin (unrelated product) | `Documents/AC&E/Twin` |
| V2 portal prototype | `Documents/AC&E/ProgramVerificationCodeBase/` |
| Cursor plan file | Cursor Plans UI on the old machine (content is already in this repo) |
| CSR_Server source | Rick’s machine / plant — not in this repo |
| Secrets (SendGrid, Drive JSON) | Do **not** copy. Abandoned for production. |

`.gitignore` still blocks stray `*.CATPart` / `*.rmcd` at repo root. Files under `testdata/` are tracked on purpose.

---

## 5. People and access

- **Owner:** GitHub `bmalone2022`
- **Rick:** invited as collaborator from GitHub. He must **accept** the invite before clone works for him. Until then a private repo looks like it does not exist.
- Sharing is by collaborator invite, not by sending a public URL.

---

## 6. Current status (as of transfer)

- Phase 0 specs are in this repo on `main`.
- Application is **not** started.
- Plant stack is decided (IIS, SQL Server, SMB, Exchange, Windows Service).
- Open questions: [docs/15-open-questions.md](docs/15-open-questions.md) (CSR_Server exact watch path, intranet hostname, SQL instance, quality mailbox, etc.).

When you are ready to build, that is a **new application repo**, not more files pretending to be the portal inside this specs repo — unless you explicitly decide to expand this repo later.
