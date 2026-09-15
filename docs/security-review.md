# Security Review

## Passed / implemented

- Google Gemini 2.5 Flash is used; no OpenAI dependency.
- Workflow JSON does not intentionally contain API tokens or passwords.
- Non-secret runtime configuration is externalized through n8n Variables on Cloud.
- Required webhook fields are validated before downstream processing.
- SQL uses parameter replacement instead of string concatenation.
- Structured AI output parsing and fallback handling are present.
- Monitoring uses timeout handling and routes non-success responses to an alert path.

## Production review items

1. **Webhook authentication:** add suitable authentication or an upstream API gateway before exposing the support endpoint publicly.
2. **Rate limiting:** enforce upstream rate limits for public webhook traffic.
3. **PII minimization:** keep customer data out of Slack messages and execution logs unless operationally required.
4. **Least privilege:** use a database account restricted to the tables/operations required by the workflow.
5. **Secret rotation:** rotate Gemini/Slack/email/database credentials according to operational policy.
6. **Retention:** apply and verify n8n execution pruning at the instance level.
7. **Monitoring delivery:** verify the Slack bot is a member of the alert channel and has the required permission before declaring live alert delivery complete.

## Recording hygiene

Redact credentials, tokens, customer PII, webhook secrets, and private URLs from screenshots and demo recordings.
