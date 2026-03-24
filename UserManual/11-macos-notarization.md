# macOS Notarization

## Availability <span style="color: #D4AF37;">[Pro]</span>

macOS notarization workflow is a Pro-only feature.

## Prerequisites <span style="color: #D4AF37;">[Pro]</span>

- macOS host environment for macOS pipeline tasks.
- Xcode installed.
- Apple Developer account.
- Developer ID Application certificate.
- Entitlements file configured in profile.
- App-specific password for notarization.

## Workflow <span style="color: #D4AF37;">[Pro]</span>

1. Ensure macOS build output exists.
2. Select profile with notarization settings configured.
3. Enable Notarize macOS Build.
4. Execute and monitor logs.

## Best Practices <span style="color: #D4AF37;">[Pro]</span>

- Test notarization early in release cycle.
- Keep certificate and entitlement configuration under version control policy.
- Validate notarized artifact before public release.

## Common Issues <span style="color: #D4AF37;">[Pro]</span>

1. Signing failure:
- Certificate not found or invalid.

2. Notarization submission failure:
- Credential/app-specific password issues.

3. Entitlements mismatch:
- Entitlements file not aligned with app capabilities.
