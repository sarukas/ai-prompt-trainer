## Exercise 22: Confidence-Informed Self-Consistency

### Theoretical background

Standard Self-Consistency (Wang et al. 2022) asks AI to generate multiple reasoning paths and takes the majority answer. Confidence-Informed Self-Consistency (CISC) improves this by asking the model to also rate its confidence in each path, then applying weighted voting — high-confidence paths count more.

**Evidence:** CISC achieves up to 53% reduction in compute cost compared to standard self-consistency while matching or exceeding accuracy, validated across 9 models and 4 datasets.
**Source:** [arXiv:2502.06233](https://arxiv.org/abs/2502.06233), ACL 2025 Findings.

For executive use, CISC is the gold standard for high-stakes decisions where you need both multiple perspectives AND a clear ranked recommendation — not just majority vote, but confidence-weighted synthesis.

### Student task

Take a high-stakes decision you are currently facing (investment, hire, strategic pivot). Write a CISC prompt requesting 3-5 distinct reasoning paths, confidence scores for each, and a final conclusion weighted by confidence. Compare to asking for a single answer on the same question.

### Examples

**Standard single-answer prompt:**
"Should we renew our enterprise software contract at the new price (40% increase) or switch vendors?"

**AI response:** Balanced pros/cons. No clear recommendation. Hedged.

**CISC prompt:**
```
We are evaluating whether to renew our CRM contract (Salesforce, 40% price
increase to €180K/year) or migrate to HubSpot (€95K/year, 6-month migration
estimated). Current team: 12 sales reps, 3 years of historical data.

Generate 4 different reasoning paths analysing this decision.
For each path:
- State the core assumption or lens used (e.g. financial, risk, productivity)
- Reach a clear conclusion (renew / migrate)
- Rate your confidence in this path's conclusion: 0-100
- Briefly explain the confidence rating

Then provide a final weighted recommendation, giving more weight to
higher-confidence paths. Flag any path where confidence is below 50 and explain why.
```

**AI response:**

*Path 1 — Financial lens:* Migration saves €85K/year. Payback on migration cost (estimated €40K) in under 6 months. **Conclusion: Migrate. Confidence: 75.** Well-established cost analysis; uncertainty around migration timeline accuracy.

*Path 2 — Risk/disruption lens:* 6-month migration disrupts Q3 sales cycle. Historical data migration carries 15% risk of CRM data loss without specialist support. **Conclusion: Renew. Confidence: 60.** Disruption cost is real but hard to quantify precisely.

*Path 3 — Productivity lens:* HubSpot's interface shows higher rep adoption in comparable firms; Salesforce has low voluntary usage in your team size range. **Conclusion: Migrate. Confidence: 55.** Productivity gains are real but team-specific; your reps may differ.

*Path 4 — Strategic lock-in lens:* Salesforce's ecosystem integrations with your ERP are deep; switching costs compound over time. **Conclusion: Renew. Confidence: 80.** Integration dependency is a hard constraint, not a soft preference.

**Weighted final recommendation:** Renew — but negotiate. Paths 1 and 4 have highest combined confidence (75 + 80 = 155 vs 60 + 55 = 115 for migrate paths). Financial savings are real but Path 4's lock-in risk is the deciding factor. Recommended action: Use migration option as negotiating leverage to reduce increase from 40% to 15-20%.

### Gotchas

AI confidence scores are not calibrated probabilities — they reflect the model's internal consistency, not real-world accuracy. Treat them as relative weights, not absolute reliability metrics. If all four paths return confidence below 60, that is itself a signal: the decision has genuine uncertainty that AI cannot resolve; you need additional data before deciding.

### Key takeaways

CISC gives you something single-answer prompts never can: a transparent view of which reasoning holds up most robustly and which depends on uncertain assumptions. For executives, this mirrors the way good management consultants structure options analysis — multiple perspectives, explicit assumptions, ranked confidence. The technique also surfaces when a decision is genuinely too uncertain to make without more information.

---
