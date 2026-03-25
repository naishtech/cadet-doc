# macOS Notarization

## Availability <span style="color: #D4AF37;">[Pro]</span>

macOS notarization workflow is a Pro-only feature.

This workflow signs and submits your macOS application for Apple notarization, then verifies the result before release distribution.

## Prerequisites <span style="color: #D4AF37;">[Pro]</span>

- macOS host environment for macOS pipeline tasks.
- Xcode installed.
- Apple Developer account.
- Developer ID Application certificate.
- Entitlements file configured in profile.
- App-specific password for notarization.

Preparation checklist:

- Confirm certificate is installed in the active keychain.
- Confirm entitlements file path is valid in profile settings.
- Confirm app specific password is valid and current.

## Workflow <span style="color: #D4AF37;">[Pro]</span>

1. Ensure macOS build output exists.
2. Select profile with notarization settings configured.
3. Enable Notarize macOS Build.
4. Execute and monitor logs.

Recommended sequence:

1. Build macOS artifact.
2. Run notarization operation.
3. Validate notarization success in logs.
4. Smoke test notarized app before public release.

## Best Practices <span style="color: #D4AF37;">[Pro]</span>

- Test notarization early in release cycle.
- Keep certificate and entitlement configuration under version control policy.
- Validate notarized artifact before public release.

Additional guidance:

- Avoid last minute certificate changes on release day.
- Keep a dedicated macOS release machine with stable toolchain versions.

## Common Issues <span style="color: #D4AF37;">[Pro]</span>

1. Signing failure:
- Certificate not found or invalid.

2. Notarization submission failure:
- Credential/app-specific password issues.

3. Entitlements mismatch:
- Entitlements file not aligned with app capabilities.

4. Notarization passes but app fails to launch:
- Cause, packaging or runtime signing mismatch.
- Fix, review bundle contents and rerun signing plus notarization with corrected settings.
