# ResumeForge Operations Runbook

This runbook is for maintainers and contributors responsible for keeping the project operational.

## Scope

Covers:

1. Environment setup validation.
2. Build and preview operations.
3. Incident diagnostics and recovery.
4. CI behavior and verification.

## Standard Operating Procedure

## Daily Health Check

1. Confirm tools:
   - xelatex --version
   - latexmk -v
2. Validate source exists:
   - resume.tex
3. Validate build:
   - make

## Preview Operation

1. Start watcher: make watch
2. Confirm log line: Watching for updated files
3. Edit and save resume.tex
4. Confirm resume.pdf refreshes

## Cleanup Operation

1. Remove temporary artifacts: make clean
2. Remove temporary artifacts and PDFs: make distclean

## Incident Response

## Incident: Codespace Recovery Mode

Symptoms:

1. Codespace starts in recovery mode.
2. Home path/config permission or creation errors are shown.

Actions:

1. Open creation log from command palette.
2. Rebuild container.
3. Verify devcontainer files:
   - .devcontainer/devcontainer.json
   - .devcontainer/Dockerfile
4. Re-run health check commands.

## Incident: Build Failure

Symptoms:

1. make returns non-zero.
2. resume.pdf is not generated.

Actions:

1. Run make distclean.
2. Re-run make and collect terminal output.
3. Confirm dependency availability:
   - xelatex --version
   - latexmk -v
4. Check recent edits in resume.tex and revert only the problematic section.

## Incident: Watch Mode Not Refreshing

Symptoms:

1. make watch starts but PDF does not update.

Actions:

1. Stop watcher with Ctrl+C.
2. Run make once to ensure baseline build succeeds.
3. Restart watcher with make watch.
4. Re-open resume.pdf tab in VS Code.

## CI Runbook

Workflow: .github/workflows/build-resume.yml

Validation logic:

1. Select source file (resume.tex, updated.tex, or updated).
2. Build with make.
3. Fail if resume.pdf is missing or empty using test -s resume.pdf.
4. Upload PDF artifact.

## CI Failure Handling

1. Open failed GitHub Actions log.
2. Reproduce locally in codespace with:
   - make distclean
   - make
3. Verify resume.pdf exists and has non-zero size.
4. Push fix and re-run pipeline.

## Command Summary

See [COMMANDS.md](COMMANDS.md) for a concise command list.
