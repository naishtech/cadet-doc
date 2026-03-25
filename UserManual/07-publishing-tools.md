# Publishing Tools

## Overview <span style="color: #D4AF37;">[Pro]</span>

Publishing Tools is the Pro control center for deployment dependencies and credential setup.

Use this window before first release setup, and revisit it whenever credentials rotate or tooling changes.

Primary capabilities:
- Install and validate required third-party binaries/tools.
- Launch credential setup flows.
- Check deployment readiness before publish operations.

## Typical First Time Setup

1. Open Publishing Tools.
2. Install Cosmos Binaries.
3. Install SteamCMD and or Epic BuildPatchTool based on store targets.
4. Configure credentials for each target.
5. Verify readiness indicators are green.

## Dependency Setup <span style="color: #D4AF37;">[Pro]</span>

Common dependencies managed here:
- Cosmos Binaries
- SteamCMD
- Epic BuildPatchTool

Recommended sequence:
1. Install Cosmos Binaries first.
2. Install platform-specific tools (SteamCMD/Epic BuildPatchTool).
3. Validate readiness indicators.

Maintenance guidance:

- Revalidate tools after machine upgrades.
- Reinstall dependencies if tool paths are moved.
- Keep one consistent tool installation path per machine.

## Readiness Checklist <span style="color: #D4AF37;">[Pro]</span>

Before first publish run:
- Required dependencies installed.
- Required credentials configured.
- Profile publishing fields complete and valid.

If any item is missing, CADET disables dependent publish actions and surfaces setup guidance in the UI.

## Lite Behavior

In Lite, publishing tool actions are unavailable because publishing workflows are Pro-only.

## Troubleshooting Quick Checks

1. Tool shows not installed after install:
- Cause, invalid path or blocked extraction.
- Fix, reinstall with administrator permission, then revalidate.

2. Credentials configured but publish still unavailable:
- Cause, profile fields incomplete.
- Fix, open profile and fill required store specific values.
