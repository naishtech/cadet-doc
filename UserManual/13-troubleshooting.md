# Troubleshooting

Use this chapter as a quick diagnostic playbook. Start with the exact symptom, then follow the cause and fix path.

## 1. Execute button does nothing

Possible causes:
- No profile selected.
- No valid operation selected.
- Validation errors in profile.

What to do:
- Select profile, confirm checkboxes, resolve validation messages.

Quick verification:

- Confirm at least one operation is enabled.
- Confirm no required field warnings are active in the profile.

## 2. Build fails early

Possible causes:
- Invalid Unity Editor path.
- Invalid source/sync/output paths.
- Workspace permission problems.

What to do:
- Verify all profile paths and write permissions.

Additional checks:

- Confirm Unity version is supported.
- Confirm project opens and compiles outside CADET.

## 3. Queue job stuck or failed

Possible causes:
- Sync failure.
- Build process error.
- Interrupted execution.

What to do:
- Open job logs, fix root cause, then re-queue.

Recovery steps:

1. Cancel active stuck job.
2. Validate sync workspace path and permissions.
3. Requeue a single job to confirm recovery before full queue restart.

## 4. Steam/Epic publish options unavailable <span style="color: #D4AF37;">[Pro]</span>

Possible causes:
- Using Lite edition.
- Missing publishing dependencies.
- Missing credentials.
- Missing profile publishing fields.

What to do:
- Use Pro edition and complete Publishing Tools setup.

Additional checks:

- Confirm dependencies are marked installed and ready.
- Confirm profile contains required store fields.

## 5. macOS notarization fails <span style="color: #D4AF37;">[Pro]</span>

Possible causes:
- Signing certificate issues.
- Apple credential problems.
- Entitlements mismatch.

What to do:
- Recheck certificate, credentials, entitlements, then rerun notarization.

Additional checks:

- Confirm notarization is executed on a macOS host.
- Confirm keychain access for signing certificate.

## 6. Git Sync fails <span style="color: #D4AF37;">[Pro]</span>

Possible causes:
- Repository URL/branch mismatch.
- Missing Git or Git LFS.
- Authentication/access issues.

What to do:
- Validate Git settings and credentials, then retry.

Additional checks:

- Confirm branch exists on remote.
- Confirm Git LFS installed for repositories with LFS assets.

## 7. Build output missing or incomplete

Possible causes:

- Output path points to unexpected location.
- Build executable name mismatch.
- Previous artifacts overwritten by another profile.

What to do:

- Verify output path and executable name in profile.
- Use target specific output folders per profile.
- Rebuild and compare timestamps of generated files.

## 8. When To Escalate

Escalate with logs when:

- The same failure persists after configuration checks.
- A previously working profile fails without environment changes.
- Publish or notarization fails with opaque third party tool errors.

Include in support report:

- CADET version.
- Unity version.
- Profile type and selected operations.
- Relevant log excerpts with timestamps.
