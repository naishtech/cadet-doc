# Sync Modes: Directory Sync and Git Sync

## Why Sync Exists

CADET can prepare a clean build workspace before executing build/publish operations.

This isolation step reduces release risk by separating your active editor workspace from the workspace used to execute build jobs.

## Directory Sync

Directory Sync copies project files from source path to sync/build workspace path.

How it works:

- Reads from your source project path.
- Copies required files into sync workspace.
- Executes build from sync workspace.

Best for:
- Local development workflows.
- Teams that do not require Git-driven build checkout inside CADET.

Strengths:

- Fast setup.
- No repository credential requirements.
- Works well for solo or small team local pipelines.

## Git Sync <span style="color: #D4AF37;">[Pro]</span>

Git Sync uses repository + branch information in the profile to prepare the build workspace from Git.

How it works:

- Connects to the configured repository.
- Checks out target branch.
- Pulls latest changes.
- Optionally resolves Git LFS objects.

Best for:
- Release branch workflows.
- Repeatable CI-like desktop pipelines.

Typical Git Sync profile inputs:
- Repository URL
- Branch
- Git LFS behavior

Strengths:

- Branch controlled build inputs.
- Easier release traceability.
- Better fit for teams with strict source control policy.

## Choosing a Sync Mode

- Use Directory Sync for the fastest local setup.
- Use Git Sync when branch-controlled workspace state is required.

Decision checklist:

- Need fastest setup with minimal tooling: Directory Sync.
- Need branch fidelity for releases: Git Sync.
- Need to build from tags or controlled history: Git Sync.

## Common Sync Validation Tips

- Confirm source/sync paths exist and are writable.
- Keep workspace paths outside temporary folders.
- Verify repository and branch details before execution when using Git Sync.

## Common Failure Patterns

1. Sync path permission denied:
- Cause, restricted folder or antivirus lock.
- Fix, move sync workspace to a writable folder and retry.

2. Git branch not found:
- Cause, typo or stale branch reference.
- Fix, verify branch name in profile and remote.

3. LFS objects missing:
- Cause, Git LFS not installed or not initialized.
- Fix, install Git LFS and rerun sync.
