# n8n Workflow Development Repository

This repository contains configuration files, documentation, and tools for developing n8n workflows with enhanced AI assistance through Claude Code and n8n-MCP integration.

## What is this repository?

This is a specialized development environment for creating, validating, and deploying n8n automation workflows. It provides:

- **AI-Powered Workflow Development**: Integration with Claude Code for intelligent n8n workflow creation
- **n8n-MCP Tools**: Access to comprehensive n8n Model Context Protocol tools for node discovery, validation, and deployment
- **Best Practices**: Structured workflow development process with validation at every step
- **Template Workflows**: Pre-built automation examples like Google Docs to Sheets integration

## Key Features

### 🤖 Claude Code Integration
- Intelligent n8n workflow design and implementation
- Automated node discovery and configuration
- Real-time validation and error checking
- Best practices enforcement

### 🔧 n8n-MCP Tools Access
- 525+ n8n nodes with comprehensive documentation
- 263 AI-optimized nodes for advanced automation
- Template library with 399+ community workflows
- Complete workflow validation and testing

### 📋 Structured Development Process
1. **Discovery Phase**: Find the right nodes for your automation
2. **Pre-Validation**: Validate configurations before building
3. **Building Phase**: Construct workflows with validated components
4. **Workflow Validation**: Complete validation including connections and expressions
5. **Deployment**: Deploy only after all validations pass
6. **Post-Validation**: Verify deployment success

## Repository Structure

```
├── README.md                 # This file
├── claude.md                 # Core Claude Code instructions for n8n development
├── workflow-setup-guide.md   # Example: Google Docs to Sheets automation guide
├── .cursor/
│   ├── mcp.json             # n8n-MCP server configuration
│   └── rules/
│       └── n8n-mcp.mdc      # Development rules and guidelines
├── newtest.json             # Sample workflow JSON
├── openaiprompt.md          # OpenAI integration examples
└── triwestschema.md         # Schema documentation
```

## Getting Started

### Prerequisites
- n8n instance (cloud or self-hosted)
- Claude Code with n8n-MCP integration
- Access to the configured n8n API endpoint

### Setup
1. Clone this repository
2. Configure your n8n API credentials in `.cursor/mcp.json`
3. Follow the workflow development process outlined in `claude.md`

### Example Workflow
The repository includes a complete example workflow that:
- Reads content from 8 Google Documents
- Extracts structured data using AI parsing
- Updates corresponding rows in Google Sheets
- Handles dropdown mappings and data validation

## Development Philosophy

### Key Principles
- **Validate Early and Often**: Catch errors before deployment
- **Use Standard Nodes**: Prefer built-in nodes over custom code
- **Incremental Updates**: Use diff operations for efficient workflow updates
- **Comprehensive Testing**: Validate both locally and after deployment

### Validation Strategy
- **Before Building**: Check required fields and validate configurations
- **After Building**: Complete workflow validation including connections and expressions
- **After Deployment**: Verify deployed workflows and monitor execution

## Tools and Capabilities

This repository provides access to:
- Node discovery and search across 525+ available nodes
- Pre-configured templates for common automation tasks
- Real-time workflow validation and error checking
- AI-powered node configuration and optimization
- Direct deployment to n8n instances
- Execution monitoring and debugging tools

## Contributing

When developing workflows:
1. Follow the structured development process in `claude.md`
2. Always validate configurations before deployment
3. Use the provided MCP tools for node discovery and validation
4. Document your workflows following the established patterns

## Support

For issues with:
- **n8n workflows**: Check the workflow validation tools and execution logs
- **MCP integration**: Verify API credentials and endpoint configuration
- **Claude Code**: Refer to the Claude Code documentation

## License

This repository contains configuration and documentation files for n8n workflow development. Refer to n8n's licensing terms for workflow deployment and usage.