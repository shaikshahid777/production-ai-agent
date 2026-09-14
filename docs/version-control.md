# Version Control & Git Export

Export both n8n workflows as JSON and keep them under workflows/.

Use main as the production-ready branch. Use descriptive commits and Git tags for releases. Never commit API keys, tokens, passwords, real .env files, or embedded credential secrets.

Rollback can be performed by reverting a workflow commit and re-importing the known-good JSON into n8n.