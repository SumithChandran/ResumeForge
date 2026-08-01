# ResumeForge

Build an ATS-friendly resume with LaTeX templates, live preview, and practical writing guidance.

ResumeForge is a reusable LaTeX resume setup that anyone can fork and customize.

## What You Get

- A working LaTeX resume source file
- A clean starter template with placeholders
- Build instructions for local development
- GitHub Actions workflow to auto-build PDF on push/PR

## Repository Structure

- `resume.tex`: Primary resume source (current version)
- `resume-template.tex`: Generic starter template for new users
- `Makefile`: One-command build and clean targets
- `.github/workflows/build-resume.yml`: CI build workflow

## Prerequisites (Ubuntu/Debian)

Install a LaTeX engine and required packages:

1. `sudo apt-get update`
2. `sudo apt-get install -y texlive-xetex texlive-fonts-extra latexmk`

## Quick Start

1. Clone or fork this repository.
2. Create your resume file:
	- Option A: Edit `resume.tex` directly.
	- Option B: Copy `resume-template.tex` to `resume.tex` and then edit.
3. Build PDF:
	- `make`
4. Output file:
	- `resume.pdf`

## Useful Commands

- Build: `make`
- Live rebuild (watch mode): `make watch`
- Clean temporary files: `make clean`
- Remove temporary files and PDFs: `make distclean`

## Live Preview While Editing (VS Code)

This repo includes VS Code workspace settings for live PDF updates.

Recommended in Codespaces/web VS Code:

1. Open `resume.tex` and `resume.pdf` side by side.
2. Start watcher from terminal: `make watch`.
3. Edit `resume.tex` and save.
4. `resume.pdf` is rebuilt automatically.
5. Stop watcher with `Ctrl+C` when done (exit code 130 is expected).

Start watcher from VS Code task (no terminal typing):

1. Open command palette.
2. Run `Tasks: Run Task`.
3. Select `Resume: Live Preview Watch`.

Optional (if you install LaTeX Workshop):

1. Install `James-Yu.latex-workshop`.
2. Use `LaTeX Workshop: Build LaTeX project` for compilation automation.

Alternative terminal workflow:

1. Run `make watch` in a terminal.
2. Keep `resume.pdf` open in VS Code preview.

## Live Preview Troubleshooting

1. If PDF does not refresh, verify watcher output includes `Watching for updated files`.
2. Re-open the `resume.pdf` tab.
3. Rebuild once manually: `make distclean && make`.
4. Start watch mode again: `make watch`.

## Use This As a GitHub Template

1. Push this repository to GitHub.
2. In GitHub: Settings -> General -> Template repository -> Enable.
3. Others can click Use this template to create their own resume repo.

## Notes for Contributors

- Keep formatting changes minimal and intentional.
- Do not commit LaTeX build artifacts (`.aux`, `.log`, `.out`, etc.).
- Prefer concise bullet points with measurable impact.

## License

This project is licensed under the MIT License. See `LICENSE`.