# Build Execution and Operations

## Operation Model

CADET executes selected operations in sequence from the same profile.

Common sequence:
1. Unity Build
2. Notarization (macOS)
3. Publishing (Steam/Epic)

## Available Operations by Edition

- Unity Build
- Notarize macOS Build <span style="color: #D4AF37;">[Pro]</span>
- Publish to Steam <span style="color: #D4AF37;">[Pro]</span>
- Publish to Epic <span style="color: #D4AF37;">[Pro]</span>

## Running an Execution

1. Select a profile.
2. Select desired operation checkboxes.
3. Click Execute.
4. Monitor progress in CADET console and progress bar.

## Practical Examples

### Example A: Build only

- Check Unity Build.
- Click Execute.

### Example B: Build then Steam publish <span style="color: #D4AF37;">[Pro]</span>

- Check Unity Build.
- Check Publish to Steam.
- Click Execute.

### Example C: Publish existing build <span style="color: #D4AF37;">[Pro]</span>

- Leave Unity Build unchecked.
- Check publish action(s).
- Click Execute.

## Build Safety Notes

- Verify output paths before running.
- Keep dedicated build workspace paths valid.
- Confirm profile validation errors are resolved before Execute.
