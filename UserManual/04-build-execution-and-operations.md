# Build Execution and Operations

## Operation Model

CADET executes selected operations in sequence from the same profile.

Execution is deterministic: selected steps run in a fixed order, and each step must pass before the next begins. This helps keep release behavior predictable and easier to audit.

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

Pre run check:

- Confirm profile validation is green.
- Confirm output directory has enough free disk space.
- Confirm required Pro dependencies and credentials are ready if publishing is selected.

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

Use this when you already created a verified artifact and only want to publish it.

## Failure Handling

- If a step fails, CADET stops the sequence and marks the job as failed.
- Review the active operation log first, then Unity log or tool specific output.
- Fix the root issue in profile settings or environment, then rerun the same operation set.

## Performance Tips

- Use separate output folders per target to avoid accidental artifact overwrite.
- Keep build workspace on a fast local SSD when possible.
- Queue independent jobs instead of editing profile fields repeatedly during a release cycle.

## Build Safety Notes

- Verify output paths before running.
- Keep dedicated build workspace paths valid.
- Confirm profile validation errors are resolved before Execute.
