# Using Recall inside Claude

Once Recall is installed, Claude can search your local files through an
MCP connection. You don't call the tools yourself — just ask Claude in
plain English. This page is a quick tour of what to ask for.

---

## What Recall sees

- Files in the folders you added during install (and any you add later).
- Documents, images, email, code, and other common file kinds.
- Metadata (filename, author, dates, tags, GPS, people in photos) **and**
  body text once parsing finishes.

Recall runs **locally**. Nothing leaves your machine.

---

## What to ask

Phrase questions naturally. A few patterns that work well:

**Find files by metadata**
- "What PDFs did I download from arxiv last month?"
- "Show me photos with GPS coordinates from 2023."
- "Files tagged 'invoice' from this year."

**Find by content**
- "What did the lease say about pets?"
- "Find the email where Sarah mentioned the Q3 budget."
- "Which doc has the deployment checklist?"

**Photos of people**
- "Photos of Alice."
- "Photos of Alice from 2019."
- "Photos of Alice that aren't in Seattle."

**Explore your corpus**
- "What folders should I add to Recall?"
- "What hasn't been indexed yet?"

---

## Tips

- **Be specific when you can.** "PDFs about taxes from 2024" beats "tax
  stuff" — Recall can filter on dates, kinds, and tags directly.
- **Citations are clickable.** Claude's answers include
  `recall://file/...` links that point to the exact file or chunk it
  used. Open them to see the source.
- **If results feel thin, ask Claude to broaden.** "Try the body text
  instead" or "search without the date filter" usually helps.
- **Indexing happens in the background.** Right after install,
  body-text search may miss files that haven't been parsed yet.
  Claude will tell you when results are partial.

---

## Lite mode

If you installed Recall without Ollama, semantic search is disabled —
Claude falls back to keyword-only matching. Paraphrases ("car" vs
"vehicle") won't match. Use literal terms from the document, or install
Ollama to enable full search.

---

## Troubleshooting

- **Claude says it can't find Recall.** Restart Claude after installing
  Recall, and confirm the Recall MCP server is enabled in Claude's
  connector settings.
- **Search returns nothing.** The initial scan may still be running.
  Check the Recall app's status bar.
- **A specific file is missing.** Confirm its folder is in your
  configured roots, then ask Claude to "rescan."
