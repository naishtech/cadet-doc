# Profiles and Build Configuration

## What a Profile Contains

A profile defines how CADET executes a workflow.

Common profile fields:
- Profile name
- Unity Editor path
- Source project path
- Sync project path
- Build output path
- Build executable name
- Target OS/platform settings

## Creating a Profile

1. Open CADET from the Unity menu.
2. Create a new profile.
3. Enter all Unity path fields.
4. Select the target OS.
5. Save and validate.

## Profile Actions

- Create
- Edit
- Duplicate
- Delete
- Export to JSON

## Publishing Fields <span style="color: #D4AF37;">[Pro]</span>

When Pro publishing is enabled, profiles also include:
- Steam settings (App ID, depots, related content fields)
- Epic settings (Product ID, Artifact ID, Sandbox ID, labels/versioning)

## Git Fields <span style="color: #D4AF37;">[Pro]</span>

When Git Sync mode is selected:
- Repository URL
- Branch
- Optional Git LFS installation behavior
- Optional Git-tag-based versioning for Epic workflows
