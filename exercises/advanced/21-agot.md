## Exercise 21: Adaptive Graph of Thoughts

### Theoretical background

Adaptive Graph of Thoughts (AGoT) is the 2025 evolution beyond Chain-of-Thought (linear: A→B→C) and Tree of Thought (branching: A→B₁/B₂/B₃). AGoT structures reasoning as a Directed Acyclic Graph (DAG) — it decomposes a complex problem into interdependent sub-problems, solves them in dependency order, and synthesises results. Crucially, it only expands sub-problems that are actually needed, reducing wasted reasoning.

**Evidence:** With GPT-4o, AGoT achieved +46.2% improvement on the GPQA Diamond scientific reasoning benchmark and +400% on the "Game of 24" math puzzle compared to standard prompting.
**Source:** [arXiv:2502.05078](https://arxiv.org/abs/2502.05078), February 2025.

AGoT is most powerful for problems with genuine dependencies — where solving Part B requires the output of Part A, and Part C requires both. In executive contexts: complex project planning, multi-variable strategic decisions, M&A analysis, regulatory risk mapping.

### Student task

Identify a complex problem with clear interdependencies — at least 3-4 sub-problems where solving later ones requires outputs from earlier ones. Write a prompt that explicitly instructs the model to: (1) decompose into sub-problems, (2) specify dependencies, (3) solve in dependency order referencing earlier results, (4) synthesise into a final answer. Compare to a single direct question on the same problem.

### Examples

**Problem:** Planning a major service line expansion for a professional services firm.

**Standard prompt:**
"Should we expand our AI consulting practice into Germany?"

**AI response:** Generic pros/cons list. No dependency structure. Misses that the financial viability question depends on market demand, which depends on competitive landscape, which depends on your differentiation.

**AGoT prompt:**
```
We are a 50-person AI consulting firm based in London, €8M revenue,
considering expanding into Germany. Please solve this using the following approach:

1. Break the decision into independent sub-problems (e.g. market demand,
   competitive landscape, regulatory requirements, financial viability,
   talent acquisition).
2. Specify which sub-problems depend on the outputs of others.
3. Solve each sub-problem sequentially, referencing prior results where needed.
4. Synthesise a final go/no-go recommendation with clear reasoning.
```

**AI response structure (AGoT):**

*Sub-problem 1: Regulatory and market entry requirements* (no dependencies)
→ Germany requires GDPR plus specific BaFin considerations for financial sector clients. Establishes baseline compliance cost of ~€80-120K setup.

*Sub-problem 2: Competitive landscape* (no dependencies)
→ Dominated by Big 4 and Accenture in enterprise; mid-market gap exists for specialist AI firms. Key differentiator needed: industry vertical or model expertise.

*Sub-problem 3: Market demand* (depends on Sub-problem 2)
→ Given mid-market gap identified above: 340+ German mid-cap firms actively investing in AI with no specialist advisor. Estimated addressable market €45M annually at current maturity.

*Sub-problem 4: Financial viability* (depends on Sub-problems 1 and 3)
→ Given €100K compliance setup and €45M addressable market: break-even at 2.2% market share (€1M revenue), achievable in 18 months based on London ramp pattern.

*Sub-problem 5: Talent acquisition* (depends on Sub-problem 4)
→ Given 18-month timeline and Berlin talent pool: hire 2 senior consultants locally before expansion; pipeline exists.

**Final synthesis:** Go — conditional on securing one anchor client before committing to office lease. Recommend 6-month pilot with remote delivery first.

### Gotchas

Poorly specified dependencies produce shallow results — AI may list sub-problems that are all independent and miss the actual causal chain. Spend time identifying real dependencies before writing the prompt. AGoT is overkill for simple decisions; reserve it for genuinely complex, multi-variable problems with stakeholder presentations or board-level consequences.

### Key takeaways

AGoT transforms AI from answer-machine into structured analyst. By making dependencies explicit, you catch logical gaps that linear reasoning misses. For senior leaders, this technique maps directly to how strategic consultants structure complex engagement analyses — and you can now do it in minutes rather than weeks.

---
