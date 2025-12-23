# MCP Server Configuration

This repository includes Model Context Protocol (MCP) server configuration to enhance AI assistant capabilities when working with this codebase.

## What is MCP?

The Model Context Protocol (MCP) is an open protocol that enables AI assistants like GitHub Copilot to securely connect to external tools and data sources.

## Configured Servers

This repository includes two MCP servers:

### 1. GitHub Server
- **Purpose**: Provides AI assistants with GitHub repository management capabilities
- **Features**: 
  - View and manage issues
  - Access pull requests
  - Read repository files
  - Interact with GitHub API
- **Authentication**: Requires a GitHub Personal Access Token (PAT) set in the `GITHUB_PERSONAL_ACCESS_TOKEN` environment variable

### 2. Filesystem Server
- **Purpose**: Provides AI assistants with secure access to repository files
- **Features**:
  - Read repository files and directories
  - Navigate the codebase structure
  - Analyze file contents
- **Scope**: Limited to the current repository directory

## Setup

### Prerequisites
- Node.js installed (for `npx` to work)
- GitHub Copilot or another MCP-compatible AI assistant

### Configuration File
The MCP server configuration is stored in `.mcp.json` at the root of the repository.

### GitHub Server Authentication
To use the GitHub MCP server, you need to set up a Personal Access Token:

1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate a new token with appropriate scopes (repo, read:org)
3. Set the token as an environment variable:
   ```bash
   export GITHUB_PERSONAL_ACCESS_TOKEN=your_token_here
   ```

## Usage

If you're using an MCP-compatible AI assistant (like GitHub Copilot with MCP support), it will automatically detect and use the `.mcp.json` configuration when working in this repository.

The servers will be invoked automatically when the AI needs to:
- Access GitHub repository information
- Read or analyze files in the repository
- Perform repository management tasks

## Security Notes

- Never commit your GitHub Personal Access Token to the repository
- The filesystem server only has access to the repository directory
- All MCP servers run locally and don't send your data to external services

## Learn More

- [Model Context Protocol Documentation](https://modelcontextprotocol.io/)
- [MCP Servers Repository](https://github.com/modelcontextprotocol/servers)
- [GitHub Copilot MCP Integration](https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp)
