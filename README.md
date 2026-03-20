# cao-profile-registry

CAO profile packages for the interop ecosystem.

## Overview

This repository is a **leaf registry** that stores CAO (Coordination, Automation, Orchestration) profile metadata only. It is NOT the CAO runtime — this repo stores profile definitions that configure agent orchestration behavior. Wrapper tools consume this registry's `manifest.json` to discover and install profiles.

## Directory Structure

```
cao-profile-registry/
├── manifest.json              # Registry manifest with all profile entries
├── schemas/
│   └── manifest.schema.json   # JSON Schema for manifest validation
├── profiles/
│   └── <profile-name>/
│       ├── PROFILE.md         # Profile documentation
│       └── metadata.json      # Profile metadata
├── README.md
└── .gitignore
```

## Available Profiles

| Canonical ID | Name | Version | Description |
|--------------|------|---------|-------------|
| `cao-profile/org/[MASKED_EMAIL]` | default-cao | 0.1.0 | Default CAO profile for standard AI agent orchestration |

## Manifest Format

The `manifest.json` file follows the LeafManifest structure:

```json
{
  "registryType": "cao-profile",
  "namespace": "org",
  "version": "0.1.0",
  "channel": "experimental",
  "generatedAt": "2026-03-20T07:00:00Z",
  "items": [...]
}
```

## How to Add a New Profile

1. Create a directory under `profiles/<profile-name>/`
2. Add `PROFILE.md` with profile documentation
3. Add `metadata.json` with profile metadata
4. Update `manifest.json` to include the new profile entry
5. Open a PR with the changes

## Canonical ID Format

All profiles use the canonical ID format:

```
cao-profile/<namespace>/<name>@<version>
```

Example: `cao-profile/org/[MASKED_EMAIL]`

## Related Repos

- [`registry-hub`](https://github.com/skillinterop/registry-hub) — Top-level hub that aggregates leaf registries
- [`skill-registry`](https://github.com/skillinterop/skill-registry) — Skill leaf registry
- [`reprogate-registry`](https://github.com/skillinterop/reprogate-registry) — ReproGate leaf registry

## License

MIT
