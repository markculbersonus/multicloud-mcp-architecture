# Installation and verification

Prerequisites: macOS, Homebrew, Node.js/npx, Azure CLI, AWS authentication appropriate to the account, and Codex CLI.

```bash
brew install --cask codex
codex --version
az login
az account show --output table
aws sts get-caller-identity
```

Register Azure MCP (check current upstream server requirements before executing):
```bash
codex mcp add azure-mcp -- npx -y @azure/mcp@latest server start
```

AWS remote MCP registration used in the lab:
```bash
codex mcp add aws-mcp --url "https://aws-mcp.us-east-1.api.aws/mcp?oauth=initialize"
```

Authenticate using the server's supported sign-in flow. Then:
```bash
codex mcp list
```

In Codex, request **read-only** subscription discovery on Azure and identity/region discovery on AWS. Verify the tool responses and record only sanitized evidence. Listing registered servers is not proof of authentication.

The AWS MCP endpoint region is not necessarily the region where AWS workloads are deployed. Project-level region restrictions may still apply.
