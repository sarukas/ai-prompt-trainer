## Exercise 23: Prompt Repetition

### Theoretical background

Prompt Repetition is the simplest advanced technique discovered in 2025: paste your question twice in the same prompt (`<question><question>`). Decoder-only language models process text sequentially. When the model reaches the second instance of the question, it has already fully processed the first — creating a pseudo-bidirectional context effect that reduces the chance of missing key details in complex queries.

**Evidence:** Up to 76% accuracy improvement on non-reasoning tasks in tests by Google Research.
**Source:** [arXiv:2512.14982](https://arxiv.org/abs/2512.14982), December 2025, Google Research.

**Important caveat:** Prompt repetition doubles input tokens, which doubles cost on token-based APIs. Use only for short, precise, high-importance tasks — not for long document analysis or RAG-based queries where context is already large.

### Student task

Select a precise, high-stakes question where getting all the nuance right matters — a strategic question, a decision brief, a risk identification task. Test it with and without repetition. Observe whether the repeated version catches subtleties the single version missed.

### Examples

**Single question (standard):**
"What are the key risks in acquiring a professional services firm with 40% revenue concentration in one client?"

**With Prompt Repetition:**
```
What are the key risks in acquiring a professional services firm with
40% revenue concentration in one client?

What are the key risks in acquiring a professional services firm with
40% revenue concentration in one client?
```

**Observed difference:** Single-question response typically covers: client loss risk, valuation impact, earn-out structure. Repeated version additionally surfaced: key-person dependency (the relationship owner for that client), restrictive covenant limitations, and the due diligence signal that 40% concentration implies failed business development — a structural problem, not just a client risk.

**Executive use case — precision document review:**
```
Review the following contract clause and identify any terms that could create
liability exposure for us as the service provider:

[clause text]

Review the following contract clause and identify any terms that could create
liability exposure for us as the service provider:

[clause text]
```

The repetition increases the probability the model identifies subtle or embedded liabilities that a single pass might deprioritise in favour of obvious ones.

### Gotchas

Do not use for long document analysis, RAG pipelines, or any prompt where context already exceeds 2,000 tokens — the cost doubles without proportional benefit. This technique works best for short, focused, high-precision queries. Also note: this applies to non-reasoning models (GPT-4o, Claude 3.5 Sonnet). For reasoning models (o3, Claude Extended Thinking), the internal multi-pass reasoning already achieves a similar effect.

### Key takeaways

Prompt repetition is the lowest-effort high-return technique in this guide. It requires no structural change to your thinking or prompt design — just paste twice. For executives who send important queries once and trust the answer, adding a single repetition is a near-zero-cost accuracy upgrade on precision tasks.

---
