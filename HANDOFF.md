# VidWright — Project Handoff & Session Log

> Read this first if you're a new session (human or agent) picking up VidWright.
> It records what this is, what we forked from, what was done, what's left, and how to build/run it.

---

## What this is

**VidWright** — an open-source, AI-native video editor that an AI agent can fully operate
(edit timelines, generate media through ComfyUI, mix audio) locally, via a built-in MCP server.

**VidWright is a GPL-3.0-only fork of [Velorn](https://github.com/VelornLabs/velorn)**
(© Velorn contributors). It is an independent project, **not affiliated with or endorsed by
the Velorn maintainers**. See [`NOTICE`](NOTICE) and [`LICENSE`](LICENSE).

## Provenance — what we forked from

| | |
|---|---|
| Upstream | `VelornLabs/velorn` |
| Fork point | upstream `main` @ commit **70d1ca9** |
| Forked | 2026-07-10 |
| This fork | `github.com/datbird/vidwright` (public GitHub fork) |
| Remotes | `origin` → datbird/vidwright · `upstream` → VelornLabs/velorn |

Pull future upstream changes with: `git fetch upstream && git merge upstream/main`
(expect conflicts in the mega-files — see "Gotchas").

## Current state (as of 2026-07-11)

All rebrand + branding work landed on **`main`** (merged from the `rebrand-vidwright` branch).
Commits on top of the fork point:

- `eb2a879` — Rebrand: Velorn/ComfyStudio → VidWright (naming only)
- `34d3ec6` — README: new tagline + description, align casing to VidWright
- `9882383` — Add VidWright app icon set + brand assets
- `(+)` — Splash + README banner + this handoff doc

## What was done this session

1. **Security review of upstream** before forking (static review, not a pentest). Headline:
   security-conscious codebase, **no malicious/backdoor code**. Watch items:
   - Local MCP server binds `127.0.0.1` but has **no auth token** — any local process can drive its tools.
   - The workflow-dependency installer git-clones node packs + `pip install`s them = informed-consent
     supply chain (well-validated: github/gitlab https-only, path-traversal-safe, preview+approve).
   - `npm audit`: 28 vulns (2 critical / 16 high), mostly dev toolchain.
2. **Rebrand (naming only, zero functional changes).** Whole-token rename
   `Velorn`/`ComfyStudio` → `VidWright`/`vidwright` across 171 files + renamed brand files/dirs.
   All real **ComfyUI** (external tool) references left untouched. `appId` = `com.vidwright.app`,
   custom protocol `vidwright://`, storage keys `vidwright-*`.
3. **GPL compliance.** `LICENSE` untouched (GPL-3.0-only); added `NOTICE` crediting Velorn;
   README attribution. Original authorship preserved.
4. **Branding.** New app icon set generated from `brand/vidwright-logo.png` (3834² transparent
   master) → `build/icon.png` + `build/icon.ico` + `build/icon.icns` + `build/icons/*`. Wordmark
   master in `brand/`. Splash (`public/splash.png` + `.jpg`) = wordmark on brand-dark.
   README banner at `docs/readme/wordmark-banner.png`.
5. **Copy.** README tagline + description rewritten; name styled **VidWright**.

## Brand assets — source of truth

- `brand/vidwright-logo.png` — 3834×3834 transparent logo master
- `brand/vidwright-wordmark.png` — 4791×931 transparent wordmark master
- Palette: `#6D5BFF` `#985CFF` `#00D4FF` `#0F0F1A` (dark base) `#E6E8FF` · Font: **Poppins**
- Regenerate icons from a 1024² `build/icon.png` via `npm run icons:generate` (uses `icon-gen`),
  or the Pillow method used this session (resize 3834² master → 16/24/32/48/64/128/256/512/1024,
  `.ico` sizes ≤256, `.icns` from 1024).

## TODO — what is NOT done yet

- [ ] **Scene assets still show Velorn art** (need background scenes, or composite the wordmark):
      `public/hero-v1.webp`, `public/vidwright-home-balanced-plate-4.webp`,
      `public/Vidwright_Project_Selection_Screen_BG.png` (5532×3072),
      `public/welcome-hero.mp4`, `public/vidwright-project-selection-page.mp4`.
- [ ] **Product screenshots** `docs/readme/*.png` still show old in-app branding — re-shoot after a rebranded build.
- [ ] **Links:** Discord invite still points to Velorn's server (`discord.gg/QWZUuUChVK`);
      `x.com/getvidwright` and `vidwright.ai` are placeholders — register or update.
- [ ] **Name casing:** README/brand use "VidWright"; app `productName` + in-app strings still "Vidwright".
      Decide, then optional sweep (keep lowercase `vidwright` for identifiers/appId/protocol/URLs).
- [ ] **Smoke-test the renamed ComfyUI bridge** (`electron/comfyui-injected/vidwright_bridge`) against a live ComfyUI.
- [ ] **Dependencies:** bump electron (<35.7.5 ASAR bypass), lodash, axios, form-data, tar when convenient.
- [ ] **Tests:** upstream has none — consider smoke tests around timeline/export/keyframe math.
- [ ] **Light/dark:** one wordmark currently used for both modes; add a light-background variant later.

## Build / install / run (Windows testing)

**Prereqs:** Node.js 20 LTS+ and npm (no version pinned; 20/22 LTS recommended), Git.
For generation features you also need a **running ComfyUI** (connect in-app: Settings → ComfyUI,
default `http://127.0.0.1:8188`).

```bash
git clone https://github.com/datbird/vidwright.git
cd vidwright
npm install

# dev (vite + electron, hot reload):
npm run electron:dev

# build a Windows installer + portable (electron-builder → dist/):
npm run electron:build:win
```

Other targets: `electron:build:mac`, `electron:build:linux`; web-only preview: `npm run dev`.

> **No packaged releases are published on this fork yet — you build from source.**
> Windows SmartScreen will warn on the self-built unsigned `.exe` (expected). Code-signing is a later task.

## Gotchas for the next session

- **Mega-files** make upstream merges painful: `electron/mcpServer.js` (~13.8k lines),
  `src/components/GenerateWorkspace.jsx` (~18k), `src/stores/timelineStore.js` (~5.4k),
  `src/services/mcpActions.js` (~7.9k). Keep your changes **additive / isolated** to minimize conflicts.
  Consider extending via a **separate companion MCP server** instead of editing the monoliths.
- **Don't rename `comfyui`/`ComfyUI`** — that's the external dependency, not our brand.
- The fork is **public** (GitHub forks of public repos can't be made private without a detached mirror).

## Key facts

- Repo: `github.com/datbird/vidwright` — fork of `VelornLabs/velorn` — **GPL-3.0-only**
- `appId`: `com.vidwright.app` · protocol: `vidwright://` · storage keys: `vidwright-*`
- Stack: Electron + Vite + React + Zustand; media via FFmpeg (bundled) + WebCodecs/WebGL; ComfyUI over HTTP/WS; MCP server on `127.0.0.1`.
