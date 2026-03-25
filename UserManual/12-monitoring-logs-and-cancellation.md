# Monitoring, Logs, and Cancellation

## Monitoring Features

CADET provides:
- Real-time console output with message categories.
- Progress updates for running operations.
- Access to related log files.

Use monitoring continuously during active runs, especially when running multi step Pro operations that include publish or notarization.

## Log Streams

Common logs include:
- CADET operation logs
- Unity build logs

Use logs to confirm:
- Step order
- Validation failures
- Build/publish completion

Suggested review order when troubleshooting:

1. CADET operation log for high level sequence.
2. Unity build log for compilation and build pipeline errors.
3. Tool specific output for Steam, Epic, or notarization failures.

## Cancellation

You can cancel active operations from the UI.

Cancellation guidance:
- Cancel only when needed to avoid partial workflow state.
- Review logs immediately after cancellation.
- Re-run the operation after fixing the root issue.

Safe cancellation pattern:

- Cancel active step once.
- Wait for state to transition to Cancelled or Failed.
- Avoid repeated cancel spam, this can hide root signal in logs.
- Requeue only after confirming workspace and profile integrity.

## Pro Monitoring Additions <span style="color: #D4AF37;">[Pro]</span>

Pro workflows include additional visibility into publish and notarization phases.

## Practical Logging Tips

- Save logs for release candidates to keep an audit trail.
- Include profile name and timestamp in exported log filenames.
- Attach relevant log sections when reporting issues to support.
