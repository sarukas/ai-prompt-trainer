# AI Prompt Trainer

A stand-alone coaching workspace that turns Claude (or any capable AI) into a dedicated prompting trainer: it answers your question first, then gives you targeted, concise feedback on how that specific prompt could have been sharper.

## What's inside

```
├── CLAUDE.md                          # Trainer behavior instructions (system prompt)
│
├── docs/
│   ├── principles.md                  # 5 teaching principles behind the trainer
│   ├── techniques-library.md          # Research-backed techniques with 2026 nuances and citations
│   └── anti-patterns-2026.md         # What not to do on modern frontier models
│
├── exercises/
│   ├── 00-learning-path.md            # Curriculum map — start here
│   ├── foundations/                   # Exercises 1–8: AI as a thinking partner
│   ├── techniques/                    # Exercises 9–18: Core prompting methods
│   └── advanced/                      # Exercises 19–25: 2025–2026 frontier techniques
│
└── deployment/
    ├── claude-code.md                 # Claude Code (full tool support, recommended)
    ├── claude-ai.md                   # Claude.ai Projects
    ├── api.md                         # Anthropic API
    └── custom-gpt.md                  # OpenAI Custom GPT
```

---

## Quick start

### Claude Code (recommended)
```bash
git clone <repo-url>
# Open the folder in Claude Code — CLAUDE.md loads automatically
# Start asking questions
```

### Claude.ai
See `deployment/claude-ai.md` — copy the adapted system prompt into a Project.

### Anthropic API
See `deployment/api.md` — pass `CLAUDE.md` as the system prompt with prompt caching.

### Custom GPT
See `deployment/custom-gpt.md` — paste the adapted instructions and upload the docs as knowledge files.

---

## Where to start learning

Open `exercises/00-learning-path.md` for the full curriculum with difficulty ratings (⭐–⭐⭐⭐⭐⭐), time estimates, prerequisites, and suggested paths.

**Quick-start paths:**

| Goal | Path |
|------|------|
| New to prompting | Exercises 1 → 4 → 9 → 12 → 13 |
| Daily AI user wanting more precision | Exercises 13 → 15 → 17 → 18 → 22 |
| High-stakes decisions with AI | Exercises 19 → 21 → 22 → 25 |
| One quick win right now | Exercise 23 — Prompt Repetition (20 min, no prerequisites) |

Before starting any path, read `docs/anti-patterns-2026.md` — knowing what *not* to do on modern models saves significant time.

---

## Techniques covered

**Core (2022–2024):** Zero-shot CoT · Few-shot · Role prompting · Reverse prompting · Tree of Thought · Step-back prompting · Self-consistency · Closed-context prompting

**Frontier (2025–2026):** Adaptive Graph of Thoughts (AGoT) · Confidence-Informed Self-Consistency (CISC) · Prompt Repetition · Adversarial CoT · DR-CoT

**Superseded:** Techniques confirmed ineffective or counterproductive on GPT-4o+, Claude 3.5+, and equivalent frontier models

All techniques are evidence-backed with citations. See `docs/techniques-library.md`.

---

## Philosophy

> More context → fewer, better associations → more precise output for your circumstances.

The best prompts don't just ask questions — they constrain, prioritise, and give the model the right lens to see your problem clearly. This workspace teaches you to do exactly that.

---

## Contributing

To add a new exercise, follow the structure of any existing exercise file:

```markdown
## Exercise N: Title

### Theoretical background
### Student task
### Examples
### Gotchas
### Key takeaways
```

Place it in the appropriate tier folder (`foundations/`, `techniques/`, or `advanced/`), add it to `exercises/00-learning-path.md`, and update the techniques library if it covers a new technique.
