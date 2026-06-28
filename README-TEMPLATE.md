# Dasher Frontend README Template

Each `Dasher-<Platform>` repository's `README.md` should follow this structure.
Copy it, replace the `<...>` placeholders, and adapt the platform-specific
sections. Keep it concise — link out to [dasher.at](https://dasher.at) and
[DasherCore](https://github.com/dasher-project/DasherCore) for depth rather
than duplicating their content.

---

```markdown
# Dasher for <Platform>

[![Build](<ci-badge-url>)](<ci-link>) [![Release](<release-badge-url>)](<release-link>) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

Dasher is an information-efficient text-entry interface, driven by continuous
pointing gestures. It lets you write using eye gaze, a mouse, a switch, a
joystick, or touch — designed for accessibility and augmentative communication
(AAC).

This is the **<Platform>** frontend, built on the shared
[DasherCore](https://github.com/dasher-project/DasherCore) engine.

> **[dasher.at](https://dasher.at)** — downloads, user docs, and live demo
> **[Feature status](https://dasher.at/status/)** — what each platform supports
> **[All repos](https://github.com/dasher-project)** — engine, frontends, design guide

## Status

> **<Phase/Release status>** — <one line>. See the
> [feature matrix](https://dasher.at/status/) for what's implemented.

## Install

<Platform app store link, or "Download the latest build from
[Releases](../../releases)", or "Not yet publicly available".>

## Build

### Prerequisites

- <tool 1 + version>
- <tool 2 + version>
- Git (with submodules)

### Steps

```bash
git clone --recurse-submodules https://github.com/dasher-project/Dasher-<Platform>.git
cd Dasher-<Platform>
<build command>
```

<If the build has multiple phases (native layer + UI layer), number them
like the Dasher-Windows README does.>

<If the frontend supports multiple host OSes for development, include a
dependency table like the Dasher-GTK README.>

## Architecture

<One paragraph: how DasherCore is consumed (Pattern A: direct C++ subclassing,
Pattern B: C API via FFI/JNI/P-Invoke, or WASM) and what this repo provides.>

```
<concise ASCII diagram of the data flow — see Dasher-Windows for the best example>
```

See [DasherCore's C API](https://github.com/dasher-project/DasherCore/blob/main/docs/C_API.md)
for the engine contract.

## Repository layout

| Path | Purpose |
|---|---|
| `<dir>/` | <what it does> |
| `third_party/DasherCore/` | DasherCore submodule (do not edit here — PR upstream) |

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for build details, code style, and
DCO sign-off. For project-wide conventions (code of conduct, RFCs, security),
see the
[org contributing guide](https://github.com/dasher-project/.github/blob/main/CONTRIBUTING.md).

## License

MIT — see [LICENSE](./LICENSE).
```

---

## Guidance

- **Opening:** use the two-sentence intro verbatim (do not rewrite it per
  repo — consistency helps search and first impressions).
- **Badges:** at minimum a CI badge and a license badge. Add a release/store
  badge if the platform has one (TestFlight, Google Play, Flatpak, etc.).
- **Status blockquote:** be honest about maturity. Link to the feature matrix
  rather than summarising it inline.
- **Build:** copy-paste blocks that work when pasted into a terminal. Number
  multi-phase builds. If a manual step is unavoidable (copy a DLL, set a
  PATH), say so explicitly — don't hide it.
- **Architecture:** keep it to one paragraph + one diagram. Link to DasherCore
  for the full C API contract. Don't duplicate DasherCore's docs.
- **What NOT to include:** a long "what is Dasher?" explainer (link dasher.at),
  the v5 "PDAs" boilerplate, full RFC summaries (link governance), or the
  feature matrix table (it lives on the website).
