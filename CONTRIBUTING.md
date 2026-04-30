# Contributing to n8n Workflows & Automation

Thank you for your interest in contributing! Here's how to get started.

## How to Contribute

### Reporting Bugs

Open an issue using the [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md) template. Include:
- n8n version
- Workflow JSON (exported from n8n UI)
- Expected vs actual behavior
- Steps to reproduce

### Suggesting Features

Open an issue using the [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md) template.

### Submitting Workflows

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-workflow-name`
3. Export your workflow from n8n as JSON and place it in `workflows/`
4. Follow the [Workflow Standards](#workflow-standards) below
5. Open a pull request using the PR template

## Workflow Standards

- Use descriptive node names (not "HTTP Request 1")
- Add error-handling nodes for critical paths
- Include a `README` inside `workflows/<category>/` describing the workflow
- Test with sample data before submitting
- Do not commit real API keys or credentials

## Coding Standards

- Naming: `snake_case` for files, descriptive names for nodes
- JSON: Format workflow exports with 2-space indentation
- Comments: Document non-obvious logic in the workflow description field

## Code of Conduct

Be respectful and constructive. This project follows the [Contributor Covenant](https://www.contributor-covenant.org/).
