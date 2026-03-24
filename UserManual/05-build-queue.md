# Build Queue

## Overview

Build Queue lets you enqueue multiple jobs and process them sequentially.

Use cases:
- Run multiple profile builds unattended.
- Schedule repeated build/publish workflows.
- Keep work moving while Unity remains responsive.

## Queue Workflow

1. Configure one or more profiles.
2. Add jobs to queue.
3. Start queue processing.
4. Monitor queued, active, and completed jobs.

## Queue Statuses

Common states include:
- Queued
- Running
- Completed
- Failed
- Cancelled

Pro workflows may also show publishing/notarization-specific progress stages.

## Persistence and Recovery

- Queue state is persisted across Unity domain reloads.
- Active operation context is recovered when possible after reload.

## Queue Actions

- Start processing
- Cancel active job
- Remove jobs
- Open logs for job diagnostics

## Edition Notes

- Queue itself is available in both editions.
- Queue items that include publish/notarize operations require Pro.
