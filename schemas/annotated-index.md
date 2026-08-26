# annotated/index.json schema

Written to `inbox/{jobId}/annotated/index.json`.

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://ac-e.local/program-verification/schemas/annotated-index.json",
  "title": "ProgramVerificationAnnotatedIndex",
  "type": "object",
  "additionalProperties": false,
  "required": ["jobId", "images"],
  "properties": {
    "jobId": { "type": "string", "format": "uuid" },
    "images": {
      "type": "array",
      "minItems": 1,
      "items": {
        "type": "object",
        "additionalProperties": false,
        "required": ["file", "sortOrder"],
        "properties": {
          "file": {
            "type": "string",
            "description": "Filename in this folder, e.g. 01.png"
          },
          "sortOrder": { "type": "integer", "minimum": 1 },
          "caption": {
            "type": "string",
            "maxLength": 500,
            "description": "Zone name or instruction such as do not drill"
          }
        }
      }
    }
  }
}
```

Omit this file when `manifest.noVisualExclusions` is true.
