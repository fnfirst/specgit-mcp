# specgit MCP

Work together, live, in the docs and boards your team keeps in GitHub. Edit, suggest, and comment from your agent, under the access you choose.

**specgit** (by FnFirst) hosts a remote Streamable HTTP MCP server at `https://specgit.com/api/agent` (Official MCP Registry ID: `com.specgit/docs-agent`). There is nothing to build or run locally and no API keys to manage: every person signs in through OAuth 2.1 with their own GitHub account and chooses what each agent may do.

## What the connector does

- **Live collaborative editing:** open, read, edit, rewrite sections, and insert text in Markdown documents and Obsidian Bases (`.base` YAML files) kept in GitHub, alongside teammates editing live. Each agent edit can be undone.
- **Suggestions:** propose wording or section rewrites that leave the document unchanged until a person accepts or rejects them in specgit. Only people accept suggestions.
- **Comments, review, and triage:** comment on exact words, reply to pull request review threads, resolve them, run a structured review, or triage open threads with replies and suggested edits.
- **Obsidian Canvas boards:** add, edit, move, resize, restyle, connect, and group cards and tidy lanes on `.canvas` boards live, with undo.
- **File actions:** create and rename Markdown documents, `.canvas` boards, and `.base` files, and add images from a web address or attachment. A new document starts as a draft for review, never as the published version.
- **Review and publish controls:** read and comment access cannot publish or submit a document for review. With edit access, the agent can propose publishing, submitting for review, or catching up in the editor card, and an edit grant can also submit for review or publish on documents you can open (GitHub's branch rules still apply). No tool deletes a file.

In Claude, ChatGPT, and Cursor, the specgit editor appears right inside the conversation through MCP Apps. In other MCP clients, each result links to the document on `https://specgit.com`.

## Connect

Every client connects to the same remote Streamable HTTP endpoint:

```text
https://specgit.com/api/agent
```

### Claude and Claude Code

- **Claude web and desktop (one-click install):** [Add to Claude](https://claude.ai/plugins/id/plugin_01UQgcQn9KB6q2DFXiWuhMza?via=directory) (or add a custom connector pointing to `https://specgit.com/api/agent` under **Customize**, **Connectors**, then choose **Connect** and sign in with GitHub).
- **Claude Code (plugin):**

```bash
/plugin marketplace add fnfirst/specgit-mcp
/plugin install specgit@specgit-mcp
```

- **Claude Code (CLI):**

```bash
claude mcp add --transport http specgit https://specgit.com/api/agent
```

### Cursor

- **One-click install:** [Add to Cursor](https://cursor.com/install-mcp?name=specgit&config=eyJ1cmwiOiJodHRwczovL3NwZWNnaXQuY29tL2FwaS9hZ2VudCJ9)
- **Manual config (`~/.cursor/mcp.json` or `.cursor/mcp.json`):**

```json
{
  "mcpServers": {
    "specgit": {
      "url": "https://specgit.com/api/agent"
    }
  }
}
```

### VS Code

- **One-click install:** [Install in VS Code](https://vscode.dev/redirect/mcp/install?name=specgit&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fspecgit.com%2Fapi%2Fagent%22%7D)
- **Workspace config (`.vscode/mcp.json`):**

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

### ChatGPT

Turn on developer mode in ChatGPT settings, add a custom connector pointing at `https://specgit.com/api/agent` with OAuth sign-in, choose **Connect**, and sign in with GitHub.

### Gemini, Grok, Windsurf, Cline, and other MCP clients

Add `https://specgit.com/api/agent` as a remote Streamable HTTP MCP server. Clients that support OAuth 2.1 discovery find the authorization server automatically through `/.well-known/oauth-protected-resource/api/agent`. See [`llms-install.md`](./llms-install.md) for agent installer instructions and `https://specgit.com/auth.md` for manual OAuth steps.

## Permissions, plans, and privacy

- **Access scopes:** choose **Read documents** (`docs:read`), **Read and comment** (`docs:comment`), or **Read, comment and edit** (`docs:edit`), and choose how long the grant lasts (30 days, 90 days, or until you remove it). Remove any agent at any time in specgit under **Settings**, **Connected agents**, or revoke its token at `https://specgit.com/oauth/revoke`.
- **Plans:** reading documents, reviewing, and commenting work on every plan, including Free. Editing and opening the embedded live editor require the repository owner to be on Pro or Pro Plus. Outside agents run on your host's own model and use zero specgit agent usage.
- **Privacy:** Zero Content Retention: specgit never keeps a copy of your documents or comments, with narrow exceptions listed at `https://specgit.com/privacy`. GitHub remains the source of truth. What your connected agent reads through specgit is processed by your host's provider under your agreement with it.

## Resources

- Developer docs and full tool list: `https://specgit.com/developers`
- OAuth 2.1 auth guide: `https://specgit.com/auth.md`
- No-account sandbox: `https://specgit.com/try`
- Security: `https://specgit.com/security`
- Privacy policy: `https://specgit.com/privacy`
- Support: `https://specgit.com/support` (`support@specgit.com`)

## License

MIT. See [`LICENSE`](./LICENSE). This repository holds public connector metadata and setup documentation for specgit's remote MCP server; it contains no proprietary server code.
