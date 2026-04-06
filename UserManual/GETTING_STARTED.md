# CADET Getting Started

This guide walks through a simple first workflow:
1. Configure a Unity Windows build.
2. Run the build.
3. Deploy the build to Steam.

Estimated time:

- Lite path, build only: 10 to 20 minutes.
- Pro path, build and Steam publish: 20 to 40 minutes, depending on tool setup and upload size.

Feature markers used in this guide:
- <span style="color: #D4AF37;">[Pro]</span> Available only in CADET Pro.
- Unmarked sections apply to both CADET Lite and CADET Pro.

## Quick Product Difference

- CADET Lite is free and can build Unity projects.
- CADET Lite cannot publish to Steam or Epic.
- CADET Pro includes publishing to Steam/Epic and additional deployment tooling.

## Before You Start

> **Back up your project before installing or upgrading.** CADET modifies your Unity project by importing assets into `Assets/Covyne/Cadet`. Make sure you have a current backup or source control commit before proceeding.
>
> **Upgrading from CADET Lite to CADET Pro?** You **must** remove CADET Lite before installing Pro. Delete the `Assets/Covyne/Cadet` folder from your Unity project before importing the CADET Pro package. Importing Pro over an existing Lite installation will cause conflicts.

1. Unity 2022.3 LTS or later is installed.
2. Your project opens successfully in Unity.
3. You have a dedicated build workspace copy of your Unity project.
4. For Steam publishing, you have a Steamworks app and credentials.

Recommended checks:

- Confirm your Unity project compiles without editor errors.
- Confirm output folder location has enough free disk space.
- Confirm CADET profile paths point to existing directories.

## Step 1: Open CADET in Unity

1. Open Unity.
2. Go to `Tools > Covyne > C.A.D.E.T`.

Expected result:

- CADET window opens and shows profile controls.

## Step 2: Configure Publishing Tools <span style="color: #D4AF37;">[Pro]</span>

If you are using CADET Pro and want to publish to Steam:

1. In CADET, open `Publishing Tools`.
2. Install required binaries/tools:
- Cosmos Binaries
- SteamCMD
3. Configure Steam credentials from the credential wizard.
4. Verify all Steam-related checks are green/ready.

Note:
- In CADET Lite, Publishing Tools and Steam publishing are not available.

Expected result:

- Steam publish operation becomes available once dependencies and credentials are valid.

## Step 3: Create a Build Profile

1. In CADET, create a new profile.
2. Set Unity build fields:
- Unity Editor Path
- Source Project Path
- Sync Project Path (dedicated build workspace)
- Build Output Path
- Build Executable Name
3. Set OS/target to Windows.

Optional sync mode:
- Directory Sync mode
- Git Sync mode <span style="color: #D4AF37;">[Pro]</span>

## Step 4: Add Steam Settings to the Profile <span style="color: #D4AF37;">[Pro]</span>

In the same profile, configure Steam fields:

1. Steam App ID.
2. Depot/content settings.
3. Build description/branch settings as needed.

If Steam is not fully configured, CADET will block publish actions until required fields are set.

## Step 5: Run a Simple Windows Build

1. Select your profile.
2. Check `Unity Build`.
3. Click `Execute`.
4. Monitor progress in CADET console and Unity log monitor.

Expected result:
- Windows build files are generated in your configured build output path.

Verification tip:

- Open the output folder immediately and confirm executable plus data files are present.

## Step 6: Deploy the Build to Steam <span style="color: #D4AF37;">[Pro]</span>

1. Keep the same profile selected.
2. Check:
- `Unity Build` (if you want a fresh build), and/or
- `Publish to Steam`
3. Click `Execute`.
4. CADET runs selected operations in sequence (build first, then publish).
5. Review output for Steam upload success.

Expected result:
- Build is uploaded to Steam according to your configured branch/depot settings.

Verification tip:

- Confirm upload record in CADET logs, then verify artifact visibility in Steamworks.

## Using Build Queue

You can queue multiple jobs (for example, several profiles or repeated workflows).

1. Add jobs to the queue.
2. Start processing.
3. Monitor queued, active, and completed states.

Notes:
- Queue processing is available in both Lite and Pro.
- Publishing steps inside queued jobs are Pro-only.

## Common First-Run Issues

1. Steam publish option disabled:
- Cause: Pro-only feature or missing Steam tool/credentials.
- Fix: Use CADET Pro and complete Publishing Tools setup.

2. Build runs but output is missing:
- Cause: Incorrect output path or profile misconfiguration.
- Fix: Recheck profile paths and run Unity Build again.

3. Sync errors before build:
- Cause: Invalid source/sync workspace paths.
- Fix: Verify dedicated build workspace paths and permissions.

## Minimal Example Summary

For the fastest successful first run:

1. Create one Windows profile.
2. Fill Unity paths.
3. Run `Unity Build`.
4. (Pro only) Configure Steam tools + credentials.
5. (Pro only) Run `Publish to Steam`.

## What To Do Next

After your first successful run:

1. Create separate profiles for release and QA.
2. Add queue jobs for repeatable release bundles.
3. Read the full manual sections for your pipeline:
- [Build Queue](05-build-queue.md)
- [Sync Modes](06-sync-modes-directory-and-git-sync.md)
- [Troubleshooting](13-troubleshooting.md)

