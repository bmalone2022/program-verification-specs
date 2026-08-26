# Annotated screenshots

Engineers mark regions of the CAD part that **must not appear in the program** (no-drill, no-trim, keep-out). This is a first-class input, equal in importance to the RMCD and the engineering tool request.

The Cowl 4 example uses red boxes over hole rows the ETR forbids, plus a yellow marker for the allowed origin of the first ten holes.

## Why the prototype was wrong

V2 treated the annotated image as a fifth upload mainly for Gemini “no-drill” AI. Production does **not** depend on cloud AI. Humans and CSR_Server (if/when it consumes images) need the pixels **and** captions retained for audit, the status page, and the PDF.

## Rules

- At least one image unless **No visual exclusions** is checked.
- Formats: PNG, JPEG, WebP. Suggested cap: 20 MB per file, max 20 files per job.
- Each image may have a short caption (zone letter, instruction).
- Stored as `inbox\{jobId}\annotated\01.png` … and `annotated\index.json` (schema in [`../schemas/annotated-index.md`](../schemas/annotated-index.md)).
- Shown as thumbnails on the status list and full size on job detail.
- Embedded in the results PDF.
- Included in the CSR_Server inbox even if the agent ignores images today.

## Relationship to the ETR

The engineering PDF often says “do not drill holes annotated with red box.” Screenshots are the visual counterpart. The portal does not automatically OCR the PDF in this phase.
