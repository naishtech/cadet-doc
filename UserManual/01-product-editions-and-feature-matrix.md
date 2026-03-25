# Product Editions and Feature Matrix

## Editions

- CADET Lite: Free edition focused on reliable Unity build automation, profile reuse, and queue based local execution.
- CADET Pro: Paid edition that includes everything in Lite, plus publishing workflows for Steam and Epic, macOS notarization, Git Sync, and credential tooling.

## Which Edition Fits Your Workflow

- Choose Lite if your current need is predictable local build output with minimal setup.
- Choose Pro if you need release automation beyond build generation, especially store publishing and notarization.
- Start in Lite and upgrade later if your release process grows, profiles and core build workflows transfer naturally.

## Feature Matrix

| Feature | Lite | Pro |
|---|---|---|
| Unity Build execution | Yes | Yes |
| Build Queue | Yes | Yes |
| Directory Sync mode | Yes | Yes |
| Git Sync mode | No | Yes |
| Publish to Steam | No | Yes |
| Publish to Epic Games Store | No | Yes |
| macOS notarization workflow | No | Yes |
| Publishing Tools window | No | Yes |
| Steam/Epic/macOS credential wizards | No | Yes |

## What This Means In Practice

- Lite supports a complete build only pipeline: profile configuration, workspace sync, queue execution, and artifact generation.
- Pro adds release pipeline steps after a build completes: publish to Steam, publish to Epic, and notarize macOS outputs.
- If a Pro only feature is selected in Lite, CADET blocks that action and shows validation guidance.

## Practical Meaning

- <span style="color: #D4AF37;">[Pro]</span> steps require CADET Pro.
- Unmarked steps can be performed in any edition.
- If a <span style="color: #D4AF37;">[Pro]</span> feature is unavailable, CADET will disable that action in the UI.

## Typical Paths

- Lite path: profile setup, directory sync or queue setup, Unity build.
- Pro path: profile setup, sync mode selection, Unity build, optional publish and notarization.

## Upgrade Checklist: Lite To Pro

1. Keep your existing build profiles and verify paths are correct.
2. Install dependencies in Publishing Tools: Cosmos, SteamCMD, Epic BuildPatchTool.
3. Configure credentials for Steam, Epic, or Apple notarization.
4. Add publishing fields to profiles and run one staging release before production.
