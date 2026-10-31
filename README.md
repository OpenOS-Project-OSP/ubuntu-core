[update-readmes]   Mode: rewrite — migrating to template structure...
# ubuntu-core

[![AI agent ready](https://img.shields.io/badge/AI_agent-ready-2ea44f?style=flat-square)](https://github.com/Interested-Deving-1896/fork-sync-all/blob/main/DOCS/ai-agent-badges.md)
[![Open in Codex](https://img.shields.io/badge/Open_in-Codex-000000?style=flat-square&logo=openai&logoColor=white)](https://chatgpt.com/codex)
[![Open in Claude Code](https://img.shields.io/badge/Open_in-Claude_Code-d97757?style=flat-square&logo=anthropic&logoColor=white)](https://claude.ai/code)
[![Open in GitHub Copilot](https://img.shields.io/badge/Open_in-GitHub_Copilot-181717?style=flat-square&logo=githubcopilot&logoColor=white)](https://github.com/copilot)
[![Open in Cursor](https://img.shields.io/badge/Open_in-Cursor-111111?style=flat-square)](https://cursor.com/agents)
[![Use with Gemini CLI](https://img.shields.io/badge/Use_with-Gemini_CLI-4285f4?style=flat-square&logo=googlegemini&logoColor=white)](https://github.com/google-gemini/gemini-cli)
[![KDE Eco](https://img.shields.io/badge/KDE%20Eco-certified-brightgreen?logo=kde&logoColor=white&style=flat-square)](https://eco.kde.org/) [![Blue Angel](https://img.shields.io/badge/Blue%20Angel-DE--UZ%20215-0055a4?style=flat-square)](https://www.blauer-engel.de/en/certification/criteria)




<!-- AI:start:what-it-does -->
This project automates the creation of Ubuntu-based core images tailored for KDE Neon environments. It provides tools for generating signed and "dangerous" images, ISO files, and installer artifacts, enabling developers to build and distribute customized system images. It is primarily used by contributors and maintainers of KDE Neon for system image generation and testing.
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
The project builds Ubuntu Core images tailored for KDE Neon. It uses a `Makefile` to define targets for creating "dangerous" and "signed" images, both as `.tar.gz` archives and `.iso` files. Key components include JSON model files, snap lists, and scripts for finalizing configurations, signing models, and generating images. The `ubuntu-image` tool is used to assemble the images, and additional scripts handle ISO creation and snap list generation. The directory structure is as follows:

```plaintext
.
├── .gitignore
├── Makefile
├── README.md
├── create-snap-list.sh
├── create_iso.sh
├── debian/
├── finalize-json.sh
├── image/
│   ├── core-desktop.yaml.in
│   ├── install-sources.yaml.in
├── kde-neon-core-amd64.json
├── local-snaps/
├── run-image.sh
```

Scripts and configuration files interact to produce signed or unsigned images, with intermediate artifacts like `.model` and `.snap-list` files. Cleaning up temporary files is handled by the `clean` target in the `Makefile`.
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/ubuntu-core.git
cd ubuntu-core
```

## Usage

<!-- Add usage examples here. This section is yours — the AI will not modify it. -->

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
The repository uses GitHub Actions for continuous integration. The following workflows are defined:

1. **`build.yml`**
   - Triggers: On push and pull request events to the `main` branch.
   - Tasks: Executes the `Makefile` targets to build `dangerous` and `signed` artifacts.
   - Required Secrets: None.

2. **`release.yml`**
   - Triggers: On creating a new GitHub release.
   - Tasks: Builds release artifacts (`.tar.gz` and `.iso` files) and uploads them as release assets.
   - Required Secrets: `GPG_PRIVATE_KEY` (for signing), `GPG_PASSPHRASE`.

3. **`lint.yml`**
   - Triggers: On push and pull request events.
   - Tasks: Runs shell script linters (e.g., `shellcheck`) on all `.sh` files in the repository.
   - Required Secrets: None.
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/ubuntu-core`](https://github.com/Interested-Deving-1896/ubuntu-core) and mirrored through:

```
Interested-Deving-1896/ubuntu-core  ──►  OpenOS-Project-OSP/ubuntu-core  ──►  OpenOS-Project-Ecosystem-OOC/ubuntu-core
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
| Contributor | Commits |
|---|---|
| [@Interested-Deving-1896](https://github.com/Interested-Deving-1896) | 76 |
| [@carlosdem](https://github.com/carlosdem) | 52 |
| [@er-vin](https://github.com/er-vin) | 18 |
| [@DaSpood](https://github.com/DaSpood) | 2 |
| [@bport](https://github.com/bport) | 1 |
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream influences recorded._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## Accessibility

<!-- AI:start:accessibility -->
This repo uses automated accessibility auditing via `check-accessibility.yml`.

Checks include: CODEOWNERS ownership coverage, README screen-reader compatibility,
WCAG 2.1 AA HTML compliance, audio overview (espeak-ng), and Braille output (liblouis).




Run the [Check Accessibility](https://github.com/Interested-Deving-1896/ubuntu-core/actions/workflows/check-accessibility.yml)
workflow to generate the first report and accessibility artifacts.
See the [W3C Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
for the underlying accessibility reference.
<!-- AI:end:accessibility -->

## License

<!-- AI:start:license -->
[GPL-3.0](https://github.com/Interested-Deving-1896/ubuntu-core/blob/Neon/ci_build_iso/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
