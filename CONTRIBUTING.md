# Contributing to ResumeForge

Thanks for contributing.

## Read First

1. User workflow: [docs/USER_GUIDE.md](docs/USER_GUIDE.md)
2. Operations and incident handling: [docs/RUNBOOK.md](docs/RUNBOOK.md)
3. Command reference: [docs/COMMANDS.md](docs/COMMANDS.md)
4. Versioning standard: [docs/VERSIONING.md](docs/VERSIONING.md)

## Setup

1. Recommended: Open this repository in a GitHub Codespace instance.
   - The required LaTeX tools are preinstalled from `.devcontainer/`.
2. Build the resume PDF:
   - `make`
3. Optional live-preview check:
   - `make watch` (stop with `Ctrl+C`)
4. If you are not using Codespaces, install dependencies locally:
   - `sudo apt-get update`
   - `sudo apt-get install -y texlive-xetex texlive-fonts-extra latexmk`

## Contribution Guidelines

- Keep sections and formatting consistent with existing style.
- Keep wording concise and impact-focused.
- Avoid introducing unnecessary packages.
- Do not commit generated LaTeX artifacts.

## Pull Requests

1. Create a branch.
2. Make your changes.
3. Run validation before opening PR:
   - `make distclean`
   - `make`
   - `test -s resume.pdf`
4. Open a pull request with:
   - What changed
   - Why it changed
   - Any assumptions made

## Release Hygiene

1. User-visible changes should be captured in [CHANGELOG.md](CHANGELOG.md).
2. Maintainers should bump [VERSION](VERSION) and tag releases as described in [docs/VERSIONING.md](docs/VERSIONING.md).