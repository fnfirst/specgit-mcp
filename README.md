# specgit for Cursor

specgit makes GitHub a better place for your whole team to write. This plugin brings
Cursor into the documents your team is writing, so it works in the room with you, not
on a copy.

Ask Cursor to open a document or an Obsidian Canvas board, or to show you a picker of
the ones you can open. The specgit editor opens in the chat, live, with your teammates
in it. Cursor reads the text as it is right now, including what someone is typing.

## What Cursor can do

- Edit a sentence, rewrite a section, or add text under a heading. Edits land live
  where your team sees them, and each can be undone.
- Suggest wording instead. Nothing changes until a person accepts it.
- Comment on the exact words in question, reply to threads, and resolve them. Ask for
  a review and it leaves comments. Ask for a triage and it answers each thread and
  suggests the fixes.
- Add, move, connect, and group cards on a board, and lay out its lanes.
- Start a new document or board, rename one, or add an image from a web address.
- Get a document ready to submit for review or publish. You press the button.

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

## What you need

- A GitHub account and a specgit account.
- Reading and commenting work in any repository you can open in specgit.
- The live editor and edits need the repository's owner on a paid specgit plan.
- Cursor works on Markdown documents and Canvas boards.

## Your docs stay in GitHub

Zero Content Retention: specgit never keeps a copy of your documents or comments, with
narrow exceptions listed at [specgit.com/privacy](https://specgit.com/privacy). What
Cursor reads through specgit is processed by Cursor under your agreement with it.

- Docs: [specgit.com/developers](https://specgit.com/developers)
- Support: support@specgit.com
