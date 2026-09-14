# Production AI Agent — Topic 12

Production deployment, monitoring, security hardening, and version-control package for the n8n Autonomous Support & Lead Generation Agent.

## AI model
Google Gemini 2.5 Flash only. No OpenAI dependency.

## Workflows
- workflows/production-ai-agent.json — main support and lead-generation agent.
- workflows/monitoring-workflow.json — Schedule (15 min) → HTTP health check → IF → Slack alert.

## Production hardening
- Environment-specific values use n8n $env references.
- Secrets remain in n8n credentials and are not committed.
- Input validation, structured AI output parsing, fallback/error handling, and parameterized SQL are used.
- Execution pruning and monitoring are documented as instance/environment configuration.

## Honest verification scope
Sandbox verification covered workflow structure and simulated external actions. Real Gemini/Slack/Postgres/SMTP delivery, live health endpoint, server-level pruning, screenshots, and demo video require the operator environment.