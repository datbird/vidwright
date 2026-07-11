<div align="center">

# VidWright

**AI-native video editing — fully local, fully agent-driven.**

[![Latest Release](https://img.shields.io/github/v/release/datbird/vidwright?label=Latest&color=6C63FF)](https://github.com/datbird/vidwright/releases/latest)
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue)](LICENSE)
[![Platforms](https://img.shields.io/badge/Platforms-Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-444444)](https://github.com/datbird/vidwright/releases/latest)

[![Website](https://img.shields.io/badge/Website-vidwright.ai-0A9396)](https://vidwright.ai)
[![Follow on X](https://img.shields.io/badge/Follow-%40getvidwright-000000?logo=x&logoColor=white)](https://x.com/getvidwright)
[![Join our Discord](https://img.shields.io/badge/Discord-Join%20the%20community-5865F2?logo=discord&logoColor=white)](https://discord.gg/QWZUuUChVK)

[![Download for Windows](https://img.shields.io/badge/Windows-Download-0078D4?style=for-the-badge)](https://github.com/datbird/vidwright/releases/latest)
[![Download for macOS](https://img.shields.io/badge/macOS-Download-1a1a1a?style=for-the-badge&logo=apple&logoColor=white)](https://github.com/datbird/vidwright/releases/latest)
[![Download for Linux](https://img.shields.io/badge/Linux-Download-E95420?style=for-the-badge&logo=linux&logoColor=white)](https://github.com/datbird/vidwright/releases/latest)

English · [Español](docs/i18n/README.es.md) · [简体中文](docs/i18n/README.zh-CN.md) · [日本語](docs/i18n/README.ja.md) · [한국어](docs/i18n/README.ko.md) · [Português (Brasil)](docs/i18n/README.pt-BR.md) · [Français](docs/i18n/README.fr.md)

</div>

<p align="center"><img src="docs/readme/agent-editing.gif" alt="One prompt: Claude builds the edit in VidWright via MCP" width="860"></p>
<p align="center"><i>One prompt. The agent generates media, builds the timeline, and mixes the audio — live, via MCP.</i></p>

> **VidWright is a fork of [Velorn](https://github.com/VelornLabs/velorn)** (© Velorn contributors), released under **GPL-3.0-only**. It is an independent project and is not affiliated with or endorsed by the Velorn maintainers. See [NOTICE](NOTICE) for attribution.

VidWright is an open-source, AI-native video editor that your AI agent can fully operate — editing timelines, generating media through ComfyUI, and mixing audio, all locally on your machine. It brings planning, generation, asset management, timeline editing, captions, effects, and export into one project-based app.

Use built-in local and cloud workflows, bring your own ComfyUI API workflow JSON, or install the bundled VidWright Bridge so a graph open in ComfyUI can be sent back into VidWright.

<p align="center">
  <img src="docs/readme/editor-timeline.png" alt="VidWright editor with generated assets, preview, timeline tracks, and inspector" />
</p>

## What VidWright Is For

- Creating music videos from lyrics, timing, characters, keyframes, video shots, and timeline edits.
- Building UGC-style creator ads and small-business ads with editable shot plans.
- Running curated local and cloud image/video workflows from one Generate workspace.
- Running custom ComfyUI image, video, keyframe, and music-video workflows inside the app.
- Editing generated clips with tracks, transitions, effects, captions, proxy/cache tools, and export.
- Keeping generated media, prompts, workflow outputs, and timelines organized inside a project.

VidWright is not a replacement for ComfyUI. It is the production layer around ComfyUI: plan the work, send jobs to ComfyUI, collect the outputs, and finish the edit.

<p align="center">
  <img src="docs/readme/create-workflows.png" alt="VidWright Create workspace with UGC, business ad, music video, and short film creators" />
</p>

## Download

Most users should download the packaged desktop app from the [GitHub Releases page](https://github.com/datbird/vidwright/releases).

Release assets include:

- `Windows Installer`
- `Windows Portable`
- `Mac (Apple Silicon)`
- `Mac (Intel)`
- `Linux AppImage`
- `Linux deb`

Ignore GitHub's auto-generated source-code archives unless you plan to build VidWright from source.

## Main Features

### Generate

Generate runs built-in local workflows, cloud/partner workflows, and custom ComfyUI workflows.

- Local image, video, image-edit, audio, and utility workflows.
- Cloud workflows such as Nano Banana 2, GPT Image 2, Seedance, Kling, and other partner-node routes where available.
- Custom Image and Custom Video workflows for users who want VidWright to run their own ComfyUI API graphs.
- API JSON import for advanced users who prefer exporting workflows manually from ComfyUI.
- VidWright Bridge support so compatible graphs can be sent from ComfyUI back to the correct VidWright panel.
- Workflow setup checks for missing nodes, models, credentials, and configuration.
- A Featured / My Workflows / Templates browser with Local and Cloud filters. Imported community workflows appear in Featured next to the built-ins.

<p align="center">
  <img src="docs/readme/generate-featured.png" alt="VidWright Generate browser with Featured workflows, Local and Cloud filters, and the dependency checker" />
</p>

The Templates tab browses the official ComfyUI template catalog (500+ templates with size and popularity info) and launches any of them into the embedded ComfyUI tab.

<p align="center">
  <img src="docs/readme/generate-templates.png" alt="VidWright Templates browser showing the official ComfyUI template catalog with categories and filters" />
</p>

### Create

Create contains guided creator workflows built on VidWright's Director Mode engine.

- **Music Video Creation** - turns a song, lyric timing, characters, references, and a director script into keyframes, video shots, and an editable timeline.
- **UGC Creator** - builds creator-style social ads with hooks, dialogue, product demos, try-ons, testimonials, and editable shot-by-shot outputs.
- **Business Ad Creator** - builds offer-first ads for local businesses, ecommerce products, events, services, and small teams.
- **Short Film Creation** - experimental script-to-scene coverage workflow. This is still very beta and may have rough edges.

### Music Video Creation

The Music Video Creator supports:

- Song import and lyric timing.
- ASR transcription or pasted-lyrics alignment into SRT.
- People/cast setup, including existing character sheets.
- Per-shot keyframe prompts, reference images, prompt copy, prompt editing, image replacement, and shot reruns.
- Built-in keyframe routes such as Qwen Image Edit and Nano Banana 2.
- Custom keyframe workflows using VidWright endpoint nodes.
- Built-in video routes such as LTX 2.3 Music and WAN 2.2.
- Custom video workflows with optional injected keyframe image, prompt, seed, width, height, FPS, duration, and audio.
- Timeline assembly from generated shot assets.

### Timeline Editor

The editor includes:

- Project asset browser.
- Multi-track video/audio timeline.
- Clip trimming, moving, snapping, overlap replacement behavior, and transitions.
- Text, shape, title, solid-color, adjustment-layer, keyframe, and visual effect tools.
- Inspector controls.
- Proxy/cache tools for smoother playback.
- Export panel for final renders.

### Captions

Captions can be generated from edited timeline audio and styled in-app.

- Timeline-aware transcription.
- Caption style presets.
- Font, color, outline, background, shadow, and animation controls.
- Saved caption style presets for reuse.
- Live preview with play/scrub controls and safe-zone overlays.
- Export-ready caption renders.

### Export

The Export tab includes practical render presets, hardware-accelerated options where available, queue controls, and project-aware output settings.

<p align="center">
  <img src="docs/readme/export-settings.png" alt="VidWright export settings with presets, codec controls, and export queue" />
</p>

### Stock

The Stock tab uses Pexels so you can search and import photos or videos directly into the current project. A Pexels API key is optional and can be added in Settings.

<p align="center">
  <img src="docs/readme/stock-pexels.png" alt="VidWright Stock tab with Pexels photo and video search" />
</p>

### ComfyUI Integration

VidWright talks to a local ComfyUI server and can also help launch it.

- Default endpoint: `http://127.0.0.1:8188`
- Custom port support in Settings.
- Windows launcher support for a configured ComfyUI start script.
- macOS launcher support for a configured `ComfyUI.app`.
- Optional auto-start, stop-on-quit, and restart behavior.
- Embedded ComfyUI tab for opening and editing graphs.
- ComfyUI account login support inside the embedded ComfyUI tab.
- ComfyUI credit balance display when available.

Only localhost/loopback ComfyUI endpoints are supported in the desktop app.

### AI Agents (MCP)

VidWright includes a local MCP server with 100+ tools for Codex, Claude Code, Cursor-compatible tools, and other MCP clients.

- Endpoint: `http://127.0.0.1:19790/mcp`
- In-app setup: `Settings > Agents (MCP)` (one copy-paste command per client)
- Guide: [docs/MCP.md](docs/MCP.md)

Agents can inspect the open project, review timeline frames and visible shots, troubleshoot ComfyUI setup, preview safe timeline edits, queue approved generation work, and start delivery exports.

Agents can also bring in community ComfyUI workflows: hand one a workflow link or file, and it analyzes the graph, reports missing custom nodes and models, installs them after your approval, and runs the workflow on your timeline assets.

Write tools preview their plan first and apply only after approval, on VidWright's normal undo stack. MCP is the recommended automation path for agent-assisted review, timeline operations, graphics polish, and generation workflows.

<p align="center">
  <img src="docs/readme/agents-mcp.png" alt="VidWright Agents (MCP) settings with the running local server, connect commands, and the full tool list" />
</p>

## Custom Workflows

Custom workflows are one of the main reasons VidWright exists.

Advanced users can:

1. Open a starter graph from VidWright.
2. Modify it in ComfyUI.
3. Keep the required VidWright endpoint nodes.
4. Send it back with the VidWright Bridge or import the API workflow JSON manually.
5. Run that graph from VidWright as part of a creator flow or from Generate.

Common VidWright endpoint node titles include:

- VidWright input image - `VIDWRIGHT_INPUT_IMAGE`
- VidWright prompt - `VIDWRIGHT_PROMPT`
- VidWright seed - `VIDWRIGHT_SEED`
- VidWright width - `VIDWRIGHT_WIDTH`
- VidWright height - `VIDWRIGHT_HEIGHT`
- VidWright FPS - `VIDWRIGHT_FPS`
- VidWright duration - `VIDWRIGHT_DURATION`
- VidWright audio - `VIDWRIGHT_AUDIO`
- VidWright output image - `VIDWRIGHT_OUTPUT_IMAGE`
- VidWright output video - `VIDWRIGHT_OUTPUT_VIDEO`

Exact `VIDWRIGHT_*` titles are preferred, but VidWright also recognizes readable titles such as `VidWright input image`. Older graphs that still use `COMFYSTUDIO_*` marker titles are supported for backward compatibility.

If an endpoint is present, VidWright can inject that value. If an endpoint is not present, the graph controls that setting itself.

<p align="center">
  <img src="docs/readme/comfyui-bridge.png" alt="Embedded ComfyUI graph with VidWright endpoint nodes and Send to VidWright button" />
</p>

## Requirements

Minimum for normal app use:

- A separately installed local ComfyUI.
- Enough disk space for generated media and project assets.

Optional integrations:

- Comfy account login or API key for paid partner-node workflows.
- Pexels API key for the Stock tab.
- LM Studio for the local LLM Assistant.

Local workflow requirements vary by model. Some workflows can run on modest GPUs, while heavy video workflows may need 24 GB+ VRAM. Cloud workflows shift most of that requirement to the provider but may require credits.

## First Run

1. Install and launch VidWright.
2. Choose a projects folder.
3. Create or open a project.
4. Configure ComfyUI in `Settings > ComfyUI Connection`.
5. Use `VidWright > Getting Started` from the bottom menu if you want the guided setup path.

If ComfyUI is running on a non-default port, update the endpoint in Settings and run the connection test.

## ComfyUI Setup Notes

VidWright ships workflow JSON files, but workflows still need the correct ComfyUI environment.

Depending on the workflow, users may need:

- Custom nodes installed in ComfyUI.
- Model files in the expected folders.
- Cloud/partner credentials.
- Enough local VRAM for the selected model and resolution.

VidWright 0.2.1+ talks to local ComfyUI without any CORS setup. On older VidWright versions, launch ComfyUI with `--enable-cors-header` if the embedded tab is blank or API calls return 403.

Inside Generate, use the workflow setup and dependency tools when something is missing.

## Run From Source

For development, run the Electron app:

```bash
npm install
npm run electron:dev
```

Browser-only `npm run dev` is useful for frontend work, but Electron is the normal development path because many features depend on desktop APIs.

## Build Commands

```bash
npm run build
npm run electron:build:win
npm run electron:build:mac
npm run electron:build:linux
```

Packaged artifacts are written to `release/`.

For release process details, see:

- `docs/RELEASE_PROCESS.md`
- `docs/CI_SECRETS.md`
- `docs/AI_RELEASE_HANDOFF.md`

## Roadmap

See [ROADMAP.md](ROADMAP.md).

<p align="center">
  <a href="ROADMAP.md">
    <img src="docs/roadmap-overview.svg" alt="VidWright roadmap overview" />
  </a>
</p>

## Contributing

VidWright is open source, and contributions are welcome.

See:

- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`
- `SECURITY.md`

## License

VidWright is licensed under the GNU General Public License v3.0. See `LICENSE`.

Versions released before this license change remain available under the license terms they were released with.
