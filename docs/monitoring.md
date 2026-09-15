# Production AI Agent Monitoring

Workflow ID: `SYuFAXb4bCqMcF6d`

## Flow

`Every 15 Minutes → Health Check Request → Is Healthy? → Healthy - No Alert / Slack Alert`

The health request uses a 10-second timeout and accepts HTTP 2xx/3xx as healthy. Request failures and non-success status codes route to the alert branch.

## Cloud-safe configuration

The workflow uses `$vars.MONITOR_TARGET_URL || 'https://mohammad-shaheed.app.n8n.cloud/healthz'` and `$vars.SLACK_ALERT_CHANNEL || '#alerts'`.

This avoids the managed-Cloud `$env` access restriction encountered during testing while keeping configuration external to the workflow logic.

## Alert payload

The Slack alert includes the target URL, HTTP status (or no response), timestamp, and n8n execution ID, plus an investigation instruction.

## Verification

Healthy monitoring was verified with HTTP 200 and `status: ok`, reaching `Healthy - No Alert`. The failure route was exercised during development; real Slack delivery requires the configured Slack credential and channel access.
