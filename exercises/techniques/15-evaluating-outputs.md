## Exercise 15: Reading and evaluating outputs

### Theoretical background

This exercise develops the critical skill of AI output evaluation. Research in machine learning shows that "looking at your data"—carefully examining model outputs rather than just metrics—reveals insights about model behavior, training artifacts, and failure modes. The same principle applies to prompt engineering: close reading of AI outputs teaches you how the model interprets your prompts and where it struggles.

The technique involves treating AI output as a diagnostic signal about the prompt's effectiveness, not just an end product. Errors are particularly valuable because they reveal the gap between your intended meaning and AI's interpretation. Developing this evaluative skill prevents blind trust in AI outputs and enables rapid iteration.

### Student task

Generate 10 AI responses for a consistent task (same type of question or request repeated with different inputs). Read each response carefully, not just for accuracy but for patterns. Document: where does AI consistently succeed? Where does it struggle? What types of errors occur? Are there surprising interpretations of your prompt? What do the failure patterns reveal about the model's understanding?

Use these insights to revise your prompt and test again.

### Examples

**Task:** "Summarize this research paper abstract into one accessible sentence for a general audience."

**10 test cases (abstracts from different fields):**
1. Neuroscience paper → Output quality: Good
2. Quantum computing paper → Output quality: Confusing jargon remained
3. Sociology paper → Output quality: Good
4. Marine biology paper → Output quality: Excellent
5. Theoretical physics paper → Output quality: Oversimplified to inaccuracy
6. Economics paper → Output quality: Good but removed important nuance
7. Computer science paper → Output quality: Good
8. Climate science paper → Output quality: Excellent
9. Philosophy paper → Output quality: Missed key logical distinction
10. Genetics paper → Output quality: Good

**Pattern analysis:**
- **Success pattern:** Papers with concrete examples (marine biology, climate science) produced best summaries
- **Failure pattern #1:** Highly theoretical papers (quantum computing, physics) retained unexplained jargon OR oversimplified to incorrectness when trying to avoid jargon
- **Failure pattern #2:** Papers with subtle distinctions (philosophy, economics) lost important nuances in compression
- **Interpretation insight:** AI struggles with the trade-off between accessibility and accuracy for abstract theoretical content
- **Surprising insight:** The word "accessible" in the prompt isn't specific enough—accessible to whom? High school student vs. educated non-specialist makes a big difference.

**Revised prompt based on evaluation:**
"Summarize this research paper abstract into one sentence for an educated reader with no background in this specific field (assume bachelor's degree level). If the research is highly theoretical, use an analogy. If important nuances would be lost in compression, keep the sentence slightly longer to preserve accuracy. Avoid unexplained jargon."

**Retest on previous failures:**
- Quantum computing → Improved: "This research develops error-correction techniques for quantum computers by creating 'backup copies' of quantum information, similar to how RAID systems protect data on regular hard drives." [Analogy works]
- Theoretical physics → Improved: "The study proposes a mathematical framework unifying two previously incompatible theories about how space and time behave at extremely small scales." [Preserves accuracy without oversimplifying]
- Philosophy → Improved: "The paper argues that moral responsibility requires not just free choice but also proper understanding of consequences—a distinction that matters for evaluating impulsive versus deliberate actions." [Preserves key distinction]

### Gotchas

Evaluating outputs is time-intensive and may not be justified for low-stakes tasks. Focus this technique on high-stakes or repeated-use prompts. You may develop biases in your evaluation, seeing patterns that aren't there or preferring outputs that match your existing beliefs regardless of objective quality.

Pattern recognition requires enough samples—evaluating 2-3 outputs isn't sufficient to identify true patterns versus random variation.

### Key takeaways

Close reading of AI outputs is the fastest way to improve prompt quality. Errors are learning opportunities that reveal how your language is interpreted. This evaluative skill distinguishes prompt users from prompt engineers—users accept outputs at face value, engineers use outputs as feedback to improve inputs.
