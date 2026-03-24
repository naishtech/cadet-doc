# Publishing Tools

## Overview <span style="color: #D4AF37;">[Pro]</span>

Publishing Tools is the Pro control center for deployment dependencies and credential setup.

Primary capabilities:
- Install and validate required third-party binaries/tools.
- Launch credential setup flows.
- Check deployment readiness before publish operations.

## Dependency Setup <span style="color: #D4AF37;">[Pro]</span>

Common dependencies managed here:
- Cosmos Binaries
- SteamCMD
- Epic BuildPatchTool

Recommended sequence:
1. Install Cosmos Binaries first.
2. Install platform-specific tools (SteamCMD/Epic BuildPatchTool).
3. Validate readiness indicators.

## Readiness Checklist <span style="color: #D4AF37;">[Pro]</span>

Before first publish run:
- Required dependencies installed.
- Required credentials configured.
- Profile publishing fields complete and valid.

## Lite Behavior

In Lite, publishing tool actions are unavailable because publishing workflows are Pro-only.
