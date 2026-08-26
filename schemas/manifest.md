# manifest.json schema

Written to `inbox/{jobId}/manifest.json` when a job is queued.

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://ac-e.local/program-verification/schemas/manifest.json",
  "title": "ProgramVerificationJobManifest",
  "type": "object",
  "additionalProperties": false,
  "required": [
    "jobId",
    "projectName",
    "submitterEmail",
    "notifyEmails",
    "createdAt",
    "noVisualExclusions",
    "artifacts"
  ],
  "properties": {
    "jobId": {
      "type": "string",
      "format": "uuid"
    },
    "projectName": {
      "type": "string",
      "minLength": 1,
      "maxLength": 200
    },
    "submitterEmail": {
      "type": "string",
      "format": "email"
    },
    "notifyEmails": {
      "type": "array",
      "minItems": 1,
      "items": { "type": "string", "format": "email" }
    },
    "createdAt": {
      "type": "string",
      "format": "date-time"
    },
    "noVisualExclusions": {
      "type": "boolean"
    },
    "artifacts": {
      "type": "array",
      "items": { "$ref": "#/$defs/artifact" }
    }
  },
  "$defs": {
    "artifact": {
      "type": "object",
      "additionalProperties": false,
      "required": ["kind", "path", "originalFileName", "sha256", "sizeBytes"],
      "properties": {
        "kind": {
          "type": "string",
          "enum": [
            "part",
            "program",
            "tool_list",
            "engineering_request",
            "annotated_image"
          ]
        },
        "path": {
          "type": "string",
          "description": "Relative to the job inbox root, e.g. part.CATPart or annotated/01.png"
        },
        "originalFileName": { "type": "string" },
        "sha256": {
          "type": "string",
          "pattern": "^[a-fA-F0-9]{64}$"
        },
        "sizeBytes": { "type": "integer", "minimum": 0 }
      }
    }
  }
}
```
