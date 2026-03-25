# Credentials

## Credential Types <span style="color: #D4AF37;">[Pro]</span>

CADET Pro supports credential workflows for:
- Steam publishing
- Epic Games Store publishing
- macOS notarization

Credentials are environment specific. Configure them on each machine that executes publishing or notarization tasks.

## Where to Configure <span style="color: #D4AF37;">[Pro]</span>

Use Publishing Tools to open credential setup dialogs/wizards.

Recommended flow:

1. Install required dependencies first.
2. Open credential wizard for target platform.
3. Save credentials.
4. Run readiness checks.

## Steam Credentials <span style="color: #D4AF37;">[Pro]</span>

Typical requirements:
- Steam account access
- Steam Guard-ready authentication

Validation tips:

- Confirm account has rights for target App ID.
- Confirm Steam Guard challenge can complete on this machine.

## Epic Credentials <span style="color: #D4AF37;">[Pro]</span>

Typical requirements:
- Epic Developer credentials (Client ID / Client Secret and related IDs)

Validation tips:

- Ensure Product, Artifact, and Sandbox identifiers match profile values.
- Rotate secrets according to studio policy and update CADET immediately after rotation.

## macOS Notarization Credentials <span style="color: #D4AF37;">[Pro]</span>

Typical requirements:
- Apple account details for notarization
- App-specific password

Validation tips:

- Confirm Apple account has required signing permissions.
- Confirm app specific password is current and not revoked.

## Security Best Practices <span style="color: #D4AF37;">[Pro]</span>

- Use least-privilege account access where possible.
- Rotate credentials according to your studio security policy.
- Validate credentials after updates before release day.

Additional recommendations:

- Restrict publish credentials to release managers when possible.
- Avoid sharing credentials in profile exports.
- Run one test publish to non production branch after major credential changes.

## Lite Note

Credential-based publishing workflows are not available in Lite.
