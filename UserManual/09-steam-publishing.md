# Steam Publishing

## Availability <span style="color: #D4AF37;">[Pro]</span>

Steam publishing is a Pro-only feature.

CADET integrates Steam publishing as an operation in the same execution pipeline as Unity build, so you can run build and upload in one pass.

## Prerequisites <span style="color: #D4AF37;">[Pro]</span>

1. SteamCMD installed via Publishing Tools.
2. Steam credentials configured.
3. Profile Steam fields completed (App ID, depot/content settings).
4. A successful build output available.

Preflight checks:

- Confirm profile output path points to the correct artifact set.
- Confirm branch target in Steam matches your release stage, for example beta or public.

## Basic Workflow <span style="color: #D4AF37;">[Pro]</span>

1. Select profile.
2. Enable Publish to Steam (and optionally Unity Build for fresh output).
3. Execute.
4. Confirm successful upload in CADET logs.

Recommended first publish:

1. Upload to a non public branch.
2. Validate artifact contents in Steamworks.
3. Promote branch after QA signoff.

## Recommended First Run <span style="color: #D4AF37;">[Pro]</span>

- Start with one depot and one branch.
- Validate logs and Steam-side artifact visibility.
- Expand to additional depots/branches after initial success.

## Deployment Patterns

- Single branch rollout: simplest for solo teams.
- Beta first rollout: upload to beta branch, test, then promote.
- Multi depot rollout: split shared content and platform specific binaries for faster patching.

## Common Issues <span style="color: #D4AF37;">[Pro]</span>

1. Publish option disabled:
- Missing dependencies or credentials.

2. Upload fails:
- Invalid App ID/depot configuration.

3. Build published from wrong files:
- Incorrect build output/content root in profile.

4. Upload succeeds but users do not see update:
- Cause, branch visibility or release state issue in Steamworks.
- Fix, verify branch assignment and release settings in Steamworks dashboard.
