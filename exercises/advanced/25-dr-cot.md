## Exercise 25: DR-CoT (Dynamic Recursive Chain of Thought)

### Theoretical background

DR-CoT addresses two weaknesses of standard Chain-of-Thought for long or complex reasoning tasks: (1) context dilution — important early reasoning gets "forgotten" as the chain grows long, and (2) high token costs. DR-CoT combines three mechanisms: recursive sub-problem decomposition, dynamic context pruning (keeping only essential content within a fixed token budget per step), and multi-path voting to verify the final answer.

**Evidence:** Consistently 3-4 percentage points higher than standard CoT on AIME 2024 (mathematics competition). On GPQA Diamond, small BERT-class models using DR-CoT outperformed GPT-4 and LLaMA 2 on zero-shot basis.
**Source:** [Scientific Reports / Nature, Vol. 15, 2025](https://www.nature.com/articles/s41598-025-18622-6).

For executives, DR-CoT is most relevant for: complex financial modelling analysis, multi-step scenario planning, long regulatory or contract analysis, or any task where reasoning chains span many intermediate steps and accuracy is critical.

### Student task

Select a problem requiring more than 4-5 reasoning steps where accuracy at each step affects later conclusions (compound reasoning). Write a DR-CoT prompt specifying: sub-problem decomposition, a token/length budget per step, two independent solution paths, and reconciliation of those paths before giving the final answer.

### Examples

**Problem:** Evaluate whether a 5-year managed services contract at current terms generates positive NPV given projected cost inflation.

**Standard CoT prompt:**
"Calculate the NPV of a 5-year managed services contract. Revenue: €500K/year. Costs grow at 8%/year. Discount rate: 10%. Starting cost base: €300K."

**AI response:** Often produces correct Year 1, then compounds errors across years due to context dilution of the base figure.

**DR-CoT prompt:**
```
Evaluate the NPV of the following managed services contract. Follow these rules:

Rules:
- Decompose into annual sub-calculations (Year 1 through Year 5).
- At each year, reference only the immediately prior year's output
  (do not carry forward the full calculation chain).
- Limit each year's working to the essential figures only
  (token budget: max 3 lines per year).
- Solve twice using two independent methods:
  Path A: Year-by-year cumulative.
  Path B: Closed-form PV formula.
- If results match within 5%, present as confirmed answer.
  If they diverge, flag the discrepancy and show both.

Contract details:
- Revenue: €500K/year (fixed)
- Cost base Year 1: €300K, growing 8%/year
- Discount rate: 10%
- Contract length: 5 years
```

**AI response (DR-CoT):**

*Year 1:* Revenue €500K, Cost €300K, Margin €200K. PV = €200K / 1.10 = €181,818
*Year 2:* Cost €324K, Margin €176K. PV = €176K / 1.21 = €145,455
*Year 3:* Cost €349.9K, Margin €150.1K. PV = €150.1K / 1.331 = €112,772
*Year 4:* Cost €377.9K, Margin €122.1K. PV = €122.1K / 1.464 = €83,402
*Year 5:* Cost €408.1K, Margin €91.9K. PV = €91.9K / 1.611 = €57,047

*Path A total NPV: €580,494*

*Path B (formula verification):* [closed-form calculation] = €578,900

*Variance: €1,594 (0.27%) — within 5% threshold.*
**Confirmed NPV: ~€580K. Contract generates positive returns. Recommend proceed.**

### Gotchas

DR-CoT requires you to specify the token budget and independent paths clearly — vague instructions produce standard CoT without the pruning benefit. The two-path verification is the most important element: if paths diverge by more than your threshold, that is a signal to investigate which assumption is wrong before trusting the answer. Do not use DR-CoT for simple calculations where standard arithmetic suffices; reserve it for multi-step compound reasoning where intermediate error propagation is a real risk.

### Key takeaways

DR-CoT is the most technically rigorous prompting technique in this guide. It imports from software engineering (modular, stateless computation with verification) into language model reasoning. For executives who use AI for financial analysis, scenario modelling, or complex contract evaluation, DR-CoT provides a structured audit trail and built-in error detection. The two-path verification step alone — asking AI to confirm its answer via an independent method — should become standard practice for any high-stakes numerical output.

---
