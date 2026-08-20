<!-- markdownlint-disable -->

# Hardening Report: dorny--test-reporter/v3.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **dorny--test-reporter/v3.0.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All `uses:` references across the workflow files use mutable tag refs (@v6, @v7) instead of full 40-character SHA commit digests. This exposes the action to supply-chain attacks if the referenced tags are moved or overwritten. Affected references: `actions/checkout@v6`, `actions/setup-node@v6`, `actions/upload-artifact@v7`.

Locations:

- `.github/workflows/check-dist.yml:22`
- `.github/workflows/check-dist.yml:25`
- `.github/workflows/check-dist.yml:44`
- `.github/workflows/ci.yml:16`
- `.github/workflows/ci.yml:17`
- `.github/workflows/ci.yml:25`
- `.github/workflows/dependabot-rebuild-dist.yml:20`
- `.github/workflows/dependabot-rebuild-dist.yml:26`
- `.github/workflows/manual-run.yml:12`
- `.github/workflows/test-report.yml:14`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all mutable tag references to full commit SHAs across 5 workflow files:
- actions/checkout@v6 → @d23441a48e516b6c34aea4fa41551a30e30af803 # v6 (in check-dist.yml, ci.yml, dependabot-rebuild-dist.yml, manual-run.yml, test-report.yml)
- actions/setup-node@v6 → @249970729cb0ef3589644e2896645e5dc5ba9c38 # v6 (in check-dist.yml, ci.yml, dependabot-rebuild-dist.yml)
- actions/upload-artifact@v7 → @043fb46d1a93c77aae656e7c1c64a875d1fc6a0a # v7 (in check-dist.yml, ci.yml)
All 10 affected locations have been fixed. Tag comments preserved for readability.

