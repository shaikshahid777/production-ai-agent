# Monitoring Failure Test

1. Configure MONITOR_TARGET_URL to a live health endpoint and verify a healthy run produces no alert.
2. Temporarily point MONITOR_TARGET_URL to an invalid path or otherwise produce a non-2xx/3xx response.
3. Manually execute the monitoring workflow.
4. Verify Is Healthy? evaluates false and Slack Alert executes.
5. Confirm the real Slack channel receives the alert.
6. Restore the live endpoint and repeat the healthy test.

Capture screenshots of the healthy run, failure routing, and real Slack alert.