## Exercise 24: Adversarial Chain-of-Thought

### Theoretical background

Adversarial Chain-of-Thought (Adv-CoT) embeds a prompt improvement loop within a single prompt: a generator proposes reasoning, a discriminator identifies failure cases, and revisions are made iteratively — all in one AI interaction. Rather than you iterating on the prompt manually across sessions, the model does it internally.

**Evidence:** Average +4.44% accuracy improvement across 12 reasoning datasets with GPT-3.5-turbo; improvements on sports reasoning (+4.5%), arithmetic (+3.7%), and algebraic reasoning (+3.9%). Low variance across repeated runs confirms stable gains.
**Source:** [MDPI Information, December 2025](https://www.mdpi.com/2078-2489/16/12/1092).

For executives, Adv-CoT is most valuable for refining prompts you plan to reuse — sales qualification criteria, document review checklists, decision frameworks. Run it once to improve the prompt, then use the improved version repeatedly.

### Student task

Identify a prompt you use regularly but feel produces inconsistent or incomplete results. Write an Adv-CoT meta-prompt asking the model to: (1) identify 3 failure cases in the original prompt, (2) revise the prompt to address each, (3) generate a response with the improved prompt, (4) explain what improved. Compare original and improved outputs.

### Examples

**Original prompt (used repeatedly, produces variable results):**
"Review this proposal and tell me if it's ready to send to the client."

**Adv-CoT improvement prompt:**
```
I have this prompt I use to review client proposals:
"Review this proposal and tell me if it's ready to send to the client."

Please do the following:
1. Identify 3 specific failure cases — situations where this prompt would
   produce incomplete, misleading, or unhelpful responses.
2. Rewrite the prompt to prevent each failure case.
3. Show me what a response to the improved prompt looks like, applied to
   a hypothetical proposal for a €200K AI training engagement.
4. Explain concisely how the improved version is better.
```

**AI output:**

*Failure case 1:* "Ready to send" is undefined. The model has no criteria — it will default to surface-level grammar/formatting checks and miss strategic or commercial gaps.

*Failure case 2:* No client context provided. A proposal for a risk-averse public sector client requires different readiness criteria than one for a startup CEO.

*Failure case 3:* No reviewer perspective specified. The model doesn't know if it should review as a senior partner, a client procurement officer, or a legal reviewer.

*Improved prompt:*
```
Review the following client proposal against these specific criteria:
1. Executive summary: Does it state the problem, solution, and value in under 150 words?
2. Commercial clarity: Is pricing justified with clear ROI or reference to benchmarks?
3. Risk mitigation: Are client concerns (timeline, delivery risk, dependencies) addressed?
4. Call to action: Is the next step clear and time-bound?
5. Tone calibration: Is the language appropriate for [client type: e.g. CFO of a mid-cap manufacturer]?

Flag any section that would cause a senior client stakeholder to hesitate or ask a clarifying question before signing.
```

*Sample output on improved prompt:* [Detailed section-by-section review against criteria, with specific line-level flags.]

### Gotchas

Adv-CoT produces longer outputs and works best when your original prompt is specific enough to have identifiable failure modes. If your original prompt is too vague ("make this better"), the model cannot identify meaningful failure cases. Start with a prompt you already use in practice, not a hypothetical one. The improved prompt from Adv-CoT should be saved and used going forward — the value compounds when the better prompt becomes your standard.

### Key takeaways

Adv-CoT turns prompt improvement from a manual trial-and-error process into a structured, single-session exercise. For executives who use AI for recurring tasks (proposal review, meeting prep, decision briefs), running Adv-CoT once on your standard prompts and saving the result is one of the highest-leverage investments of AI prompting time. The improved prompts become institutional assets.

---
