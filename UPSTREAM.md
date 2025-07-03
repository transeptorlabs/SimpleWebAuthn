# UPSTREAM.md

## Fork Summary

This fork was created from [`MasterKale/SimpleWebAuthn`](https://github.com/MasterKale/SimpleWebAuthn)
to support experimental WebAuthn PRF features that are not yet available upstream.

## Branching Strategy

- `main`: tracks upstream/main for easy merging and diffing
- `feature/prf-support`: our working branch for PRF and related patches

## Last Synced

**Upstream commit**: 786d2d8cd4560c36b6361f818a8ddaa8f0301012
**Date**: `2025-05-12`  
**Tag/Ref**:
- `@simplewebauthn/server: v13.1.1`
- `@simplewebauthn/browser: v13.1.0`

## Changes Made

- Added PRF extension support in `generateAuthenticationOptions()`
- Extended types for `AuthenticationExtensionsPRFInputs`
- Added helper to derive HD wallet keys using PRF output

## Merge Notes

---

## Usage & Distribution Plan

We do **not** plan to publish this forked version to npm.

Instead, any projects that depend on PRF support will:
- Use this fork as a **Git submodule**
- Reference the local `dist/` directory of the built package via a `file:` path in `package.json`

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

### Build or Use the Submodule

1. Run script to build packages
```bash
yarn install && yarn build
chmod +x ./scripts/build-deps.sh
./scripts/build-deps.sh
```

2. Reference in package.json:
```json
{
  "dependencies": {
    "@simplewebauthn/server": "file:dist/@simplewebauthn-server"
  }
}
```