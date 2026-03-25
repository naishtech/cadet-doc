# Profiles and Build Configuration

## What a Profile Contains

A profile is a named configuration that tells CADET how to execute a complete build or publishing workflow. Instead of manually entering paths and settings every time, you save a profile once and reuse it across multiple builds. Profiles are the foundation of repeatable, reliable releases.

### Core Unity Build Fields

- **Profile name** : A label for this profile (e.g., "Windows Release Build", "macOS Dev"). Use descriptive names so you can quickly identify the right profile.
- **Unity Editor path** : The full path to the Unity Editor executable (e.g., `C:\Program Files\Unity\Hub\Editor\2022.3.0f1\Editor\Unity.exe`).
- **Source project path** : The path to your active development project (the one you work in daily).
- **Sync project path** : A dedicated build workspace copy of your project. CADET syncs from source to here before each build, so your active project stays clean and unaffected.
- **Build output path** : Where CADET places the finished build artifacts (executables, data folders, etc.).
- **Build executable name** : The name of the generated executable (e.g., `MyGame`). NOTE: Do not include `.exe` or `.app` file extensions.
- **Target OS/platform settings** : The operating system you are building for (Windows, macOS).

## Creating a Profile

1. **Open CADET from the Unity menu** : Go to `Tools > Covyne > C.A.D.E.T` to open the CADET UI.
2. **Create a new profile** : Click "New Profile" or similar. You will be prompted for a profile name.
3. **Enter all Unity path fields** : Fill in the Editor path, source project path, sync project path, and build output path. Use explicit absolute paths. On save, CADET validates existing paths for fields like Unity Editor Path and Unity Project Path, while Build Output Path is validated as absolute format and does not need to exist yet.
4. **Set the build executable name** : Enter the exact name the Unity build should produce (e.g., `MyGame.exe`).
5. **Select the target OS** : Choose Windows or macOS depending on what platform you are building for. This affects build settings and validation logic.
6. **Select a sync mode** (optional) : Choose between Directory Sync (copies files every build) or Git Sync (checks out a branch and pulls latest). See [Sync Modes](06-sync-modes-directory-and-git-sync.md) for details.
7. **Save and validate** : CADET checks that all required paths exist and reports errors if any are missing or invalid.

## Profile Actions

Once you have created a profile, CADET supports the following operations:

- **Create** : Make a new profile from scratch.
- **Edit** : Modify any field in an existing profile (paths, OS, sync mode, publishing settings). Changes take effect the next time you run a build with that profile.
- **Duplicate** : Copy an existing profile as a template (useful when you have multiple targets, e.g., Windows Release and Windows Debug). The duplicate is independent; changing one does not affect the other.
- **Delete** : Remove a profile permanently. Builds that used this profile will not be affected, but you cannot queue new builds with a deleted profile.
- **Export to JSON** : Save a profile as a `.json` file for sharing with team members, backing up, or version control. You can then import this file into another CADET installation.

## Publishing Fields <span style="color: #D4AF37;">[Pro]</span>

When you use CADET Pro, profiles can include publishing configuration. These fields tell CADET where and how to upload your builds:

### Steam Settings

- **Steam App ID** : The unique identifier for your game on Steamworks (a numeric ID like `1234567`). Required to publish to Steam.
- **Depot IDs** : One or more depot IDs linked to your app. Each depot typically holds build binaries for a specific OS or platform.
- **Content root** : The local directory containing the files to upload to Steam.
- **Build description** : An optional note describing this build (e.g., "v1.0.1 hotfix").
- **Branch/Live branch** : Which branch to publish to (e.g., `public`, `beta`, `staging`).

### Epic Games Store Settings

- **Product ID** : Your Epic product identifier.
- **Artifact ID** : The artifact associated with this build.
- **Sandbox ID** : The sandbox environment for publishing.
- **Labels** : Optional labels to tag builds (e.g., "release", "qa").
- **Versioning options** : Git-tag-based versioning (Pro only) for automatic version detection from Git tags.

## Git Sync Fields <span style="color: #D4AF37;">[Pro]</span>

If you select Git Sync mode instead of Directory Sync, your profile includes:

- **Repository URL** : The Git repository URL. HTTPS is recommended and validated in current workflows. SSH may work if machine level SSH keys and agent access are configured, but SSH mode is not officially validated in current CADET test coverage.
- **Branch** : The branch to check out before building (e.g., `main`, `release/v1.0`). Useful for building from release branches without touching your active development branch.
- **Git LFS** : Optionally enable Git LFS to ensure large assets are downloaded correctly. CADET can validate or install Git LFS automatically.
- **Git-tag-based versioning** : For Epic publishing workflows, you can use Git tags to define build versions automatically. For example, a tag like `v1.0.5` can be detected and used as the build version sent to Epic.

See [Sync Modes: Directory and Git Sync](06-sync-modes-directory-and-git-sync.md) for a detailed comparison and setup guide.

## Validation and Error Handling

When you save a profile, CADET validates key fields:

- Paths must exist and be readable.
- At least one build platform must be selected.
- For Pro profiles with Steam settings, the App ID and Depot IDs must be provided if you plan to publish to Steam.

If validation fails, CADET displays error messages next to the invalid fields. Correct the errors and save again.

## Tips and Best Practices

- **Use descriptive names** : Profile names like "Windows Release", "macOS Development", or "Epic QA" make it easier to pick the right profile from a list.
- **Separate source and sync paths** : Always use a dedicated sync workspace. This keeps your active project clean and prevents interference from build operations.
- **Export profiles for backup** : Use the JSON export feature to back up important profiles or share them with team members.
- **Test new profiles with a small build** : Before queueing a production build, run a quick test to verify all paths and settings are correct.
- **Update paths when moving projects** : If you move your project folder or upgrade Unity, update the relevant paths in your profile and save.
