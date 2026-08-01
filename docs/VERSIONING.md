# Versioning Policy

This repository uses Semantic Versioning: MAJOR.MINOR.PATCH.

## Source of Truth

1. VERSION file in repository root.
2. Git tag in the format vX.Y.Z.
3. CHANGELOG.md release section.

All three should match for every release.

## Version Bump Rules

1. MAJOR (X.0.0)
   - Use when introducing breaking changes.
   - Examples: incompatible template structure, major workflow behavior changes.

2. MINOR (1.X.0)
   - Use for backward-compatible additions or improvements.
   - Examples: new sections/templates, added automation, non-breaking feature additions.

3. PATCH (1.0.X)
   - Use for backward-compatible fixes.
   - Examples: build fixes, CI fixes, docs corrections, typo fixes, small styling corrections.

## Release Procedure

1. Ensure the repo is healthy:
   - make distclean
   - make
   - test -s resume.pdf
2. Update VERSION with the new number.
3. Update CHANGELOG.md:
   - Move entries from Unreleased to the new version section.
   - Add release date in YYYY-MM-DD format.
4. Commit release changes.
5. Create annotated tag:
   - git tag -a vX.Y.Z -m "Release vX.Y.Z"
6. Push commits and tag:
   - git push origin main
   - git push origin vX.Y.Z
7. Verify GitHub Actions and artifact output.

## Maintainer Notes

1. Keep Unreleased focused on user-visible changes.
2. Do not skip patch bumps for production-affecting fixes.
3. Prefer small, frequent tagged releases over large infrequent drops.
