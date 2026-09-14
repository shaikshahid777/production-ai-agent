# Environment Variables

| Variable | Purpose |
|---|---|
| SUPPORT_FROM_EMAIL | Main workflow customer email sender |
| SLACK_SUPPORT_CHANNEL | Main workflow internal Slack channel |
| MONITOR_TARGET_URL | Monitoring health-check endpoint |
| SLACK_ALERT_CHANNEL | Monitoring failure-alert channel |

Secrets such as Gemini, Postgres, SMTP/Gmail, and Slack credentials belong in n8n credentials, not Git or workflow JSON.