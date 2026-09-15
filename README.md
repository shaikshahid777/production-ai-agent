# Production AI Agent — LMS Topic 11

## Autonomous Support & Lead Generation Agent + Production Monitoring

A production-oriented n8n automation package combining an AI-assisted support/lead workflow with scheduled production health monitoring.

### Architecture

**Main workflow**  
Support Webhook → Input Validation → Input Normalization → Customer/Ticket/Account Context → Context Merge → AI Support Agent (Google Gemini 2.5 Flash) → Structured Output Parse & Validate → Decision Routing → Customer/Internal Notifications → Token Usage Logging → Webhook Response.

**Monitoring workflow**  
Schedule (every 15 minutes) → Health Check → Health Decision → Healthy / No Alert OR Slack Alert.

### Engineering practices

- Google Gemini 2.5 Flash; no OpenAI dependency.
- Required-field validation with an explicit validation-error response.
- PostgreSQL queries use parameter replacement rather than string concatenation.
- Structured AI output parsing with fallback/error handling.
- Non-secret runtime configuration uses n8n Variables (`$vars`) with safe defaults.
- Credentials remain in n8n credential storage and are not committed to Git.
- Monitoring includes timeout handling, non-success routing, execution ID, timestamp, target, and HTTP status in alerts.
- Execution retention/pruning is documented as instance-level configuration.
- Security review covers webhook authentication, rate limiting, PII minimization, least-privilege DB access, and secret rotation.

### Repository layout

- `workflows/` — importable n8n workflow JSON exports
- `docs/` — deployment, security, monitoring, retention, version-control and demo documentation
- `screenshots/` — captured execution/evidence screenshots
- `Topic_12_Production_Deployment_Documentation.pdf` — consolidated documentation package

### Verification status

The repository contains the workflow exports and implementation documentation. The healthy monitoring path was verified with HTTP 200/status `ok`; validation and routing paths were tested. Real external delivery depends on credentials and services configured in the target environment.

### Demo

Loom: https://www.loom.com/share/9251611ad7e947b3a6b88415de58adfd

### Repository

Public repository: https://github.com/shaikshahid777/production-ai-agent
