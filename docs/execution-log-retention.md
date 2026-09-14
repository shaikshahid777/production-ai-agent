# Execution Log Pruning & Retention

Configure pruning at the n8n instance level.

Recommended configuration:

EXECUTIONS_DATA_PRUNE=true
EXECUTIONS_DATA_MAX_AGE=336
EXECUTIONS_DATA_PRUNE_MAX_COUNT=10000

These settings require host-level configuration and an n8n restart. Do not claim server-side pruning is active until it is actually configured and verified.