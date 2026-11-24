# specgit MCP server setup guide for agents and IDE installers

Use this file to configure the remote **specgit** MCP server (`com.specgit/docs-agent`) in an MCP-compatible host or IDE.

## Server details

- **Name:** `specgit`
- **Registry ID:** `com.specgit/docs-agent`
- **Transport:** Streamable HTTP (`http` / `streamable-http`)
- **Endpoint URL:** `https://specgit.com/api/agent`
- **Authentication:** OAuth 2.1 with PKCE (`S256`), discovered automatically via RFC 9728 (`https://specgit.com/.well-known/oauth-protected-resource/api/agent`) and RFC 8414 (`https://specgit.com/.well-known/oauth-authorization-server`). Clients identify themselves with Client ID Metadata Documents or Dynamic Client Registration (`https://specgit.com/oauth/register`).
- **API keys or local binaries:** None. This is a remote server with nothing to build or run locally.

## Configuration by client

### Cline (`cline_mcp_settings.json`)

Add the following entry under `mcpServers` in Cline's MCP settings file:

```json
{
  "mcpServers": {
    "specgit": {
      "url": "https://specgit.com/api/agent",
      "type": "streamableHttp",
      "disabled": false
    }
  }
}
```

### Cursor (`~/.cursor/mcp.json` or `.cursor/mcp.json`)

```json
{
  "mcpServers": {
    "specgit": {
      "url": "https://specgit.com/api/agent"
    }
  }
}
```

### VS Code (`.vscode/mcp.json`)

```json
{
  "servers": {
    "specgit": {
      "type": "http",
      "url": "https://specgit.com/api/agent"
    }
  }
}
```

### Claude Code

Run in a terminal:

```bash
claude mcp add --transport http specgit https://specgit.com/api/agent
```

### Windsurf and other Streamable HTTP MCP clients

Register a remote Streamable HTTP server named `specgit` pointing to `https://specgit.com/api/agent` with OAuth 2.1 enabled and no static headers or client secret.

## First-time authorization

1. Trigger a connection or tool listing in the host.
2. When the server responds `401` with `WWW-Authenticate` pointing at `https://specgit.com/.well-known/oauth-protected-resource/api/agent`, open the browser authorization prompt for the person.
3. The person signs in with GitHub (through the specgit GitHub App), chooses a scope (`docs:read`, `docs:comment`, or `docs:edit`), and chooses a grant duration (30 days, 90 days, or until removed).
4. Never enter credentials or complete GitHub sign-in on the person's behalf.

## Access rules and verification

- Reading documents, reviewing, and commenting work on every plan. Editing Markdown documents, Obsidian Canvas boards (`.canvas`), and Obsidian Bases (`.base` YAML files) requires the repository owner on Pro or Pro Plus.
- Read and comment access cannot publish or submit a document for review. With edit access, the agent can propose publishing, submitting for review, or catching up, and an edit grant can also submit for review or publish on documents the person can open (GitHub's branch rules still apply). Only people accept suggestions, and no tool deletes a file.
- Verify the connection by calling `tools/list` on `https://specgit.com/api/agent` and reading a repository document with `read_document`.
- Full documentation: `https://specgit.com/developers` and `https://specgit.com/auth.md`.
