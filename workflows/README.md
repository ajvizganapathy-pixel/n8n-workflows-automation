# Workflows

This directory contains all n8n workflow JSON exports organized by category.

## Structure

```
workflows/
├── email/          # Email automation workflows
├── data-sync/      # Data synchronization workflows
├── payments/       # Payment and billing workflows
├── notifications/  # Alert and notification workflows
└── analytics/      # Reporting and analytics workflows
```

## Importing a Workflow

**Via n8n UI:**
1. Open the n8n dashboard
2. Click **Menu → Import from File**
3. Select the `.json` file

**Via CLI:**
```bash
n8n import:workflow --input=./workflows/email/email-parser.json
```

## Contributing a Workflow

See [CONTRIBUTING.md](../CONTRIBUTING.md) for standards and the submission process.
