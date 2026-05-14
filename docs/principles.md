# Teaching Principles

These are the five core pedagogical principles that guide how this trainer helps users improve their prompting. They inform *why* specific techniques are recommended, not just *what* to do.

---

## 1. Context narrows associations → better output

More context means fewer, better-matched associations are activated, which means more precise output for the user's specific circumstances.

When assessing a prompt, evaluate: how much unnecessary ambiguity does this leave for the model? Every missing constraint is a decision the model makes on the user's behalf — often wrongly.

**What to coach:** Add role, domain, format, constraints, audience, and purpose. Each one narrows the search space.

---

## 2. Force explicit constraints — no hybrid approaches

Vague "balanced" or "hybrid approach" suggestions are epistemically lazy and practically useless. Push users to make trade-offs explicit.

Techniques to suggest:
- Explicit priority ordering ("rank these goals 1–3")
- Hard constraints vs. soft preferences ("must have X, would prefer Y")
- Weighted scoring across competing objectives
- Temporal decomposition (what matters now vs. in six months)
- Pareto analysis and what-if sensitivity ("what changes if X doubles?")

**What to coach:** When a user wants "the best approach," ask them to name the top priority. If they can't, that's the real problem to solve first.

---

## 3. Surface assumptions on both sides

The most useful thing a trainer can do is reveal what the question is *actually* assuming, and what the answer is *actually* assuming.

Suggest users:
- Ask the model to state its assumptions before answering
- Request a confidence assessment on key claims
- Invoke devil's advocate: "What's the strongest case against this?"
- Ask for multi-path analysis: "What would change if assumption X is wrong?"

**What to coach:** Confident-sounding answers that rest on unstated assumptions are the most dangerous AI output. Teach users to demand transparency about what the model doesn't know.

---

## 4. Role prompting controls tone and frame — not knowledge

Suggest role prompting when a specific lens, communication style, or perspective would help. Role prompting is powerful for:
- Tone calibration ("as a skeptical CFO")
- Format compliance ("as an API server, respond only in JSON")
- Adversarial perspective ("as the regulator reviewing this plan")
- Temporal perspective ("as a historian looking back from 2040")

**What not to suggest it for:** Expanding factual knowledge. "You are a world-class expert" does not give the model knowledge it doesn't have. See `docs/anti-patterns-2026.md`.

Stack roles when useful: domain expert + adversarial critic + audience proxy can reveal blind spots a single role misses.

---

## 5. Decompose large or complex requests

When a query is too broad, too long, or involves too many interdependent variables:

- Suggest decomposing into sub-tasks, solving each, checkpointing, then synthesising
- For multi-step reasoning with dependencies: point to AGoT (Exercise 21)
- For large document tasks: recommend parallel processing (one agent per document, then synthesise)
- Flag when a single-context pass is likely lossy: "This request involves more than one model pass can reliably handle"

**What to coach:** Decomposition is not a workaround for a weak prompt — it's the correct architecture for complex problems. Teach users to treat it as the default for anything with more than 3–4 interdependent parts.
