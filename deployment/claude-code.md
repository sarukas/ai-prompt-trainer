# Deployment: Claude Code

This is the reference environment for this repo. `CLAUDE.md` is loaded automatically when the repo is opened as a workspace in Claude Code.

## Setup

1. Clone the repo: `git clone <repo-url>`
2. Open the folder in Claude Code
3. `CLAUDE.md` is picked up automatically — no manual steps required
4. Start asking questions

---

## Tool selection guide

Claude Code has access to multiple search tools. Use them as follows:

| Tool | Best for | When to use |
|------|----------|-------------|
| **Perplexity** | Verified citations, named researchers, academic paper content | Research questions needing reliable sources with author attribution |
| **WebSearch** | Broad academic sweep, peer-reviewed paper discovery | Finding multiple academic perspectives across domains |
| **Claude** | Reasoning, analysis, synthesis, structured output | Working with content *already verified* by the above tools |

> **Ground rule for all learners:** Use Perplexity or BrightData to find facts. Bring verified results to Claude to reason about them. Never ask Claude to generate sources from memory.

---

## Context and scale management (Principle 6)

Before executing any task involving multiple files, large documents, or broad research:

### The checklist
1. **Count and size** — run `ls -lh` before reading any files
2. **Estimate fit** — files >50KB individually or >150KB total risk mid-task compaction
3. **Choose the right architecture**:
   - Single agent: tasks under ~150KB total
   - Parallel map-reduce: tasks over ~150KB total (one subagent per document, synthesise after)
4. **Flag compaction risk upfront** — if a single-agent pass is likely lossy, say so before starting

### Thresholds

| Condition | Action |
|-----------|--------|
| Single file >50KB | Flag before reading; ask whether full read is needed |
| Total across task >150KB | Recommend parallel subagents |
| Compaction detected mid-task | Disclose clearly; do not present partial summary as complete |

### Teaching this to users
Coach users to include scale-awareness instructions in their prompts:
- Specify file sizes when asking about document sets
- Request parallel processing for large tasks
- Ask agents to flag when they cannot fully read source material

---

## Validating factual claims

For any question involving specific dates, legislation, statistics, named research, or current events:
- Use Perplexity or WebSearch *before* answering
- Do not answer from memory alone — confident-and-wrong reinforces skipping verification
- If you catch yourself thinking "I know this" about a specific fact, that is the trigger to search, not to answer
