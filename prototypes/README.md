# Prototypes

Twin-matched visual language for Program Verification mock-ups.

| File | Role |
|------|------|
| [style-guide.md](style-guide.md) | Palette + icon construction (same hex values and glyph rules as Twin 87) |
| [program-verification-prototype_v1.html](program-verification-prototype_v1.html) | Click-through UI (login, status, submit, job detail) |
| [program-verification-prototype_v1.md](program-verification-prototype_v1.md) | Same markup, kept as `.md` for editors that treat it as text |

## Open on GitHub (after clone)

GitHub will show HTML as source, not a live app. Clone or download the file, then:

```powershell
python -m http.server 8090 --directory prototypes
```

Open [http://localhost:8090/program-verification-prototype_v1.html](http://localhost:8090/program-verification-prototype_v1.html)

Or open `program-verification-prototype_v1.html` in a browser (double-click). If scripts are blocked, use the localhost server.

**Walkthrough:** Continue on login → Status table → click **Cowl 4** (fail), **Spar cap** (pass), or **Door surround** (stuck) → **New job** for the submit package.

Live file on `main`:  
https://github.com/bmalone2022/program-verification-specs/blob/main/prototypes/program-verification-prototype_v1.html
