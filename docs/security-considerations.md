# Security considerations

- Never commit AWS access keys, secret keys, tokens, `.aws/credentials`, Azure tokens, or `.env` files.
- Use short-lived identities and least privilege where possible.
- Review MCP tools and their effective permissions before enabling write operations.
- Require human approval before any create, update, or delete operation.
- Use read-only queries for discovery validation.
- Rotate any credential that appeared in a screenshot, even in a temporary lab.
- Mask account identifiers, tenant/subscription identifiers, email addresses, and other unnecessary metadata in published evidence.
- AWS `DescribeRegions` reporting a region as enabled does not establish authorization to launch resources there.
- Keep the distinction clear between **installed skills**, **registered MCP connections**, **authenticated queries**, and **verified deployments**.
