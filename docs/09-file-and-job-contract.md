# File and job contract

Canonical JSON Schemas (as markdown until the application repo exists):

- [`../schemas/manifest.md`](../schemas/manifest.md)
- [`../schemas/annotated-index.md`](../schemas/annotated-index.md)
- [`../schemas/status.md`](../schemas/status.md)

## Root volume

Plant default (configurable):

```
D:\ProgramVerification\
  inbox\{jobId}\
  outbox\{jobId}\
```

UNC equivalent if CSR_Server is another machine: `\\fileserver\ProgramVerification\`.

## Inbox

```
inbox\{jobId}\
  manifest.json
  part.CATPart
  program.rmcd
  tool_list.txt
  engineering_request.pdf
  annotated\index.json
  annotated\01.png
  annotated\02.png
```

Portal writes **normalized** names so the agent does not depend on programmer filenames. Original names and SHA-256 live in `manifest.json`.

If **No visual exclusions** is checked, `annotated\` may be omitted and `manifest.noVisualExclusions` is true.

## Outbox

```
outbox\{jobId}\
  ace_verification_results.txt
  status.json                 # optional
  screenshots\                # optional agent captures
```

The worker treats any file matching `ace_verification_results*` as the results payload (legacy naming).

## Checksums

`manifest.json` lists `sha256` per artifact. The worker may re-hash after write. CSR_Server is not required to verify hashes in v1.
