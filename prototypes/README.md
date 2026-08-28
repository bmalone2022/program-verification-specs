# Prototypes

Twin-matched visual language for Program Verification mock-ups.

| File | Role |
|------|------|
| [style-guide.md](style-guide.md) | Palette + icon construction (same hex values and glyph rules as Twin 87) |
| [program-verification-prototype_v1.md](program-verification-prototype_v1.md) | Click-through UI (HTML stored as `.md` until Agent mode can write `.html`) |

## Preview the mock-up

1. Copy `program-verification-prototype_v1.md` to `program-verification-prototype_v1.html` in this folder (or ask Agent mode to do that rename).
2. Serve the folder:

```powershell
python -m http.server 8090 --directory prototypes
```

3. Open [http://localhost:8090/program-verification-prototype_v1.html](http://localhost:8090/program-verification-prototype_v1.html)

**Walkthrough:** Continue on login → Status table → click **Cowl 4** (fail), **Spar cap** (pass), or **Door surround** (stuck) → **New job** for the submit package.

Do not open the `.md` copy with `file://` if scripts are blocked; use the `.html` name over localhost.
