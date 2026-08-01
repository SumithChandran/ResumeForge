# Contributing to ResumeForge

Thanks for contributing.

## Local Setup

1. Install dependencies:
   - `sudo apt-get update`
   - `sudo apt-get install -y texlive-xetex texlive-fonts-extra latexmk`
2. Build the resume PDF:
   - `make`
3. Optional live-preview check:
   - `make watch` (stop with `Ctrl+C`)

## Contribution Guidelines

- Keep sections and formatting consistent with existing style.
- Keep wording concise and impact-focused.
- Avoid introducing unnecessary packages.
- Do not commit generated LaTeX artifacts.

## Pull Requests

1. Create a branch.
2. Make your changes.
3. Run `make` and ensure the PDF builds without errors.
4. Open a pull request with:
   - What changed
   - Why it changed
   - Any assumptions made