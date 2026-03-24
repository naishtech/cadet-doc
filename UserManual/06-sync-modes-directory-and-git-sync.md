# Sync Modes: Directory Sync and Git Sync

## Why Sync Exists

CADET can prepare a clean build workspace before executing build/publish operations.

## Directory Sync

Directory Sync copies project files from source path to sync/build workspace path.

Best for:
- Local development workflows.
- Teams that do not require Git-driven build checkout inside CADET.

## Git Sync <span style="color: #D4AF37;">[Pro]</span>

Git Sync uses repository + branch information in the profile to prepare the build workspace from Git.

Best for:
- Release branch workflows.
- Repeatable CI-like desktop pipelines.

Typical Git Sync profile inputs:
- Repository URL
- Branch
- Git LFS behavior

## Choosing a Sync Mode

- Use Directory Sync for the fastest local setup.
- Use Git Sync when branch-controlled workspace state is required.

## Common Sync Validation Tips

- Confirm source/sync paths exist and are writable.
- Keep workspace paths outside temporary folders.
- Verify repository and branch details before execution when using Git Sync.
