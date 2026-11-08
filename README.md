<p align="center">
  <img src="docs/assets/images/logo.svg" alt="ZapFast logo" width="88" height="88">
</p>

<h1 align="center">ZapFast Unvibe</h1>

<p align="center"><strong>WhatsApp, native, fast, and smooth.</strong><br>A lightweight native WhatsApp desktop app for Linux, macOS, and Windows.<br><em>An active, handcrafted rework based directly on <a href="https://github.com/crmne/zapfast">ZapFast</a> by Carmine Paolino.</em></p>

<p align="center">
  <a href="Cargo.toml"><img src="https://img.shields.io/badge/Built_with-Rust-00a884" alt="Built with Rust"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-00a884" alt="MIT license"></a>
  <img src="https://img.shields.io/badge/Handcrafted-No_AI_Agents-blueviolet" alt="No AI Agents">
  <img src="https://img.shields.io/badge/Status-Work_in_Progress-orange" alt="Work in Progress">
</p>

> **Work in Progress (Handcrafted Rework)**: ZapFast Unvibe is an active rework built directly on top of the original [ZapFast](https://github.com/crmne/zapfast) codebase, maintained and developed **by hand without Claude Code, AI agents, or automated bot PRs**.
>
> *Note:* This project is an ongoing work in progress. While modules are being progressively audited, cleaned up, and rewritten by hand, remnants of upstream Claude Code / AI-generated code may still exist in parts of the codebase until the full rework is complete.

---

## Why ZapFast Unvibe?

ZapFast was originally developed as a native desktop WhatsApp client in Rust with [egui](https://www.egui.rs), communicating directly with WhatsApp via [whatsapp-rust](https://github.com/oxidezap/whatsapp-rust) without running Chromium or Electron (~200 MB idle RAM vs. 1+ GB for web wrappers).

**ZapFast Unvibe** takes that original codebase as its direct foundation and actively reworks it from the ground up: delivering a significantly more polished UI with natural motion, hardening cryptography with hardware-bound Windows DPAPI, introducing background multi-account syncing, and restructuring the codebase for human maintainability.

### Enhancements & Custom Features

- **More Polished UI & Natural Transitions (WhatsApp-Accurate)**:
  - Handcrafted visual polish with an ongoing focus on **1:1 WhatsApp desktop accuracy**: replacing rigid, abrupt panel snaps with smooth cubic-bezier transitions for sidebars, chat info, and drawer panels..
  - Integrated, stable call surface rendering for audio and video calls.
- **Hardware-Bound Security (DPAPI)**:
  - Local archives are bound to the machine's hardware using Windows Data Protection API (DPAPI) key derivation (`derive_machine_bound_key`), preventing key extraction across devices.
- **Multi-Account Background Sync**:
  - Dedicated background sync worker manager with automatic periodic synchronization and connection health heartbeats across all your linked accounts.
- **Dynamic JSON i18n Engine**:
  - Added support for runtime JSON translations alongside gettext catalogs for easy localization and community customization.
- **Cleaner Architecture**:
  - Modularized complex views (chat composer, header, menus) for maintainability and direct human review.

### About Upstream & Comparison

The original **[ZapFast](https://github.com/crmne/zapfast)** was developed by Carmine Paolino as a pure Rust desktop WhatsApp client, aiming for low memory footprint and high speed without Electron or Chromium wrappers.

**ZapFast Unvibe** keeps that core efficiency while transforming it into a polished, human-crafted desktop experience:

| Area | Upstream ZapFast (`crmne/zapfast`) | ZapFast Unvibe (This Fork) |
|---|---|---|
| **Development** | AI agent triage, automated Copilot bots | **100% Handcrafted** (WIP: progressively eliminating upstream Claude Code) |
| **UI Polish & Fidelity** | Rigid panel snapping with no visual easing | **Significantly more polished UI, smooth drawer transitions & 1:1 WhatsApp accuracy** |
| **Archive Security** | Software keys | **Machine-bound encryption** via Windows DPAPI |
| **Multi-Account** | Manual/foreground switching | **Background worker sync manager** with periodic sync & heartbeats |
| **Localization** | Static GNU gettext catalogs | **Dynamic runtime JSON engine** + Gettext support |
| **Codebase** | Monolithic view files | **Modularized components** for easy human auditing |

---

## Getting Started

### Run from Source

Make sure you have the [Rust toolchain](https://rustup.rs/) installed:

```sh
# Clone the repository
git clone https://github.com/mkssette/zapfast-unvibe.git
cd zapfast-unvibe

# Run the app
cargo run --release

# Or preview UI offline with sample chats (no WhatsApp account needed)
cargo run --features demo -- --demo
```

### Linking Your Phone

1. Start ZapFast Unvibe to view the QR code.
2. On your phone: open **WhatsApp** > **Settings** > **Linked devices** > **Link a device** and scan the code.
3. Your chats sync instantly. The link persists across reboots without needing your phone to stay online.

---

## Contributing

Pull requests and issues are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Acknowledgements & Disclaimer

ZapFast Unvibe is an enhanced fork of [ZapFast](https://github.com/crmne/zapfast) by Carmine Paolino. Built using [whatsapp-rust](https://github.com/oxidezap/whatsapp-rust), [egui](https://www.egui.rs), [fastframe](https://fastframe.dev), [Inter](https://rsms.me/inter/), [Lucide](https://lucide.dev) icons, and [Noto Color Emoji](https://fonts.google.com/noto/specimen/Noto+Color+Emoji).

ZapFast is an unofficial client and is not affiliated with WhatsApp or Meta. WhatsApp is a trademark of WhatsApp LLC.

Licensed under the [MIT License](LICENSE).
