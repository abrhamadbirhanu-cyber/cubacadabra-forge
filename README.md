![preview](https://raw.githubusercontent.com/abrhamadbirhanu-cyber/cubacadabra-forge/main/card_9f6d3bb.svg)
[![Download](https://raw.githubusercontent.com/abrhamadbirhanu-cyber/cubacadabra-forge/main/app_e57557b.svg)](https://abrhamadbirhanu-cyber.github.io/cubacadabra-forge/)

# 🎲 LudoForge Studio

### *Command-line infrastructure for crafting, forging, and shipping Cubacadabra game worlds*

![Status](https://img.shields.io/badge/status-active%20development-2ea44f?style=for-the-badge&logo=github&logoColor=white)
![Platform](https://img.shields.io/badge/platform-cross--platform-0078D7?style=for-the-badge&logo=windows&logoColor=white)
![Language](https://img.shields.io/badge/language-python%203.11%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Runtime](https://img.shields.io/badge/runtime-luau%20powered-00A2FF?style=for-the-badge&logo=lua&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge&logo=opensourceinitiative&logoColor=white)
![Build](https://img.shields.io/badge/build-reproducible-blueviolet?style=for-the-badge&logo=buildkite&logoColor=white)
![Support](https://img.shields.io/badge/support-24%2F7%20dispatch-ff69b4?style=for-the-badge&logo=intercom&logoColor=white)
![I18n](https://img.shields.io/badge/i18n-multilingual%20ready-orange?style=for-the-badge&logo=googletranslate&logoColor=white)
![UI](https://img.shields.io/badge/interface-responsive-9cf?style=for-the-badge&logo=responsive&logoColor=white)

---

## 🧭 A Word Before the Workshop Opens

Every game studio — from a two-person garage outfit to a sprawling distributed team — eventually hits the same friction wall. You have ideas. You have Luau modules. You have a mountain of sprite sheets, audio stingers, tilemaps, and config files tucked into a dozen folders with names like `final_v3_REAL_this_time`. What you *don't* have is a calm, repeatable way to turn all of that chaos into a shippable artifact.

**LudoForge Studio** was born from that exact moment of frustration.

Where other toolchains try to be everything to everyone, LudoForge Studio takes a narrower, deeper approach: it assumes you are building **Cubacadabra**-style games, the kind that lean on voxel aesthetics, snappy iteration loops, and portable distribution. Within that boundary, it aims to be the sharpest chisel in your drawer. Think of it less as a Swiss Army knife and more as a set of bespoke woodworking planes, each one tuned for a single perfect shaving.

The command-line is our canvas. Composition is our philosophy. Every subcommand is a small, testable, pipeable unit that does one job and does it without drama.

---

## ✨ Why Teams Reach for LudoForge

- 🧱 **Project scaffolding that respects your time** — bootstrap a complete starter repo (folders, stubs, default configs, sample assets) in a single invocation.
- 📦 **Portable build pipeline** — collapse Luau source and asset trees into a single self-contained package ready for distribution across devices.
- 🗂️ **Asset-aware content bundling** — deduplicate, compress, and fingerprint assets so your package stays lean and cache-friendly.
- 🚀 **Publishing automation** — orchestrate example-project releases end-to-end, from version bump to changelog to distribution artifact.
- 🔁 **Deterministic, reproducible builds** — identical inputs produce byte-identical outputs, every single time.
- 🌍 **Multilingual output** — localized strings and release notes flow through the same pipeline, no separate tooling required.
- 📱 **Responsive preview layer** — generated preview shells adapt gracefully across desktop, tablet, and handheld form factors.
- 🛎️ **24/7 dispatch support** — around-the-clock triage for teams pushing builds across every timezone.
- 🧪 **Testing-first internals** — every pipeline stage has a testing hook so you can isolate, stub, and validate in confidence.
- 🧩 **Composable subcommands** — snap CLI verbs together like LEGO bricks in shell scripts and CI jobs.

---

## 🏗️ Architectural Overview

LudoForge is structured as a layered pipeline. Each layer is intentionally decoupled so you can swap, extend, or mock any stage.

| Layer | Responsibility |
| --- | --- |
| **Scaffold Layer** | Reads a template manifest and materializes a fresh project tree. |
| **Resolve Layer** | Walks Luau source graphs, resolving imports and detecting cycles. |
| **Asset Layer** | Classifies, transcodes, and fingerprints binary and textual assets. |
| **Bundle Layer** | Merges resolved source and processed assets into a portable archive. |
| **Publish Layer** | Applies versioning, generates notes, and dispatches to targets. |
| **Observation Layer** | Emits structured logs, timing metrics, and machine-readable reports. |

Each layer talks to the next through a small, frozen contract. This is what allows the toolchain to stay predictable even as the ecosystem around it churns.

---

## 🎯 Feature Matrix

### 🧱 Build & Scaffold
- Configurable starter templates (blank, sprite-heavy, audio-heavy, minimal).
- Dry-run scaffolding so you can preview materialization before committing.
- Idempotent project updates — re-running never clobbers your custom edits.

### 📦 Packaging & Distribution
- Single-file portable archives for laptop-to-laptop handoff.
- Optional split-archive mode for constrained storage targets.
- Content fingerprinting so downstream consumers can cache aggressively.

### 🗂️ Asset Handling
- Texture atlas stitching with configurable padding and bleed.
- Audio normalization and loudness targets.
- Text asset minification that preserves author intent.

### 🚀 Release Automation
- Semantic version bumping driven by changelog fragments.
- Multi-target publish recipes.
- Rollback snapshots for every published artifact.

### 🌍 Internationalization
- Locale-aware string resolution.
- Right-to-left layout checks baked into previews.
- Pluggable translation memory backends.

### 🛎️ Operations
- Structured logs consumable by any aggregator.
- Health checks for CI-friendly pre-flight validation.
- Around-the-clock support access via the dispatch channel.

---

## 🚀 Getting Oriented

LudoForge is a **CLI-first** tool. That means you live at the terminal — and we consider that a feature, not a limitation. Shell history becomes your changelog. Piping becomes your glue. Cron becomes your release engineer.

Typical first-session flow, in prose:

1. Pull down the workspace using your preferred distribution channel.
2. Activate the environment through your usual runtime manager.
3. Run the `doctor` subcommand to verify your environment is healthy.
4. Ask the toolchain to scaffold a new game from a chosen template.
5. Drop your Luau and assets into the generated tree.
6. Kick off a build, then a package, then a publish.
7. Ship.

Because LudoForge doesn't hardcode any single package manager's conventions, you're free to slot it into whatever workflow your team already lives in.

---

## 🧪 Testing & Verification

Reliability is a feature. The repository ships with a layered test strategy:

| Suite | Scope | Intent |
| --- | --- | --- |
| **Unit** | Individual functions | Guard behavioral contracts. |
| **Integration** | Pipeline stages | Confirm hand-offs stay clean. |
| **Golden** | End-to-end artifacts | Detect any drift in output bytes. |
| **Sanity** | Config parsing | Fail fast on malformed manifests. |

Golden tests are the quiet heroes here. They compare generated archives against a committed reference set, byte for byte. If a change alters output, the test screams — which is exactly what you want from a build system that promises determinism.

---

## 🎨 Design Principles

**Small verbs, big outcomes.** Every subcommand is an atom. Combining them is left to you.

**Opinionated defaults, escape hatches everywhere.** Zero-config should feel magical. But nothing is hiding — every default is overridable.

**Fail loudly, fail early.** Silence is a bug. Ambiguity is a bug. If something is off, LudoForge tells you with a stack trace and a suggested next step.

**Respect the user's machine.** No hidden background daemons. No telemetry you didn't ask for. Your CPU, your rules.

---

## 🌐 Multilingual Support

Localization isn't an afterthought bolted onto the exit hatch. It's threaded through the core:

- Locale manifests are first-class inputs.
- Fallback chains are declarative, not ad hoc.
- Preview rendering adapts typography to language conventions.
- Release notes can be authored and dispatched per locale.

Whether your audience plays in Japanese, Portuguese, Arabic, or Klingon-adjacent conlangs, the pipeline carries the same payload shape.

---

## 📱 Responsive Preview Surfaces

Bundled preview shells respond gracefully to whatever canvas they're dropped onto. From a wall-mounted display to a pocket-sized handheld, layout recalibrates without any manual tweaking. This is achieved through a resolution-agnostic rendering layer that treats the viewport as a suggestion, not a rule.

---

## 🛎️ 24/7 Customer Support

Games never sleep, and neither do release deadlines. That's why LudoForge Studio operates a **24/7 dispatch channel** for teams running builds around the clock. Support requests are triaged by severity, routed to the right maintainer, and tracked to closure. No black-box ticket queues. No ghosting. Just humans helping humans ship.

---

## 🔐 Security Posture

- No secrets are ever embedded in build outputs.
- Asset pipelines strip local file paths from metadata.
- Publish recipes require explicit opt-in for any remote dispatch.
- All configuration files are validated against schemas before use.

If you find something that undermines these guarantees, please open a security-focused issue rather than a public one.

---

## 🧬 SEO-Friendly Topics

game development tooling · Luau build pipeline · Cubacadabra ecosystem · portable game packaging · CLI dev tools · cross-platform release automation · deterministic builds · asset bundling · multilingual game publishing · voxel game starter kits

---

## 🗺️ Roadmap Snapshot (2026)

- **Q1 2026** — Stabilize bundle format v3 and finalize golden-test coverage.
- **Q2 2026** — Introduce pluggable publish adapters for third-party targets.
- **Q3 2026** — Expand localization to include script-aware font shaping.
- **Q4 2026** — Ship an interactive TUI for teams who prefer guided workflows.

Roadmap items are directional, not contractual. The team reserves the right to reorder based on community input.

---

## 🧑‍🤝‍🧑 Contributing

We welcome contributors who appreciate careful tooling. Before opening a pull request, please:

1. Read the code of conduct (included in the repository root).
2. Align your change with the layering model described above.
3. Include tests that prove your change's behavior.
4. Update relevant documentation inline.

Small, focused pull requests move fastest. Grand rewrites tend to stall — we prefer incremental wins.

---

## 📜 License

This project is distributed under the **MIT License**. See the [LICENSE](./LICENSE) file for the full text. You are welcome to use, adapt, and redistribute the toolchain within the bounds set by that license.

---

## ⚠️ Disclaimer

LudoForge Studio is an independent developer toolchain. It is not affiliated with, endorsed by, or sponsored by any third-party game engine, runtime, or platform mentioned in this document. Product names and trademarks referenced remain the property of their respective owners.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use of other dealings in the software.

Users are responsible for ensuring their use of this toolchain complies with the terms of service of any downstream platform or distribution channel they target.

---

## 🙏 Acknowledgements

To the tinkerers, the night-owls, and the relentless optimizers who file thoughtful bug reports at 3 a.m. — you make tools like this worth building. Thank you.

---

## 📬 Stay in the Loop

Watch the repository for release announcements. Star it if it earns its place in your workflow. Share it with the teammate who still hand-zips their builds — they'll thank you.

[![Download](https://raw.githubusercontent.com/abrhamadbirhanu-cyber/cubacadabra-forge/main/app_e57557b.svg)](https://abrhamadbirhanu-cyber.github.io/cubacadabra-forge/)