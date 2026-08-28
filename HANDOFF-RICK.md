# Handoff for Rick — clone this specs repo onto `rickguptilltwin`

Send Rick this file (or the GitHub URL after it is on `main`). His Cursor **Agent** should run the migration. This is **not** Twin. This is **not** CSR_Server source.

**Source (public):** https://github.com/bmalone2022/program-verification-specs  
**Target:** create **`rickguptilltwin/program-verification-specs`** (new repo, full git history, same `main`).

**Click-through mock-up (test in a browser after clone):** [prototypes/program-verification-prototype_v1.html](prototypes/program-verification-prototype_v1.html) — see [prototypes/README.md](prototypes/README.md).

Brett Malone (`bmalone2022`) authored the phase-0 specs. Rick owns CSR_Server on the plant network. After migrate, Rick’s GitHub is the working copy; keep Brett as a collaborator.

---

## What Rick’s agent must do

1. Confirm GitHub CLI / git is signed in as **`rickguptilltwin`** (`gh auth status` → that user).
2. Clone **all history** from the source (do not download a ZIP; do not copy files into an empty repo without `.git`).
3. Create **`rickguptilltwin/program-verification-specs`** if it does not exist. Do **not** force-push over an unrelated existing repo. If the name is taken by something else, stop and ask Rick.
4. Push `main` (and any tags) to the new origin.
5. Set remotes: `origin` = Rick’s repo; optional `upstream` = `bmalone2022/program-verification-specs`.
6. Invite **`bmalone2022`** as a collaborator with **Write**.
7. Open the cloned folder as the Cursor workspace (**not** Twin / twin87-data-viewer / twinapps).
8. Confirm `testdata/cowl-4-golden/` has CATPart, RMCD, tool list, ETR PDF, annotated JPG.
9. Stop. Do **not** scaffold the portal application unless Rick explicitly asks.

Visibility: the source is **public**. Match that unless Rick says private.

---

## Commands (agent may adapt paths)

```bash
git clone https://github.com/bmalone2022/program-verification-specs.git
cd program-verification-specs
git remote rename origin upstream
gh repo create program-verification-specs --public --source=. --remote=origin --push
git branch -u origin/main main
gh api -X PUT repos/rickguptilltwin/program-verification-specs/collaborators/bmalone2022 -f permission=push
```

SSH variant if that is how Rick’s machine talks to GitHub:

```bash
git clone git@github.com:bmalone2022/program-verification-specs.git
cd program-verification-specs
git remote rename origin upstream
gh repo create program-verification-specs --public --source=. --remote=origin --push
```

Windows (example home):

```powershell
git clone https://github.com/bmalone2022/program-verification-specs.git "$env:USERPROFILE\program-verification-specs"
cd "$env:USERPROFILE\program-verification-specs"
```

Then Cursor → **File → Open Folder** on that directory.

---

## Paste this into Rick’s new Cursor Agent chat

```text
Migrate Program Verification specs onto my GitHub.

Source (public, clone with full git history, not a zip):
https://github.com/bmalone2022/program-verification-specs

Create a NEW repo on the account I am authenticated as:
rickguptilltwin/program-verification-specs

Push main with history. Set origin to my new repo. Keep upstream pointing at bmalone2022/program-verification-specs. Invite collaborator bmalone2022 with Write. Open this folder as the Cursor workspace.

This repo is SPECIFICATIONS ONLY. It is not Twin. It is not CSR_Server source. Do not scaffold the application unless I explicitly ask. Do not use Google Drive, Cloud Run, SendGrid, or MinIO as the production design.

Read CHARTER.md, docs/00-index.md, docs/10-architecture.md, docs/09-file-and-job-contract.md, docs/13-phasing.md, and HANDOFF.md after the clone.

Locked plant stack: Windows Server + IIS; React+TS SPA as static files (Node is build-only); ASP.NET Core LTS /api; SQL Server; NTFS+SMB inbox/outbox for CSR_Server; Windows Service worker; Exchange/SMTP with SQL email log; demo login for now. Status page is home. Annotated exclusion screenshots required on submit unless No visual exclusions. Golden files: testdata/cowl-4-golden/

CSR_Server is my on-network RMCD verifier. Integration is a folder contract (inbox/outbox). Do not rewrite CSR_Server.

If rickguptilltwin/program-verification-specs already exists and is not this project, STOP and tell me.

When done, print: clone path, origin URL, upstream URL, gh repo view visibility, and whether testdata/cowl-4-golden files are present. Then wait.
```

---

## After migrate (Rick)

- Working URL should be `https://github.com/rickguptilltwin/program-verification-specs`
- Brett’s copy remains at `https://github.com/bmalone2022/program-verification-specs` until you agree which is canonical
- Point future app work at a **new application repo**, not this specs tree
- Open questions still in `docs/15-open-questions.md` (your CSR_Server watch path is the important one)

## What not to copy

- Twin 87 / twinapps
- CSR_Server binaries or source (stays on Rick’s plant machine)
- SendGrid keys, Google Drive JSON, Cloud Run configs
