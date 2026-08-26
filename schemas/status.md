# outbox status.json schema (optional)

CSR_Server may write `outbox/{jobId}/status.json`. If absent, the worker infers completion from `ace_verification_results*`.

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://ac-e.local/program-verification/schemas/status.json",
  "title": "ProgramVerificationOutboxStatus",
  "type": "object",
  "additionalProperties": false,
  "required": ["state"],
  "properties": {
    "state": {
      "type": "string",
      "enum": ["complete", "failed"]
    },
    "message": {
      "type": "string",
      "maxLength": 4000
    },
    "completedAt": {
      "type": "string",
      "format": "date-time"
    }
  }
}
```

`complete` means the agent finished a run (program may still fail checks). `failed` means the agent could not run verification.
