# Prompting Techniques Library (Research-Backed)

> Load this file when teaching or recommending specific techniques.
> Reference: `docs/techniques-library.md`

## Core Techniques — High Evidence

| Technique                            | When to Use                                       | 2026 Nuance                                                           | Source               |
| ------------------------------------ | ------------------------------------------------- | --------------------------------------------------------------------- | -------------------- |
| Zero-shot CoT ("Think step by step") | Complex reasoning on non-reasoning models         | ⚠️ Redundant on o3/Claude Extended Thinking — adds latency only       | Wei et al. 2022      |
| Closed-context prompting             | Any task where hallucination is a risk            | Still essential — most important for exec use                         | ODU Survey 2025      |
| Self-consistency                     | High-stakes decisions; ask for 3+ reasoning paths | Use CISC (weighted) for efficiency                                    | Wang et al. 2022     |
| Role + Constraint prompting          | Specialist framing needed                         | ⚠️ Role ≠ knowledge expansion; useful for tone/format/compliance only | Prompt Report 2024   |
| Few-shot (2-3 examples max)          | Format or style-matching tasks                    | ⚠️ >5 examples confirmed counterproductive ("Few-Shot Collapse")      | Chen et al. 2023     |
| Tree of Thought (ToT)                | Creative, strategic, multi-path problems          | Still effective                                                       | Yao et al. 2024      |
| Step-back prompting                  | Domain-knowledge questions needing context        | Still effective                                                       | Google Research 2023 |
| Reverse prompting                    | Ambiguous or complex requests                     | Still effective                                                       | White et al. 2023    |

## Advanced Techniques — 2025–2026 (Verified with Citations)

| Technique                                   | When to Use                                                        | Evidence                                              | Source                                                            |
| ------------------------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------- | ----------------------------------------------------------------- |
| Adaptive Graph of Thoughts (AGoT)           | Complex multi-dependency problems; surpasses CoT/ToT on hard tasks | +46.2% on GPQA Diamond with GPT-4o                    | [arXiv:2502.05078](https://arxiv.org/abs/2502.05078)              |
| Confidence-Informed Self-Consistency (CISC) | High-accuracy needs; reduces compute vs. standard self-consistency | 53% compute reduction, equal/better accuracy          | [arXiv:2502.06233](https://arxiv.org/abs/2502.06233)              |
| Prompt Repetition                           | Short, precise tasks — paste the prompt twice                      | Up to 76% accuracy improvement on non-reasoning tasks | [arXiv:2512.14982](https://arxiv.org/abs/2512.14982)              |
| Adversarial Chain-of-Thought                | Iterative prompt self-improvement via generator/discriminator loop | Avg +4.44% across 12 reasoning datasets               | [MDPI Dec 2025](https://www.mdpi.com/2078-2489/16/12/1092)        |
| DR-CoT (Dynamic Recursive CoT)              | Long reasoning chains needing token efficiency                     | Outperforms GPT-4 on GPQA with small models           | [Nature 2025](https://www.nature.com/articles/s41598-025-18622-6) |

## Techniques Now Less Effective in 2026 ⚠️

* **"Think step by step" on reasoning models** (o3, Claude Extended Thinking) — internal CoT already built in; explicit instruction redundant, adds 20-80% latency

* **Role prompting for knowledge expansion** — confirmed not to expand knowledge boundaries; retain only for tone, format, and compliance control

* **>5 few-shot examples** — "Few-Shot Collapse" confirmed across multiple models; 2-3 examples maximum

* **Complex scaffolding on frontier models** (GPT-5, Claude Opus class) — "Prompting Inversion": elaborate constraints hinder autonomous reasoning

* **Emotional manipulation phrases** ("please", "I'll tip you", "I'll be fired") — no measurable effect on modern frontier models
