# Installation and Prerequisites

## Unity Requirements

- Unity 2022.3 LTS or later.
- A valid Unity project that opens cleanly.

## Workspace Requirement

- Use a dedicated build workspace copy of your project.
- Keep your development workspace and build workspace separate.
- CADET Lite and CADET Pro include built-in Directory Sync and Git Sync capabilities to automatically keep source and target projects in sync.

## Platform Support

- Editor support: Windows, macOS, Linux.
- Build targets depend on your profile and platform toolchain.

## Pro Dependencies <span style="color: #D4AF37;">[Pro]</span>

Install these through the CADET Publishing Tools before publishing workflows:
- Cosmos Binaries
- SteamCMD (for Steam)
- Epic BuildPatchTool (for Epic)

## Optional Git Requirement <span style="color: #D4AF37;">[Pro]</span>

If using Git Sync mode:
- Git installed and accessible.
- Correct repository URL and branch.
- Git LFS available when your project uses LFS objects.

## macOS Notarization Requirements <span style="color: #D4AF37;">[Pro]</span>

- macOS machine for macOS build pipeline.
- Xcode installed.
- Apple Developer account.
- Developer ID Application certificate.
- Entitlements file.
- App-specific password for notarization.
