# AI-BOM scan fixtures

These are small, static fixtures for testing AI bill-of-materials detection,
not an application or production AI integration.

| Fixture | Intended scan finding |
| --- | --- |
| `fixtures/requirements.txt` | OpenAI Python SDK dependency (`openai`), an AI building block |
| `fixtures/mcp.json` | `microsoft-learn-fixture`, an MCP server configuration |
| `fixtures/skills/fixture-summary/SKILL.md` | `fixture-summary`, an AI instruction skill with name and description |

Nothing here installs dependencies, starts a server, loads a skill, or calls an
API. There are no credentials, model weights, executable agents, or CI workflows.
The MCP file references the public Microsoft Learn documentation endpoint; it
does not connect to it. Keep these examples under `fixtures/`, rather than in
assistant auto-discovery configuration directories, and do not enable or execute
them as part of a scan.

## Checking detection

Use a rules-only static scan, with AI helpers and registry/network lookups
disabled. The detector reads committed files, so commit fixture changes before
scanning this branch. A finding records a declaration, not proof of installation,
runtime use, or a successful MCP connection.

The service normally scans the default branch. Verifying this PR branch locally
does not update the service inventory: that requires merging the PR and a later
default-branch scan. No service scan or merge is triggered by these files.
