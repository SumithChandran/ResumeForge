# ResumeForge Command Reference

## Build And Preview

1. make
   - Builds resume.pdf from resume.tex.

2. make watch
   - Starts continuous rebuild while editing.

3. make clean
   - Removes temporary LaTeX build files.

4. make distclean
   - Removes temporary files and PDF output.

## Environment Validation

1. xelatex --version
2. latexmk -v

## CI-Equivalent Local Validation

1. make distclean
2. make
3. test -s resume.pdf

## Troubleshooting Sequence

1. make distclean
2. make
3. make watch
4. Check workflow file: .github/workflows/build-resume.yml

## Release Commands

1. Update version file:
   - edit VERSION
2. Create release tag:
   - git tag -a vX.Y.Z -m "Release vX.Y.Z"
3. Push main and tag:
   - git push origin main
   - git push origin vX.Y.Z

## Useful Files

1. resume.tex
2. Makefile
3. .github/workflows/build-resume.yml
4. .devcontainer/devcontainer.json
5. .devcontainer/Dockerfile
