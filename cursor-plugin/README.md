# specgit for Cursor

Work together, live, in the docs and boards your team keeps in GitHub. Edit, suggest, and comment from Cursor, under the access you choose.

Open the specgit editor right in the conversation: the document, who's in it, and the agent's latest change with **Undo**, or **Accept** and **Reject** for a suggested edit. Open it full screen for comments, review and the Status panel.

Ask for a review or a triage. In a review, the agent comments on what it finds. In a triage, it answers each open comment and suggests the changes the comment asks for.

Work on boards: add, edit, move, connect and group cards and tidy lanes, with one **Undo** for the whole step.

Create and rename documents, boards, and Obsidian Bases (.base) files, and add images from a web address or an attached file. A new document starts as a draft for review, never as the published version.

Read and comment access can't publish or send a document for review. With edit access, the agent can show the publish or review card, and an edit grant can also submit for review or publish on documents you can open (GitHub's branch rules still apply). No tool deletes a file.

Sign in with GitHub and choose what the agent may do (**Read documents**, **Read and comment**, or **Read, comment and edit**) and for how long. Remove it at any time in **Connected agents**.

Reading a document, reviewing and commenting work on every plan, including Free. Agent edits, and the editor in the conversation, need the repository owner to be on a paid specgit plan. People can still edit in specgit on any plan. The agent runs on Cursor's own model and doesn't count toward your specgit agent usage.

Zero Content Retention: specgit never keeps a copy of your documents or comments, with narrow exceptions listed at specgit.com/privacy. GitHub stays the source of truth. What Cursor reads through specgit is processed by Cursor under your agreement with it.

## Connect

Install the plugin from the Cursor Marketplace. The first time Cursor uses specgit, it
opens specgit in your browser:

1. Sign in with GitHub.
2. Choose what Cursor may do: read, read and comment, or read, comment and edit.
3. Choose how long: 30 days, 90 days, or until you remove it.

You can remove its access any time in specgit, under Settings, Connected agents.

To add it without the plugin, put this in `mcp.json`:

```json
{
  "mcpServers": {
    "specgit": { "url": "https://specgit.com/api/agent" }
  }
}
```

## Learn more

- [Try the editor, no sign-up](https://specgit.com/try)
- [How specgit works](https://specgit.com/how-it-works)
- [Obsidian for teams: collaborate on a vault in GitHub](https://specgit.com/obsidian-github-collaboration)
- [Introducing Canvas: Obsidian boards in specgit](https://specgit.com/blog/introducing-canvas)
- [Why product specs go stale and how to fix it](https://specgit.com/blog/why-product-specs-go-stale)
- Docs: [specgit.com/developers](https://specgit.com/developers)
- Support: [specgit.com/support](https://specgit.com/support)
- Privacy: [specgit.com/privacy](https://specgit.com/privacy)
