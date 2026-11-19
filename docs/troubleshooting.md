# Troubleshooting journal

## Codex executable missing
**Observed:** `zsh: command not found: codex` while AWS toolkit attempted MCP setup.  
**Resolution:** Installed Codex CLI through Homebrew and verified `codex --version`.

## Duplicate npm installation
**Observed:** `npm ERR! EEXIST` for `/opt/homebrew/bin/codex`.  
**Cause:** Homebrew had already installed the executable.  
**Resolution:** Retained Homebrew installation; did not force overwrite.

## AWS MCP initial setup unavailable
**Observed:** Toolkit reported Codex needed to be on PATH.  
**Resolution:** Installed Codex CLI; subsequently configured MCP separately.

## Validation
Codex reported successful read-only calls to Azure and AWS, with no authentication or permission errors. Screenshot evidence of the final MCP response remains to be added.
