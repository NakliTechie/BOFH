# BOFH — Browser-Native Dev Toolkit

**One HTML file. Twenty tools. Zero data leaving your device.**

Named after the [Bastard Operator From Hell](https://en.wikipedia.org/wiki/Bastard_Operator_from_Hell) — because your tokens, keys, and logs deserve better than some random website's S3 bucket.

> *Stop pasting your secrets into the internet.*

Open in browser → [naklitechie.github.io/BOFH](https://naklitechie.github.io/BOFH/) *(once published)*

---

## Why

Every developer keeps 20+ browser tabs open for the same mundane transformations: jwt.io, regex101, jsonformatter.org, base64encode.org, epochconverter.com…

Every one of those sites receives your input. JWTs with production auth tokens. JSON responses with PII. Regex patterns mining your logs.

BOFH does it all locally. Single HTML file. Open it from anywhere — GitHub Pages, `python3 -m http.server`, a `file://` URL, any static host. No build step, no npm, no framework. No telemetry, no fonts loaded from a CDN, no third-party scripts.

---

## What's in it (Phase 1)

| Module | What it does |
|---|---|
| **JSON** | Format, validate, minify, collapsible tree view, JSONPath query |
| **JWT** | Decode header/payload, verify HS256/384/512 and RS256/384/512, expiry & nbf checks, claim highlights |
| **Base64** | Encode/decode text and files, URL-safe variant |
| **Timestamp** | Unix epoch ↔ human, timezone-aware (`Intl`), relative time |
| **UUID** | Generate v4 (random) and v7 (time-ordered, database-friendly), bulk, parse & validate |

Phase 2 (next): YAML, CSV, SQL, Diff, Hash, URL, Regex, Keys, Markdown, Log Viewer, HTTP Status, User Agent, Color, IP/Subnet, Cron.

---

## How

- **One HTML file** — markup, CSS, and ~1300 lines of JS, all inline
- **Vanilla JS, no framework** — each module is a self-contained object with an `init(container)` method, lazy-initialised on first tab open
- **Hash routing** — every module has a linkable URL (`#json`, `#jwt`, …)
- **State persistence** — each module saves its last input and settings to `localStorage` under `bofh:<module>:<key>`. Wipe with the `⌫` button in the sidebar foot.
- **Dark mode default**, light mode toggle, follows `prefers-color-scheme` on first visit
- **Web Crypto API** for the JWT verifier — same primitives your OS uses, no JS crypto libraries
- **Mobile-friendly** — sidebar collapses to a hamburger menu

### Keyboard shortcuts

- `/` — focus the module filter
- `?` — open help
- `Esc` — close modal / blur input

---

## Run it

```bash
git clone https://github.com/NakliTechie/BOFH.git
cd BOFH
python3 -m http.server 8000
# open http://localhost:8000
```

Or just open `index.html` directly. Or drop it on any static host.

---

## Privacy

Your inputs are stored only in your own browser's `localStorage`. Nothing is sent over the network — there are zero `fetch` calls in Phase 1. The file is ~1300 lines of JS and ~50 KB total. Read it.

---

## Part of the [NakliTechie](https://naklitechie.github.io/) series

Single-file, browser-native tools that don't phone home. Sister projects:

- [BabelLocal](https://github.com/NakliTechie/BabelLocal) — translator for 200 languages
- [VoiceVault](https://github.com/NakliTechie/VoiceVault) — Whisper transcription
- [SnipLocal](https://github.com/NakliTechie/SnipLocal) — background remover
- [VaultMind](https://github.com/NakliTechie/VaultMind) — Obsidian explorer + AI chat
- [NakliPoster](https://github.com/NakliTechie/NakliPoster) — local-first API client
- [KanZen](https://github.com/NakliTechie/KanZen) — local-first kanban

Built by [@NakliTechie](https://github.com/NakliTechie).

## License

MIT
