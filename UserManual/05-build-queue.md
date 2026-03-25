# Build Queue

## Overview

Build Queue lets you enqueue multiple jobs and process them sequentially.

Each queued item stores the selected profile and operation set. This lets you stage a release run in advance and execute it without reconfiguring each job manually.

Use cases:
- Run multiple profile builds unattended.
- Schedule repeated build/publish workflows.
- Keep work moving while Unity remains responsive.

## Queue Workflow

1. Configure one or more profiles.
2. Add jobs to queue.
3. Start queue processing.
4. Monitor queued, active, and completed jobs.

Recommended workflow for repeat releases:

1. Duplicate a known good profile for each target.
2. Queue all required jobs in release order.
3. Start processing and review job output as each item completes.

## Queue Statuses

Common states include:
- Queued
- Running
- Completed
- Failed
- Cancelled

Pro workflows may also show publishing/notarization-specific progress stages.

Status meaning:

- Queued: waiting for execution.
- Running: currently active.
- Completed: finished successfully.
- Failed: stopped due to validation or runtime error.
- Cancelled: manually terminated by user action.

## Persistence and Recovery

- Queue state is persisted across Unity domain reloads.
- Active operation context is recovered when possible after reload.

Recovery guidance:

- If Unity restarts during a queued run, reopen CADET and verify active job state before requeueing.
- If a job cannot recover automatically, mark it failed or cancelled, fix inputs, then queue again.

## Queue Actions

- Start processing
- Cancel active job
- Remove jobs
- Open logs for job diagnostics

Operational note:

- Cancel only the active job when necessary, avoid clearing completed history until logs are archived.

## Edition Notes

- Queue itself is available in both editions.
- Queue items that include publish/notarize operations require Pro.

## Best Practices

- Keep queue jobs small and target specific, this makes failures easier to isolate.
- Use consistent naming in profiles so queue entries are easy to identify.
- Validate dependencies before long overnight queue runs.
