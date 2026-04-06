# Installation and Prerequisites

## Upgrading from CADET Lite to CADET Pro <span style="color: #D4AF37;">[Pro]</span>

If you have CADET Lite installed in a Unity project and want to install CADET Pro, you **must** remove the existing Lite installation first.

**Before importing the CADET Pro package:**

1. **Back up your project** — commit to source control or copy the project folder before making any changes.
2. Close the Unity project.
3. In your project's `Assets` folder, delete the entire `Covyne/Cadet` folder.
4. Reopen the project and confirm there are no leftover CADET scripts or errors.
5. Import the CADET Pro `.unitypackage`.

> Importing CADET Pro over an existing CADET Lite installation will cause script conflicts and may leave orphaned assets in your project. Always delete `Assets/Covyne/Cadet` first.

---

## Unity Requirements

- **Unity 2022.3 LTS or later** : CADET is designed for modern, long-term support (LTS) versions. Earlier versions are not supported.
- **A valid Unity project that opens cleanly** : Your project should load without errors in the Unity Editor. If you have compilation errors or missing dependencies in your main project, CADET will inherit those issues when it syncs your workspace.

## Workspaces

CADET runs a two-workspace model to keep your development work safe and isolated from build processes:

- **CADET handles sync automatically** : CADET Lite and Pro both include built-in Directory Sync (copy-based) and Git Sync (branch-based) modes that keep your build workspace up-to-date before each job runs. You don’t need to manually copy files or manage versions.

- **Keep development and build workspaces separate** : Your active development project (where you edit code, scenes, and assets) and your build workspace must be in different locations. This prevents lock files, temporary artifacts, and build output from interfering with your creative work.


## Platform Support

- **Editor support: Windows, macOS** : CADET runs inside the Unity Editor on either Windows or macOS machines. You queue and monitor builds from the editor UI.
- **Build targets depend on your profile and platform toolchain** : You can define profiles to build for Windows, macOS, or both. To build for macOS, you must do so on a macOS machine with Xcode installed. Similarly, building for Windows targets works on Windows (or via cross-compile if your toolchain supports it).

## Pro Dependencies <span style="color: #D4AF37;">[Pro]</span>

CADET Pro requires installing platform-specific tools before you can publish builds. CADET provides a **Publishing Tools** window to simplify download and configuration:

- **Cosmos Binaries** : A cross-platform runtime needed for CADET to execute build scripts and publishing workflows. CADET can download this automatically via Publishing Tools.
- **SteamCMD** : Command-line tool for uploading builds to Steam. Only required if you plan to publish to Steam. CADET’s Publishing Tools window guides you through installation and credential setup.
- **Epic BuildPatchTool** : Command-line tool for uploading builds to Epic Games Store. Only required for Epic publishing. Like SteamCMD, it can be installed and configured through the Publishing Tools interface.

Note: These tools are not included in the CADET package due to licensing. You must download them through CADET’s Publishing Tools before attempting to publish builds.

## Optional Git Requirement <span style="color: #D4AF37;">[Pro]</span>

If you plan to use **Git Sync** mode (Pro only), you need:

- **Git installed and accessible** : Git must be installed on your machine and available from the command line. On Windows, download from [git-scm.com](https://git-scm.com/download/win); on macOS, it’s typically installed via Xcode or Homebrew.
- **Correct repository URL and branch** : You must know the Git repository URL and the branch name CADET should check out before building (e.g., `main`, `release/v1.0`). Use HTTPS for a validated setup. SSH can be attempted with proper key and agent configuration, but SSH mode is not officially validated in current CADET test coverage.
- **Git LFS available when your project uses LFS objects** : If your repository uses Git Large File Storage (LFS) for large assets, Git LFS must be installed. CADET can optionally verify or auto-install Git LFS before syncing.

Note: Git Sync is optional. If you prefer, use **Directory Sync** mode (available in both Lite and Pro) to copy files instead.

## macOS Notarization Requirements <span style="color: #D4AF37;">[Pro]</span>

If you are building and publishing macOS applications, Apple requires code signing and notarization. These steps prepare your macOS app for distribution:

- **macOS machine for macOS build pipeline** : You must perform macOS builds on an actual macOS computer. Cross-compilation from Windows is not supported for notarization workflows.
- **Xcode installed** : Xcode provides the code signing tools CADET needs. Download from the macOS App Store.
- **Apple Developer account** : You must have an active Apple Developer Program membership to sign and notarize apps.
- **Developer ID Application certificate** : Create a code-signing certificate in your Apple Developer account. This certificate identifies your app as coming from a trusted source.
- **Entitlements file** : An entitlements `.plist` file that specifies what system resources your app can access (e.g., camera, microphone, local network). This must be provided in your project.
- **App-specific password for notarization** : Generate an app-specific password from [appleid.apple.com](https://appleid.apple.com) for automated notarization. CADET stores this securely via the credential wizard.

See [macOS Notarization](11-macos-notarization.md) for step-by-step setup instructions.
