# specgit for Cursor

specgit is a real-time collaborative visual editor built straight on GitHub. Teams write specs, Markdown docs, Obsidian Canvas boards, and Bases visually in a browser or Obsidian without learning Git, while every save stays a commit, every inline comment stays a GitHub pull request thread, and GitHub stays the source of truth.

Connect specgit to Cursor to join your team's live rooms directly from your editor, with the same capabilities teammates and built-in Ask Agent already have.

## Key capabilities

- **Embedded live editor:** Open docs and boards right inside Cursor with live teammate cursors, one-click **Undo** on direct agent edits, and full-screen access to comments, review, and the Status panel.
- **Suggestions that wait for people:** Ask Cursor to suggest wording with **Accept** and **Reject** buttons so nothing changes until a person approves.
- **Review and comment triage:** Run a document review that leaves inline comments on exact words, or triage open threads so Cursor replies under your GitHub name and suggests fixes.
- **Obsidian Canvas boards, Bases, and new files:** Add, edit, move, connect, and group Canvas cards and tidy lanes with one **Undo** for the whole step, or create and rename Markdown docs, boards, and `.base` files and add images from a web address or attached file.
- **Publishing under GitHub rules:** Read and comment access cannot submit or publish. Edit access can open the review or publish card and can also submit for review or publish on documents you can open, while GitHub branch rules always apply. No tool deletes a file.

## Permissions, plans, and privacy

Sign in with GitHub (no API keys), choose **Read documents**, **Read and comment**, or **Read, comment and edit** and a grant duration, and remove access any time in **Connected agents**.

Reading, reviewing, and commenting work on every plan, including Free. Opening the embedded live editor and editing require the repository owner to be on a paid specgit plan. People can still edit in specgit on any plan. Connected agents run on Cursor's own model and use zero specgit agent usage.

**Zero Content Retention:** specgit never keeps a copy of your documents or comments, with narrow exceptions listed at [specgit.com/privacy](https://specgit.com/privacy). GitHub stays the source of truth. What Cursor reads through specgit is processed by Cursor under your agreement with it.

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
