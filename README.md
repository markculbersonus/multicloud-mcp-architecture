# Multi-Cloud MCP Integration with OpenAI Codex ☁️

**Azure + AWS | Model Context Protocol | AI-assisted cloud engineering**

![Architecture diagram](diagrams/multicloud-mcp-architecture.svg)

## The problem
Cloud engineers often switch between separate consoles and command-line tools to investigate resources. This project explores a single AI-assisted interface for **read-only cloud discovery**, without claiming that the AI agent independently manages cloud infrastructure.

## What I built
- Installed OpenAI Codex CLI (verified as v0.170.0).
- Installed and verified **25 AWS agent skills**; installed Azure agent skills.
- Registered the **Azure MCP Server** and **AWS MCP Server** in Codex.
- Successfully queried both cloud environments using **read-only** requests.

## Verified results
| Provider | Validation | Outcome |
|---|---|---|
| Azure | Subscription discovery | 1 enabled default subscription |
| AWS | Account/role identity and EC2 region discovery | Assumed role identified; 17 regions reported enabled |
| Both | Authentication and permission errors in tested calls | None reported |

**Scope:** The AWS region listing does not establish EC2 deployment permissions in those regions. No create/update/delete operations were tested. The role name does not prove unrestricted access.

## Architecture
Codex → Azure MCP Server → Azure subscription discovery  
Codex → AWS MCP Server → AWS identity and region discovery

Azure and AWS skills provide instructions to the agent; MCP servers provide callable tools. These are distinct from the Terraform provider and cloud CLI.

## Evidence
Screenshots capture the **local installation and troubleshooting process**, not the final MCP read-only response. The final validation output was provided as a textual test result; a sanitized terminal screenshot of that output is still needed.

| Screenshot | Evidence |
|---|---|
| [01 — AWS skills installed](screenshots/01-aws-skills-installed.png) | Installation of 25 skills |
| [02 — MCP setup troubleshooting](screenshots/02-mcp-setup-troubleshooting.png) | Initial Codex executable missing |
| [03 — Codex CLI installation](screenshots/03-codex-cli-installation.png) | Successful Homebrew install; npm duplicate-path error |
| [04 — Codex hooks](screenshots/04-codex-hooks.png) | SessionStart hook active |
| [05 — AWS skills verified](screenshots/05-aws-skills-verified.png) | CLI version and local AWS skill folders |

## Reproduce the setup
See [installation guide](docs/installation-guide.md), [security considerations](docs/security-considerations.md), and [troubleshooting](docs/troubleshooting.md). The sample MCP configuration is **illustrative** and does not include credentials.

## Future improvements — not yet completed
- Terraform validation and approval-gated deployments
- Seven specialized Codex agents
- Automated MCP integration checks
- Sanitized screenshot of successful Azure/AWS MCP discovery

## Skills demonstrated
MCP integration · Cloud authentication · Multi-cloud discovery · CLI troubleshooting · Agent skill configuration · Security-conscious documentation

> This repository documents configuration and validation of existing MCP servers. It does **not** claim development of a custom MCP server.
