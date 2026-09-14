# Production AI Agent Monitoring

Workflow ID: SYuFAXb4bCqMcF6d

Flow: Schedule Trigger every 15 minutes → HTTP Request → IF → Healthy/No Alert or Slack Alert.

Healthy means HTTP status 200–399. Any non-success response or request failure routes to Slack Alert.

The workflow uses $env.MONITOR_TARGET_URL and $env.SLACK_ALERT_CHANNEL. Slack credentials remain in n8n credentials.

Sandbox validation verified unhealthy routing, but Slack delivery was simulated. A live health endpoint and Slack credential are required for live validation.