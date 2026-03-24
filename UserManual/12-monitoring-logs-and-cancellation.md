# Monitoring, Logs, and Cancellation

## Monitoring Features

CADET provides:
- Real-time console output with message categories.
- Progress updates for running operations.
- Access to related log files.

## Log Streams

Common logs include:
- CADET operation logs
- Unity build logs

Use logs to confirm:
- Step order
- Validation failures
- Build/publish completion

## Cancellation

You can cancel active operations from the UI.

Cancellation guidance:
- Cancel only when needed to avoid partial workflow state.
- Review logs immediately after cancellation.
- Re-run the operation after fixing the root issue.

## Pro Monitoring Additions <span style="color: #D4AF37;">[Pro]</span>

Pro workflows include additional visibility into publish and notarization phases.
