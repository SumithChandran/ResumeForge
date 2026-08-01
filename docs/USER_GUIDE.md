# ResumeForge User Guide

This guide is for everyday users who want to edit, build, preview, and share a resume with minimal setup.

## Start Here (Recommended)

Use GitHub Codespaces so the environment is ready by default.

![Create Codespace](../assets/screenshots/1create-codespace.png)

1. Open the repository on GitHub.
2. Select Code -> Codespaces.
3. Create a codespace on the main branch.
4. Wait until the dev container is fully built.

## First Build

![Build Success](../assets/screenshots/2build.png)

1. Open a terminal in the codespace.
2. Run: make
3. Confirm that resume.pdf is generated.

## Live Preview Workflow

![Live Preview](../assets/screenshots/3watch.png)

1. Keep resume.tex and resume.pdf open side by side.
2. Start watcher: make watch
3. Edit resume.tex and save.
4. Resume PDF auto-refreshes.
5. Stop watcher with Ctrl+C.

## Day-to-Day Editing Flow

1. Update section content in resume.tex.
2. Build quickly with make.
3. Review formatting in resume.pdf.
4. Repeat until ready.

## Download/Share Output

1. Use resume.pdf as the final artifact.
2. Commit resume.tex changes to keep source of truth.
3. Attach resume.pdf where required (job portals, email, etc.).

## Local Machine Fallback (No Codespaces)

If you do not use Codespaces:

1. Install dependencies:
   - sudo apt-get update
   - sudo apt-get install -y texlive-xetex texlive-fonts-extra latexmk
2. Run make.

## CI Validation

![CI Success](../assets/screenshots/4action.png)

On push/PR, GitHub Actions will:

1. Build with make.
2. Fail fast if resume.pdf is missing.
3. Upload PDF artifact on success.

## Common User Issues

1. Build fails immediately: run make distclean and retry make.
2. PDF not updating: restart watcher with make watch.
3. Codespace starts in recovery mode: rebuild container.

For deeper troubleshooting and operator procedures, see [RUNBOOK.md](RUNBOOK.md).
