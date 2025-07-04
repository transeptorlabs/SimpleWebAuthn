# UPSTREAM.md

## Fork Summary

This fork was created from [`MasterKale/SimpleWebAuthn`](https://github.com/MasterKale/SimpleWebAuthn)
to support experimental WebAuthn PRF features that are not yet available upstream.

## Branching Strategy

- `main`: tracks upstream/main for easy merging and diffing
- `feature/prf-support`: our working branch for PRF and related patches

## Last Synced

- **Upstream commit**: 786d2d8cd4560c36b6361f818a8ddaa8f0301012
- **Date**: `2025-05-12`
- **Tag/Ref**:
  - `@simplewebauthn/server: v13.1.1`
  - `@simplewebauthn/browser: v13.1.0`

## Changes Made

### Added

- Script that builds all packages (server, browser, types) and makes them available for local yarn/npm installation via a `file:` path in `package.json`.

## Usage & Distribution Plan

We do **not** plan to publish this forked version to npm.

Instead, any projects that depend on PRF support will:

- Use this fork as a **Git submodule**
- Reference the local `dist/` directory of the built package via a `file:` path in `package.json`.

### Setup Submodule:

```bash
git submodule add -b feature/prf-support git@github.com:transeptorlabs/SimpleWebAuthn.git vendor/SimpleWebAuthn
```

### Keep Submodule Updated

```bash
cd vendor/SimpleWebAuthn
git pull origin feature/prf-support
cd ../..
git add vendor/SimpleWebAuthn
git commit -m "Update submodule to latest commit"
```

### Build packages in Submodule

1. Run script to build packages

```bash
cd vendor/SimpleWebAuthn
chmod +x ./scripts/build-all.sh
./scripts/build-all.sh
cd ../..
```

2. Reference in your projects package.json:

```json
{
  "dependencies": {
    "@simplewebauthn/browser": "file:vendor/SimpleWebAuthn/dist/@transeptor-labs-simplewebauthn-browser",
    "@simplewebauthn/server": "file:vendor/SimpleWebAuthn/dist/@transeptor-labs-simplewebauthn-server"
  }
}
```
