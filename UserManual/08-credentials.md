# Credentials

## Credential Types <span style="color: #D4AF37;">[Pro]</span>

CADET Pro supports credential workflows for:
- Steam publishing
- Epic Games Store publishing
- macOS notarization

Credentials are environment specific. Configure them on each machine that executes publishing or notarization tasks.

## Where Credentials Are Stored <span style="color: #D4AF37;">[Pro]</span>

CADET stores credential files in the current user home directory:

- Steam credentials file: `.env_cadet_steam_credentials`
- Epic credentials file: `.env_cadet_epic_credentials`
- macOS notarization password file: `.env_cadet_mac_creds`

These files are written by helper classes in cadet-unity and consumed by CLI scripts during publish or notarization operations.

## Where to Configure <span style="color: #D4AF37;">[Pro]</span>

Use Publishing Tools to open credential setup dialogs/wizards.

Recommended flow:

1. Install required dependencies first.
2. Open credential wizard for target platform.
3. Save credentials.
4. Run readiness checks.

Practical note:

- Credential setup and dependency setup are linked, if required binaries are missing, credential checks can fail even when values are present.

## Steam Credentials <span style="color: #D4AF37;">[Pro]</span>

Typical requirements:
- Steam account access
- Steam Guard-ready authentication

### How The Steam Wizard Works

Steam credential checking in the wizard launches SteamCMD using your provided username and password, then monitors completion before final UI transition.

Behavior implemented in cadet-unity:

1. Wizard verifies SteamCMD exists in CADET tools path.
2. Wizard truncates SteamCMD console log file before test run.
3. Wizard launches SteamCMD with `+login <username> <password> +quit`.
4. Wizard waits for process completion, then waits an additional short validation window.
5. Wizard inspects SteamCMD console log for invalid password errors.
6. If no invalid password is detected, wizard moves to optional Steam Guard step.

### Steam Guard Timing, Email Delay, And Optional Entry

Steam Guard email codes can arrive with delay. The wizard supports this by treating guard code entry as optional at save time:

- You can enter a 5 character Steam Guard code if available now.
- If email code is delayed, you can save credentials without guard code.
- A Skip option is available in the optional guard step.

This design is intentional, publish scripts can still proceed with username and password, and SteamCMD may prompt or use sentry behavior depending on prior authentication state.

### Validation Caveat

Wizard validation is a practical precheck, not a full end to end account permission test. Invalid password is explicitly detected from SteamCMD output. Other downstream failures can still occur during real publish runs.

Validation tips:

- Confirm account has rights for target App ID.
- Confirm Steam Guard challenge can complete on this machine.
- If guard email is delayed, wait and retry, or save now and update code later.
- After first successful authentication, Steam sentry behavior can reduce repeated guard prompts.

## Epic Credentials <span style="color: #D4AF37;">[Pro]</span>

Typical requirements:
- Epic Developer credentials (Client ID / Client Secret and related IDs)

Implementation note:

- Epic wizard performs presence and format level checks.
- It also verifies BuildPatchTool exists.
- Full live authentication is deferred to build and publish execution time.

Validation tips:

- Ensure Product, Artifact, and Sandbox identifiers match profile values.
- Rotate secrets according to studio policy and update CADET immediately after rotation.
- Run one real publish to a non production label after credential updates.

## macOS Notarization Credentials <span style="color: #D4AF37;">[Pro]</span>

Typical requirements:
- Apple account details for notarization
- App-specific password

Implementation note:

- Publishing Tools prompts for generated app specific password and writes it to `.env_cadet_mac_creds` as `GEN_PW`.
- This value is consumed by notarization scripts during macOS signing and upload operations.

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
- Reconfigure credentials on every machine that runs CADET publish workflows, credentials are machine local.

## Lite Note

Credential-based publishing workflows are not available in Lite.
