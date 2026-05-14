## Exercise 17: Tree of thought prompting

### Theoretical background

Tree of thought (ToT) prompting is an advanced technique that encourages AI to explore multiple reasoning paths simultaneously, like a chess player considering several possible move sequences. Unlike linear chain-of-thought reasoning (A→B→C), ToT explores branching possibilities (A→B₁/B₂/B₃) and evaluates which paths are most promising before proceeding.

This technique is particularly powerful for creative problems with no single correct answer, strategic planning with multiple viable approaches, and complex decisions where different assumptions lead to different conclusions. Research shows ToT can significantly improve problem-solving on tasks requiring exploration of solution spaces.

### Student task

Select a problem with multiple valid approaches or creative interpretations (design challenge, strategic decision, open-ended brainstorming). Ask AI to solve it using ToT prompting: "Explore at least three different approaches to this problem. For each approach, identify the key assumptions, potential benefits, and likely challenges. Then recommend which approach to pursue and why."

Compare this to a single-path solution. Note whether the exploration of alternatives reveals insights even in the approaches not ultimately chosen.

### Examples

**Problem:** "Design an employee recognition program for a 50-person software company with limited budget ($5,000/year)."

**Linear approach (single path):**
"Create a monthly 'Employee of the Month' program where nominated winners receive a $100 gift card and recognition in company all-hands. This is a proven, simple approach that fits the budget."
[Functional but unexplored]

**Tree of thought approach:**

"Let me explore three different program philosophies:

**Approach 1: Peer-driven micro-recognition**
- **Philosophy:** Many small recognitions are more impactful than few large ones
- **Implementation:** Give each employee $8/month in recognition tokens they can give to colleagues with written appreciation. Tokens convert to gift cards quarterly.
- **Assumptions:** Employees value peer recognition; frequent small acknowledgments build culture better than rare formal awards
- **Benefits:** High participation, culture of mutual appreciation, visible daily reinforcement
- **Challenges:** Requires platform/system; risk of popularity contests rather than merit-based recognition
- **Budget:** $8 × 50 employees × 12 months = $4,800 + $200 platform cost = $5,000

**Approach 2: Skill development rewards**
- **Philosophy:** Best recognition is investment in employee growth
- **Implementation:** Quarterly recognition awards where winners choose from: conference attendance, course stipend, certification exam, or professional book allowance
- **Assumptions:** Employees value growth opportunities; recognition should have lasting impact beyond momentary validation
- **Benefits:** Tangible skill development; employees customize reward to their goals; company benefits from upskilling
- **Challenges:** Quarterly frequency means fewer people recognized; administrative overhead for conference logistics
- **Budget:** ~$500 per winner × 2-3 winners per quarter = $4,000-$6,000, requires budget flexibility

**Approach 3: Impact-based project completion bonuses**
- **Philosophy:** Recognize specific achievements tied to company goals, not personality or likability
- **Implementation:** Teams nominate completed projects that delivered measurable value (shipped feature, cost saving, customer satisfaction improvement). Nominated projects reviewed quarterly, winning teams split $1,000 recognition bonus.
- **Assumptions:** Team recognition is more valuable than individual; tying recognition to concrete impact focuses culture on results
- **Benefits:** Reinforces outcome orientation; team-based reduces politics; clear criteria
- **Challenges:** May favor customer-facing roles over infrastructure/support; quarterly review lag means recognition isn't timely
- **Budget:** $1,000 × 4 quarters = $4,000 + $1,000 for runner-up/honorable mentions = $5,000

**Recommendation:**
Start with Approach 1 (peer-driven micro-recognition) because:
1. Highest participation—every employee engages monthly, not just award winners
2. Culture-building is the primary value, not the gift card amount
3. Real-time recognition (within days) is more psychologically impactful than quarterly awards
4. Low administrative overhead once system is set up

However, blend in element from Approach 3: annually (end of year), dedicate $1,000 to a 'Project of the Year' team award voted on by the company. This addresses the limitation that peer micro-recognition might miss quieter but highly impactful work.

This hybrid approach uses $4,800 + $200 platform = $5,000, maximizes participation, provides both frequent and significant recognition moments, and builds appreciation culture while rewarding concrete impact."

[Multiple perspectives explored, assumptions made explicit, hybrid solution synthesized]

### Gotchas

ToT responses are much longer than linear responses, which may not be justified for simple problems. The technique can lead to "analysis paralysis" where exploration of options delays decision-making. AI may not genuinely evaluate trade-offs; instead, it might generate three variations that are superficially different but conceptually similar.

Explicitly instruct AI to explore genuinely different approaches (not just variations on a theme) to get maximum value from ToT.

### Key takeaways

ToT prompting forces systematic exploration of solution spaces, revealing both obvious and non-obvious approaches. The value often lies in the divergent thinking during exploration, not just the final recommendation. This technique teaches you to consider problems from multiple frameworks before converging on a solution—a valuable meta-cognitive skill beyond AI use.
