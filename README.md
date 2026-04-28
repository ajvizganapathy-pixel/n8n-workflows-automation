# n8n Workflows & Automation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![n8n Version](https://img.shields.io/badge/n8n-%3E%3D1.0.0-blue.svg)](https://n8n.io)
[![Node.js](https://img.shields.io/badge/Node.js-%3E%3D18.10.0-green.svg)](https://nodejs.org)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)](#)

A comprehensive collection of production-ready n8n workflows and automation solutions for seamless business process integration.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Available Workflows](#available-workflows)
- [Usage](#usage)
- [Workflow Documentation](#workflow-documentation)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [Support](#support)
- [License](#license)

## 🎯 Overview

This repository contains a curated collection of production-grade n8n workflows designed to automate critical business processes. Each workflow has been tested, optimized, and documented for reliability and maintainability in production environments.

**n8n** is a workflow automation platform that enables you to connect apps and automate processes without coding. These workflows extend that capability with:

- ✅ **Production-Ready** - Tested and optimized for reliability
- 🔧 **Easy Integration** - Drop-in workflows with minimal configuration
- 📊 **Error Handling** - Built-in error recovery and notifications
- 🔐 **Secure** - Following security best practices
- 📈 **Scalable** - Designed to handle enterprise-level volumes
- 📝 **Well-Documented** - Complete setup and usage guides

## ✨ Features

### Core Capabilities

- **Multi-Service Integration** - Connect 400+ applications and APIs
- **Data Transformation** - ETL pipelines with complex data operations
- **Real-Time Automation** - Webhook triggers for immediate execution
- **Error Recovery** - Automatic retry logic and failure notifications
- **Scheduled Workflows** - Cron-based automation for recurring tasks
- **Conditional Logic** - Sophisticated branching and decision trees
- **Data Validation** - Input validation and data consistency checks
- **Audit Logging** - Complete execution history and debugging

### Workflow Categories

- 📧 **Email Automation** - Send, parse, and manage emails
- 📊 **Data Sync** - Synchronize data across multiple systems
- 💰 **Payment Processing** - Invoice and payment automation
- 📱 **Notification Systems** - Multi-channel alerts and updates
- 📈 **Analytics** - Data collection and reporting
- 🔄 **Integration Pipelines** - Complex system-to-system connections

## 📋 Prerequisites

### System Requirements

- **Node.js**: 18.10.0 or higher (LTS recommended)
- **RAM**: 4GB minimum (8GB+ for production)
- **Storage**: 20GB free space
- **Database**: PostgreSQL 12+ (recommended for production)
- **OS**: Linux, macOS, or Windows

### Required Software

- [n8n](https://n8n.io) v1.0.0 or higher
- [Docker](https://docker.com) (optional but recommended)
- [Docker Compose](https://docs.docker.com/compose/) (optional)
- Git for cloning the repository

### API Access

Depending on workflows used, you'll need API keys/credentials for:
- Email services (Gmail, Outlook, SendGrid)
- CRM systems (Salesforce, HubSpot, Pipedrive)
- Payment processors (Stripe, PayPal)
- Cloud storage (AWS S3, Google Drive, OneDrive)
- Communication tools (Slack, Microsoft Teams)

## 🚀 Installation

### Option 1: Docker (Recommended for Production)

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/n8n-workflows.git
   cd n8n-workflows
   ```

2. **Copy environment configuration**
   ```bash
   cp .env.example .env
   ```

3. **Configure environment variables**
   ```bash
   # Edit .env with your settings
   nano .env
   ```

4. **Start with Docker Compose**
   ```bash
   docker-compose up -d
   ```

5. **Access n8n**
   - Open `http://localhost:5678` in your browser
   - Default credentials: `admin` / `password` (change immediately)

### Option 2: NPM Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/n8n-workflows.git
   cd n8n-workflows
   ```

2. **Install n8n globally**
   ```bash
   npm install -g n8n
   ```

3. **Install workflow dependencies**
   ```bash
   npm install
   ```

4. **Start n8n**
   ```bash
   n8n start
   ```

### Option 3: Docker Compose with PostgreSQL

For production deployments with database persistence:

```bash
docker-compose -f docker-compose.prod.yml up -d
```

This configuration includes:
- n8n service
- PostgreSQL database
- Persistent data volumes
- Network isolation

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the project root:

```env
# Basic Authentication
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=your-secure-password

# Server Configuration
N8N_HOST=0.0.0.0
N8N_PORT=5678
N8N_PROTOCOL=https
N8N_DOMAIN=n8n.yourdomain.com

# Database Configuration
DB_TYPE=postgres
DB_POSTGRESDB_HOST=postgres
DB_POSTGRESDB_PORT=5432
DB_POSTGRESDB_USER=n8n
DB_POSTGRESDB_PASSWORD=secure_password
DB_POSTGRESDB_DATABASE=n8n

# Encryption
N8N_ENCRYPTION_KEY=your-encryption-key

# Webhook Configuration
WEBHOOK_TUNNEL_URL=https://n8n.yourdomain.com/
WEBHOOK_TUNNEL_REDIRECT_AUTHORIZATION_URL=false

# Security
NODE_TLS_REJECT_UNAUTHORIZED=1
```

### Importing Workflows

1. **Via UI**
   - Open n8n dashboard
   - Click "Menu" → "Import from File"
   - Select workflow JSON file

2. **Via Command Line**
   ```bash
   n8n import:workflow --input=/path/to/workflow.json
   ```

3. **Via Docker Volume**
   - Place workflow files in `./workflows` directory
   - Workflows auto-import on startup

## 📚 Available Workflows

### Email Automation
- **Email Parser** - Extract and process incoming emails
- **Email Campaign** - Automated email sequences
- **Daily Digest** - Compile and send daily reports

### Data Synchronization
- **CRM Sync** - Synchronize contacts across CRM systems
- **Database Backup** - Automated data backup to cloud storage
- **Inventory Sync** - Real-time inventory updates

### Payment & Billing
- **Invoice Generator** - Auto-generate and send invoices
- **Payment Reminder** - Automated payment notifications
- **Expense Tracking** - Categorize and log expenses

### Notifications
- **Slack Alerts** - Critical event notifications
- **SMS Alerts** - Emergency notifications via SMS
- **Multi-Channel** - Route alerts to appropriate channels

### Analytics & Reporting
- **Sales Report** - Daily/weekly/monthly sales summaries
- **Performance Dashboard** - KPI tracking and metrics
- **Data Export** - Export data to spreadsheets

See [Workflows Documentation](#workflow-documentation) for detailed descriptions.

## 🎬 Usage

### Running Workflows Manually

1. **Open Workflow**
   - Navigate to Workflows in dashboard
   - Click on workflow name

2. **Execute**
   - Click "Execute Workflow" button
   - Monitor execution in logs

3. **View Results**
   - Check execution history
   - Review output data

### Scheduling Workflows

1. **Open Workflow**
   - Edit the trigger node
   - Select "Schedule" trigger type

2. **Configure Schedule**
   - Set frequency (daily, hourly, custom cron)
   - Choose timezone

3. **Enable & Save**
   - Click enable toggle
   - Save workflow

### Webhook Triggers

Create external triggers for workflows:

```bash
# Workflow webhook URL format
https://n8n.yourdomain.com/webhook/workflow-name

# Trigger with POST request
curl -X POST https://n8n.yourdomain.com/webhook/workflow-name \
  -H "Content-Type: application/json" \
  -d '{"key": "value"}'
```

## 📖 Workflow Documentation

### Workflow Structure

Each workflow includes:
- **Description** - Purpose and use case
- **Triggers** - How the workflow starts
- **Processing** - Data transformation steps
- **Output** - Expected results
- **Error Handling** - Failure scenarios
- **Configuration** - Required credentials and settings

### Example: Email Campaign Workflow

```
Trigger: Schedule (Daily at 9 AM)
  ↓
Get Subscriber List (Database query)
  ↓
Filter Active Subscribers (Conditional)
  ↓
Generate Email Content (Template)
  ↓
Send Emails (Gmail/SendGrid)
  ↓
Log Campaign Results (Database)
  ↓
Notify on Completion (Slack)
```

### Configuration Requirements by Workflow

| Workflow | Required Services | Difficulty |
|----------|-------------------|-----------|
| Email Parser | Gmail/Outlook | ⭐ Easy |
| CRM Sync | Salesforce/HubSpot | ⭐⭐ Medium |
| Invoice Generator | Stripe/QuickBooks | ⭐⭐ Medium |
| Payment Processing | Stripe/PayPal | ⭐⭐⭐ Advanced |
| Analytics Dashboard | Google Sheets/Tableau | ⭐⭐ Medium |

## 🔧 Troubleshooting

### Workflow Not Triggering

**Problem**: Scheduled workflow doesn't execute at expected time

**Solutions**:
1. Verify workflow is enabled (toggle in workflow settings)
2. Check server timezone matches expected timezone
3. Review n8n logs: `docker-compose logs n8n`
4. Confirm database connectivity
5. Check for any validation errors in workflow

```bash
# View logs
docker-compose logs -f n8n

# Check database connection
docker-compose exec n8n n8n db:check
```

### Credential Errors

**Problem**: "Invalid credentials" or authentication failures

**Solutions**:
1. Verify credentials are correctly entered
2. Check API key expiration dates
3. Confirm API permissions/scopes
4. Test credentials in API documentation
5. Re-authenticate if credentials changed

### Memory Issues

**Problem**: High memory usage or crashes

**Solutions**:
1. Limit Node.js memory:
   ```bash
   export NODE_OPTIONS="--max-old-space-size=4096"
   ```

2. Optimize workflow:
   - Remove unnecessary loops
   - Use batch processing
   - Add data cleanup steps

3. Upgrade system resources or use PostgreSQL

### Performance Issues

**Problem**: Workflows running slowly

**Solutions**:
1. Check database performance
2. Review API rate limits
3. Optimize data transformations
4. Add workflow logging for bottleneck identification
5. Consider parallel execution for independent tasks

## 🤝 Contributing

We welcome contributions! Here's how to help:

### Before You Start

1. Check existing issues and pull requests
2. Read our [CONTRIBUTING.md](CONTRIBUTING.md)
3. Follow code style guidelines
4. Write descriptive commit messages

### Workflow Contribution Process

1. **Fork the repository**
   ```bash
   git clone https://github.com/yourusername/n8n-workflows.git
   cd n8n-workflows
   git checkout -b feature/new-workflow
   ```

2. **Create your workflow**
   - Use descriptive names
   - Add error handling
   - Include comments for complex logic
   - Test thoroughly

3. **Export and document**
   ```bash
   # Export workflow from n8n UI as JSON
   # Place in workflows/ directory
   # Create documentation in docs/workflows/
   ```

4. **Submit pull request**
   - Provide clear description
   - Include workflow documentation
   - Add usage examples
   - Request review

### Coding Standards

- **Naming**: Use descriptive, snake_case names
- **Comments**: Document complex logic
- **Error Handling**: Include try-catch and notifications
- **Testing**: Test with sample data before submitting
- **Documentation**: Include setup instructions and examples

## 📞 Support

### Getting Help

- **Documentation**: Check [docs](./docs) directory
- **Issues**: Search [GitHub Issues](../../issues)
- **Discussions**: Ask in [Discussions](../../discussions)
- **n8n Community**: [community.n8n.io](https://community.n8n.io)

### Reporting Issues

When reporting bugs, include:
```
- n8n version
- Workflow name and JSON export
- Expected behavior
- Actual behavior
- Error logs
- Steps to reproduce
```

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [n8n](https://n8n.io) - Amazing workflow automation platform
- Contributors and maintainers
- Community feedback and suggestions

## 📊 Status & Roadmap

### Current Version
- **v1.0.0** - Initial release with core workflows
- Last Updated: 2024

### Planned Features
- [ ] Advanced analytics workflows
- [ ] Machine learning integrations
- [ ] Real-time data streaming
- [ ] Enhanced error recovery
- [ ] Workflow templates library
- [ ] Performance monitoring dashboard

---

<div align="center">

**[Star us on GitHub](../../) if this helps your automation journey!** ⭐

[Website](https://n8n.io) • [Documentation](https://docs.n8n.io) • [Community](https://community.n8n.io)

</div>
