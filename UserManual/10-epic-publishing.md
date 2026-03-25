# Epic Publishing

## Availability <span style="color: #D4AF37;">[Pro]</span>

Epic publishing is a Pro-only feature.

CADET runs Epic publishing as part of the same execution flow used for builds, so profile consistency is critical for reliable uploads.

## Prerequisites <span style="color: #D4AF37;">[Pro]</span>

1. Epic BuildPatchTool installed via Publishing Tools.
2. Epic credentials configured.
3. Profile Epic fields completed (Product/Artifact/Sandbox IDs and labels/versioning).
4. A successful build output available.

Preflight checks:

- Confirm Product, Artifact, and Sandbox values match your Epic backend.
- Confirm output folder contains the intended release files.

## Basic Workflow <span style="color: #D4AF37;">[Pro]</span>

1. Select profile.
2. Enable Publish to Epic (and optionally Unity Build).
3. Execute.
4. Confirm success in CADET logs.

Operational tip:

- For release branches, keep version label format consistent across profiles.

## Versioning Tips <span style="color: #D4AF37;">[Pro]</span>

- Keep version naming consistent with your release process.
- If using Git Sync, Git tag based versioning can simplify release traceability.

Suggested version policy:

- Use semantic versions, for example 1.2.0.
- Tag release commits in Git, then reuse tags in profile version inputs.
- Record published version in release notes immediately after successful upload.

## Common Issues <span style="color: #D4AF37;">[Pro]</span>

1. Publish option unavailable:
- Missing Epic tool or credentials.

2. Validation failure:
- Missing or invalid Product/Artifact/Sandbox fields.

3. Artifact mismatch:
- Build output path does not match profile expectations.

4. Version rejected:
- Cause, invalid label format or duplicate version.
- Fix, update version label to a new valid value and rerun publish.
