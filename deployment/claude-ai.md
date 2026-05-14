# Deployment: Claude.ai

Deploy this trainer as a Claude.ai **Project** so the system prompt persists across conversations.

## Setup

1. Go to Claude.ai → **Projects** → **New project**
2. Name it (e.g. "Prompt Trainer")
3. In **Project instructions**, paste the contents of `CLAUDE.md` with the adaptations below
4. Optionally upload `docs/techniques-library.md` and `docs/anti-patterns-2026.md` as project files

---

## Adaptations required

Claude.ai has no shell access or MCP tools. Remove or replace these sections from `CLAUDE.md`:

| Section to change | What to do |
|-------------------|------------|
| Tool selection guide reference | Remove — Claude.ai has built-in web search; no Perplexity/BrightData |
| `deployment/claude-code.md` reference | Remove or replace with: "Use Claude.ai's built-in search for factual validation" |
| `ls -lh` and file-size instructions | Remove — no shell access |
| Principle 6 / context scale management | Simplify to: "If a user's request involves very large amounts of content, suggest working one section at a time" |

---

## Adapted system prompt (paste into Project instructions)

Copy `CLAUDE.md` and make the following replacements:

```
# In the DO section, replace the tool validation line with:
- Validate factual claims using Claude's built-in web search before answering

# Remove this line from DO NOT:
- Read large files without a size check first
```

---

## Limitations vs. Claude Code

| Capability | Claude Code | Claude.ai |
|------------|-------------|-----------|
| Auto-loads CLAUDE.md | ✅ | ❌ (paste manually into Project) |
| Shell / file access | ✅ | ❌ |
| Perplexity / BrightData | ✅ (via MCP) | ❌ |
| Built-in web search | ✅ | ✅ |
| Reference files as knowledge | Via filesystem | Upload to Project |
| Persistent context | Per session | Per Project |
