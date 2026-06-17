# Dasher

Dasher is a zooming predictive text-entry system for accessibility and
augmentative communication (AAC). It lets you write using minimal physical
input — eye gaze, a mouse, a single switch, a joystick, or touch.

> **Looking for apps, downloads, or user docs?** Visit
> **[dasher.at](https://dasher.at)** — that's the end-user website.

## Active development (v6)

Dasher v6 is **one shared engine** consumed by **native frontends**. Each
frontend owns only input, rendering, and platform UI; all the prediction logic
lives in the engine.

| Repository                                                                                             | What it is                              | Tech            |
| :----------------------------------------------------------------------------------------------------- | :-------------------------------------- | :-------------- |
| [DasherCore](https://github.com/dasher-project/DasherCore)                                             | The engine — language models, rendering maths, settings, alphabets, flat C API | C++17           |
| [Dasher-Apple](https://github.com/dasher-project/Dasher-Apple)                                         | iOS, macOS, visionOS apps + keyboard extension        | SwiftUI         |
| [Dasher-Windows](https://github.com/dasher-project/Dasher-Windows)                                     | Windows desktop app                                 | Avalonia (.NET) |
| [Dasher-GTK](https://github.com/dasher-project/Dasher-GTK)                                             | Linux desktop app (cross-platform build)            | GTK4 / gtkmm    |
| [dasher-design-guide](https://github.com/dasher-project/dasher-design-guide)                           | Design tokens, settings structure, parity spec      | Markdown        |
| [website](https://github.com/dasher-project/website)                                                   | Source code for [dasher.at](https://dasher.at)     | Astro           |

### For developers

- **[Developer handbook](https://dasher.at/developers/)** — architecture, build guides, contributing, RFCs
- **[Feature status matrix](https://dasher.at/status/)** — what each platform supports (v6 + v5 baseline)
- **[Integrating DasherCore](https://dasher.at/docs/development/)** — C API, pre-built binaries
- **[Governance & RFCs](https://github.com/dasher-project/governance)** — decision process

### Web demo

[dasher-web](https://github.com/dasher-project/dasher-web) — DasherCore
compiled to WASM. Powers the live demo on the
[homepage](https://dasher.at). Available for anyone who wants to embed Dasher
on the web.

## Legacy & archived

| Repository                                                                                                 | Status  | Notes                                                    |
| :--------------------------------------------------------------------------------------------------------- | :------ | :------------------------------------------------------- |
| [dasher](https://github.com/dasher-project/dasher)                                                         | Stable  | Dasher 5.x (GPL-2.0). GNOME-era C++ codebase.            |
| [dasher-MIT](https://github.com/dasher-project/dasher-MIT)                                                 | Legacy  | MIT-licensed predecessor to DasherCore.                  |
| [dasher-captivewebview](https://github.com/dasher-project/dasher-captivewebview)                           | Archived | Android/iOS keyboard wrappers using dasher-web.          |

## Contributing

Contributions are welcome! See the
[contributing guide](https://github.com/dasher-project/.github/blob/main/.github/CONTRIBUTING.md)
for project-wide conventions, and each repo's own `CONTRIBUTING.md` for
platform-specific build instructions.

Dasher is maintained by Will Wade and the dasher-project team, and is
licensed under MIT (v6) or GPL-2.0 (v5), depending on the repository.
