# Deployment: Custom GPT (OpenAI)

Deploy this trainer as a Custom GPT on ChatGPT.

## Setup

1. Go to ChatGPT → **Explore GPTs** → **Create a GPT**
2. In **Configure** → **Instructions**, paste the adapted system prompt (see below)
3. Upload these files to **Knowledge**:
   - `docs/techniques-library.md`
   - `docs/anti-patterns-2026.md`
   - `exercises/00-learning-path.md`
4. Add conversation starters (see below)
5. Set **Web Browsing** to enabled (replaces Perplexity for factual validation)

---

## Adaptations required

Before pasting `CLAUDE.md` into the Instructions field:

| Section to change | What to do |
|-------------------|------------|
| All tool references (Perplexity, BrightData, WebSearch, `deployment/`) | Remove — use ChatGPT's built-in browsing instead |
| Shell / file-size instructions | Remove — no shell access |
| Principle 6 / context scale | Simplify to: "For large content tasks, suggest the user break them into smaller sections" |
| "claude-code.md" references | Remove |

Replace the factual validation DO item with:
```
- Validate factual claims using web browsing before answering
```

---

## Adapted Instructions (summary changes)

Key line in DO section:
```
Validate factual claims by browsing the web before answering. Do not answer
from memory alone for questions involving specific research, statistics, or
current events.
```

---

## Recommended conversation starters

Add these in the GPT configuration:

- "What makes a good prompt?"
- "Review my prompt and tell me how to improve it"
- "I want to practice prompting — where do I start?"
- "Teach me chain-of-thought prompting"
- "What prompting techniques should I stop using in 2026?"

---

## Limitations vs. Claude Code

| Capability | Claude Code | Custom GPT |
|------------|-------------|------------|
| Auto-loads system prompt | ✅ | ✅ (configured once) |
| Shell / file access | ✅ | ❌ |
| Perplexity / BrightData | ✅ | ❌ |
| Built-in web search | ✅ | ✅ |
| Knowledge file upload | Via filesystem | ✅ (up to 20 files) |
| Multi-turn session memory | Per session | ✅ (with Memory enabled) |
| Model | Claude (Anthropic) | GPT-4o (OpenAI) |

> Note: GPT-4o and Claude have different strengths. The coaching logic transfers well, but technique nuances specific to Claude (Extended Thinking, etc.) should be adapted for OpenAI equivalents (o3, o4-mini).
