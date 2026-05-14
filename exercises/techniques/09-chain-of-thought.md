## Exercise 9: Chain of thought prompting

### Theoretical background

Chain of thought (CoT) prompting is a breakthrough technique that dramatically improves AI reasoning, particularly for STEM, logic, and multi-step problems. The method works by explicitly instructing the model to show its reasoning process step-by-step, which forces the model to engage in more deliberate processing rather than pattern-matching to surface-level answers.

Research shows CoT prompting can improve accuracy on complex reasoning tasks by 20-40%. The technique leverages the model's training on human-written explanatory text where people naturally show their work. By requesting this format, you activate more sophisticated reasoning pathways within the model.

### Student task

Select a complex reasoning problem from mathematics, logic, or multi-step analysis. First, ask AI to solve it directly without any CoT prompt. Note the answer. Then, ask the same question with an explicit CoT instruction: "Let's think through this step-by-step..." or "Please show your reasoning process before providing the final answer." Compare the quality, accuracy, and usefulness of both responses.

Try this with at least three different problem types to see where CoT provides most value.

### Examples

**Problem 1: Mathematical reasoning**
"A farmer has 17 sheep. All but 9 die. How many sheep are left?"

**Without CoT:**
AI: "8 sheep remain."
[Incorrect—this is pattern-matching to subtraction]

**With CoT:**
"Let's think through this step-by-step:
1. The farmer starts with 17 sheep
2. The phrase 'all but 9 die' means that 9 sheep did NOT die
3. If 9 sheep did not die, then 9 sheep are still alive
4. The number of sheep that died is 17 - 9 = 8, but the question asks how many are LEFT (alive)
5. Answer: 9 sheep remain alive."
[Correct]

**Problem 2: Logic puzzle**
"Three switches outside a room control three bulbs inside. You can flip switches but can only enter the room once. How do you determine which switch controls which bulb?"

**Without CoT:**
"Flip switches, enter room, observe which bulbs are on."
[Incomplete—misses the constraint]

**With CoT:**
"Let's work through this systematically:
1. Constraint: Only one entry means we can't use trial-and-error testing
2. Insight: Light bulbs produce heat when on, providing a second observable signal beyond light
3. Strategy:
   - Turn on switch 1, wait 5 minutes, turn it off
   - Turn on switch 2
   - Leave switch 3 off
   - Enter room
4. Observation decode:
   - Bulb that's on: controlled by switch 2
   - Bulb that's off but warm: controlled by switch 1
   - Bulb that's off and cool: controlled by switch 3
5. This solves the puzzle in one entry."
[Correct and complete]

**Problem 3: Multi-step analysis**
"A company's revenue increased 50% from Year 1 to Year 2, then decreased 50% from Year 2 to Year 3. What's the net change from Year 1 to Year 3?"

**Without CoT:**
"No change—the increases and decreases cancel out."
[Incorrect—common misconception]

**With CoT:**
"Let's calculate step-by-step with concrete numbers:
1. Assume Year 1 revenue = $100
2. Year 2 = $100 + 50% = $100 × 1.5 = $150
3. Year 3 = $150 - 50% = $150 × 0.5 = $75
4. Net change = $75 - $100 = -$25
5. Percentage change = -25/100 = -25%
6. Result: Revenue decreased by 25% overall, not zero. The percentage changes don't cancel because they apply to different base values."
[Correct]

### Gotchas

CoT doesn't magically fix all reasoning errors—it reduces them but doesn't eliminate them. The AI might show step-by-step reasoning that looks correct but contains subtle flaws. You still need to verify the logic yourself. CoT also increases response length, which may not be desirable for simple questions.

Some models are trained with CoT capabilities built-in and may show reasoning steps even without explicit prompting. The technique is most impactful with models that tend toward terse, direct answers.

### Key takeaways

CoT prompting transforms AI from a answer-generator into a reasoning-partner. The visible reasoning process lets you audit the AI's logic, catch errors early, and understand why it reaches specific conclusions. This technique is essential for any high-stakes reasoning task where accuracy matters more than speed.
