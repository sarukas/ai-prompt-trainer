# Techniques to Avoid in 2026

> Reference: `docs/anti-patterns-2026.md`  
> Last updated: April 2026. Sources verified via Perplexity, WebSearch, and BrightData.

This appendix documents prompting approaches that were effective on earlier AI models (2022-2024) but have been confirmed less effective or counterproductive on current frontier models (GPT-4o, Claude 3.5/3.7, Gemini Advanced and above). Knowing what *not* to do is as important as knowing what works.

### 1. "Think step by step" on Reasoning Models

**What it is:** Explicitly instructing CoT on models that already reason internally (OpenAI o3/o4-mini, Claude Extended Thinking, Gemini Thinking).

**Why it's now ineffective:** These models perform multi-step reasoning by default. Adding explicit CoT instruction is redundant and increases response time by 20-80% with no accuracy gain.

**Source:** [arXiv:2506.07142](https://arxiv.org/abs/2506.07142), Wharton Generative AI Labs, June 2025.

**Correct approach:** State clearly what result you want. Let reasoning models reason. Reserve explicit CoT for non-reasoning models (GPT-4o, Claude 3.5 Sonnet without Extended Thinking enabled).

---

### 2. Role Prompting for Knowledge Expansion

**What it is:** "You are a world-class expert with 20 years of experience in X" — used to get more accurate or deeper factual information.

**Why it's now ineffective:** Confirmed not to expand knowledge boundaries. The model knows what it knows regardless of persona. Worse, role prompting can amplify biases associated with that persona archetype.

**Source:** [arXiv:2409.13979](https://arxiv.org/html/2409.13979v2), updated February 2025.

**Still effective for:** Tone control, output format compliance, communication style. "Review this briefly like a grumpy senior engineer" or "Respond only in JSON format as an API server" remain valid uses.

---

### 3. More Than 5 Few-Shot Examples

**What it is:** Providing 6, 8, or 10 examples to ensure the model understands the pattern.

**Why it's now counterproductive:** "Few-Shot Collapse" confirmed — performance drops sharply beyond 4-5 examples. Models overfit to the demonstrated patterns and lose generalisation. Gemini Flash on path optimisation: 0-shot 33% → 4-shot 64% → 8-shot back to 33%.

**Source:** [arXiv:2509.13196](https://arxiv.org/abs/2509.13196), September 2025.

**Correct approach:** 2-3 high-quality, diverse examples. Examples are for format and pattern demonstration, not for teaching the model what it already knows.

---

### 4. Complex Scaffolding on Frontier Models

**What it is:** Elaborate step-by-step instruction sequences ("First do X, then Y, then Z, then review, then...") applied to GPT-5 or Claude Opus-class models.

**Why it's now counterproductive:** "Prompting Inversion" phenomenon — complex constraints force excessive literal interpretation on high-capability models, blocking autonomous reasoning. GPT-5 Zero-Shot already exceeds the best GPT-4o prompted results on major benchmarks.

**Source:** [arXiv:2510.22251](https://arxiv.org/abs/2510.22251), October 2025.

**Correct approach:** For frontier models, state clearly what you want as the outcome. For GPT-4o-level models, structured scaffolding still helps. Know which model you are using and calibrate accordingly.

---

### 5. Emotional Manipulation Phrases

**What it is:** "I'll give you a $200 tip," "I'll get fired if you don't help," "This is critical for my career," "Please, I'm begging you."

**Why it's now ineffective:** Confirmed no consistent measurable effect on modern frontier models. Early EmotionPrompt research (2023) showed gains on older, smaller models; these do not replicate on current frontier systems.

**Source:** Wharton GAIL Prompting Science Report 2, 2025; Medium "Magic Phrases Don't Work," January 2026.

**Correct approach:** Provide specific context — data scale, current problem, target metrics, environment. "Our orders table has 5M rows, query takes 5 seconds, target is under 500ms on PostgreSQL 15" outperforms any emotional appeal by orders of magnitude.

---

*Last updated: April 2026. Sources verified via Perplexity, WebSearch, and BrightData cross-reference.*
