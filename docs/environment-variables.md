# Configuration Reference

The current n8n Cloud implementation uses **n8n Variables (`$vars`)** for non-secret runtime configuration.

| Variable | Purpose | Safe default |
|---|---|---|
| `SUPPORT_FROM_EMAIL` | Customer email sender | Configure in target environment |
| `SLACK_SUPPORT_CHANNEL` | Main workflow internal Slack channel | Configure in target environment |
| `MONITOR_TARGET_URL` | Monitoring health-check endpoint | `https://mohammad-shaheed.app.n8n.cloud/healthz` |
| `SLACK_ALERT_CHANNEL` | Monitoring failure-alert channel | `#alerts` |

## Secrets

Gemini, PostgreSQL, SMTP/email, and Slack authentication belong in n8n Credentials. Never commit tokens, passwords, API keys, or real `.env` files.

## Cloud vs self-hosted

For managed n8n Cloud, prefer `$vars` for these workflow settings. For self-hosted deployments, an equivalent `$env` configuration may be used where the instance policy permits environment-variable access.
