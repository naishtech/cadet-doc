# Epic Publishing

## Availability <span style="color: #D4AF37;">[Pro]</span>

Epic publishing is a Pro-only feature.

## Prerequisites <span style="color: #D4AF37;">[Pro]</span>

1. Epic BuildPatchTool installed via Publishing Tools.
2. Epic credentials configured.
3. Profile Epic fields completed (Product/Artifact/Sandbox IDs and labels/versioning).
4. A successful build output available.

## Basic Workflow <span style="color: #D4AF37;">[Pro]</span>

1. Select profile.
2. Enable Publish to Epic (and optionally Unity Build).
3. Execute.
4. Confirm success in CADET logs.

## Versioning Tips <span style="color: #D4AF37;">[Pro]</span>

- Keep version naming consistent with your release process.
- If using Git Sync, Git tag based versioning can simplify release traceability.

## Common Issues <span style="color: #D4AF37;">[Pro]</span>

1. Publish option unavailable:
- Missing Epic tool or credentials.

2. Validation failure:
- Missing or invalid Product/Artifact/Sandbox fields.

3. Artifact mismatch:
- Build output path does not match profile expectations.
