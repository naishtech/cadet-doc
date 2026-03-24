# Troubleshooting

## 1. Execute button does nothing

Possible causes:
- No profile selected.
- No valid operation selected.
- Validation errors in profile.

What to do:
- Select profile, confirm checkboxes, resolve validation messages.

## 2. Build fails early

Possible causes:
- Invalid Unity Editor path.
- Invalid source/sync/output paths.
- Workspace permission problems.

What to do:
- Verify all profile paths and write permissions.

## 3. Queue job stuck or failed

Possible causes:
- Sync failure.
- Build process error.
- Interrupted execution.

What to do:
- Open job logs, fix root cause, then re-queue.

## 4. Steam/Epic publish options unavailable <span style="color: #D4AF37;">[Pro]</span>

Possible causes:
- Using Lite edition.
- Missing publishing dependencies.
- Missing credentials.
- Missing profile publishing fields.

What to do:
- Use Pro edition and complete Publishing Tools setup.

## 5. macOS notarization fails <span style="color: #D4AF37;">[Pro]</span>

Possible causes:
- Signing certificate issues.
- Apple credential problems.
- Entitlements mismatch.

What to do:
- Recheck certificate, credentials, entitlements, then rerun notarization.

## 6. Git Sync fails <span style="color: #D4AF37;">[Pro]</span>

Possible causes:
- Repository URL/branch mismatch.
- Missing Git or Git LFS.
- Authentication/access issues.

What to do:
- Validate Git settings and credentials, then retry.
