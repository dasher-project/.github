# Contributing to the Dasher Project

First off — thank you for wanting to contribute to Dasher! Dasher is a
predictive, continuous-gesture text-entry system used worldwide as an
assistive tool (eye-gaze, head-trackers, switches, joysticks and more).
This guide gets you started; the full developer handbook lives at
**<https://dasher.at/developers/>**.

## The big picture

Dasher v6 is one **shared engine** consumed by several **native frontends**:

| Repository | Platform | UI stack | DasherCore integration |
| --- | --- | --- | --- |
| [`DasherCore`](https://github.com/dasher-project/DasherCore) | All | C++ engine + C API | _is_ the engine |
| [`Dasher-Apple`](https://github.com/dasher-project/Dasher-Apple) | iOS / macOS / visionOS | SwiftUI | compiled core + C API header |
| [`Dasher-Android`](https://github.com/dasher-project/Dasher-Android) | Android | Kotlin / Jetpack Compose | `libdasher.so` via JNI |
| [`Dasher-Windows`](https://github.com/dasher-project/Dasher-Windows) | Windows | Avalonia (.NET) | `dasher.dll` via P/Invoke |
| [`Dasher-GTK`](https://github.com/dasher-project/Dasher-GTK) | Linux (+ Win/macOS fallback) | GTK4 / gtkmm | `libdasher.so` linked |
| [`dasher-web`](https://github.com/dasher-project/dasher-web) | Web (WASM) | Rust / WASM | DasherCore compiled to WASM |
| [`website`](https://github.com/dasher-project/website) | — | Astro | docs + public feature-status matrix (not a frontend) |

Before touching a frontend, read **[DasherCore's C API contract](https://github.com/dasher-project/DasherCore/blob/main/docs/C_API.md)**
and the **[cross-platform feature matrix](https://dasher.at/status/)** — it
shows what every platform already supports so we keep parity.

## Where to go next

- **Building a specific platform:** see the developer handbook at <https://dasher.at/developers/> and the `README.md` / `CONTRIBUTING.md` inside the relevant repo.
- **Coding standards:** [`DasherCore/CONTRIBUTING.md`](https://github.com/dasher-project/DasherCore/blob/main/CONTRIBUTING.md) is the project's gold standard (no naked `new`/`delete`, `const`-correctness, zero warnings, clean API boundaries). Each frontend repo states its own language-specific rules.
- **Design tokens:** the normative source of truth is [`dasher-design-guide/DESIGN.md`](https://github.com/dasher-project/dasher-design-guide/blob/main/DESIGN.md).
- **Proposing a cross-platform change:** read the [RFC process](https://github.com/dasher-project/governance#decision-making) in our governance repo.

## Definition of Done

A pull request is ready to merge when:

- [ ] CI is green (build + tests + lint + format, as applicable to the repo).
- [ ] New behaviour has tests.
- [ ] If the change affects a cross-platform capability, the **feature matrix** (`website/src/data/feature-status.json`) has been updated in this or a linked PR.
- [ ] If the change is a new UX/hardware interaction, an **RFC** is linked.
- [ ] Docs / changelog are updated if the change is user-facing.

## Quick expectations

- **Be kind.** Our [Code of Conduct](./CODE_OF_CONDUCT.md) applies across every Dasher repository and our Slack.
- **Open a PR, not a direct push.** Reviews are required on `main`.
- **Small, focused PRs** are easier to review and land faster.
- **Talk to us first** for big changes — open an issue or an RFC.

## Developer Certificate of Origin (DCO)

All contributions to the Dasher project must be signed off under the
[Developer Certificate of Origin](https://developercertificate.org/). This is
a lightweight alternative to a CLA — it affirms that you wrote (or have the
right to submit) the code you're contributing.

**How to sign off:** add `-s` (or `--signoff`) to your commit command:

```sh
git commit -s -m "your commit message"
```

This adds a `Signed-off-by:` trailer to the commit message automatically. If
you forgot, you can amend:

```sh
git commit --amend -s --no-edit
```

For an existing PR with multiple unsigned commits, rebase with signoff:

```sh
git rebase --signoff BASE_BRANCH
git push --force-with-lease
```

> **Why DCO instead of a CLA?** Dasher is MIT-licensed and community-driven. A
> full CLA adds legal friction for volunteers. The DCO achieves provenance
> tracking with a single line, and is the same model used by the Linux kernel,
> Git, and many other open-source projects.

_This file is the organisation-wide default. Individual repositories may add their own `CONTRIBUTING.md` with platform-specific build steps and rules, which take precedence here._
