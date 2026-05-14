## Exercise 10: Few-shot prompting

### Theoretical background

Few-shot prompting teaches AI through examples rather than explicit instructions. This technique leverages the model's ability to recognize patterns and generalize from demonstrations. Research in machine learning shows that 3-5 well-chosen examples can establish complex patterns more effectively than lengthy written instructions, especially for tasks involving specific formats, styles, or domain-specific conventions.

The technique is particularly powerful when you need consistent output formatting (like JSON structures), specific tones, or domain-specific responses. It works because transformer models excel at pattern completion—they're fundamentally prediction engines that continue patterns they recognize.

### Student task

Identify a task where you need AI to produce output in a specific format or style. First, try describing the format in words alone. Then, try the same task using few-shot prompting with 3-5 examples. Compare the accuracy and consistency of outputs. Experiment with edge cases to see if the few-shot approach generalizes beyond your examples.

Try this with at least two different task types: one structural (format-based) and one stylistic (tone-based).

### Examples

**Task 1: Extract structured data from unstructured text**

**Instruction-only prompt:**
"Extract the person's name, age, location, and profession from the text into JSON format."

**Input:** "Hi, I'm Sarah, a 34-year-old graphic designer living in Portland."

**Output (inconsistent):**
```json
{
  "person": "Sarah",
  "age": "34 years old",
  "location": "Portland",
  "job": "graphic designer"
}
```
[Issues: inconsistent key names, redundant "years old" in age value]

**Few-shot prompt:**
"Extract information into JSON format. Examples:

Input: 'My name is John, I'm 28, and I work as a teacher in Boston.'
Output:
```json
{"name": "John", "age": 28, "location": "Boston", "profession": "teacher"}
```

Input: 'I'm Maria, 45 years old, engineer from Seattle.'
Output:
```json
{"name": "Maria", "age": 45, "location": "Seattle", "profession": "engineer"}
```

Now process: 'Hi, I'm Sarah, a 34-year-old graphic designer living in Portland.'"

**Output (consistent):**
```json
{"name": "Sarah", "age": 34, "location": "Portland", "profession": "graphic designer"}
```
[Correct: consistent keys, proper integer type for age, clean formatting]

**Task 2: Match a specific communication tone**

**Instruction-only prompt:**
"Respond to customer complaints in a professional but warm tone that acknowledges their frustration without over-apologizing."

**Few-shot prompt:**
"Respond to customer complaints in this style:

Example 1:
Customer: 'Your app crashed and I lost my data!'
Response: 'That sounds incredibly frustrating, especially losing your work. Let's get this sorted out. Could you share what you were working on when the crash happened? We'll help you recover what we can and ensure this doesn't happen again.'

Example 2:
Customer: 'I've been waiting 3 days for support!'
Response: 'Three days is too long to wait—I understand why you're upset. You're speaking with me now and I'm here to help. Let's tackle your issue right away. What's been going on?'

Now respond to: 'Your service is terrible and I want a refund!'"

**Output:**
"I hear your disappointment with the service. Let's make sure we address what went wrong—can you tell me what specific issues you encountered? Once I understand the situation, I'll work with you on a solution that makes this right, whether that's resolving the issue or discussing refund options."

[Matches tone: acknowledges emotion, shows agency, focuses on solutions, no excessive apologizing]

### Gotchas

Few-shot examples must be high-quality and representative of the full range of inputs you expect. If your examples are too similar, the AI may not generalize to edge cases. If they're inconsistent with each other, the AI won't know which pattern to follow.

More examples isn't always better—beyond 5-7 examples, you hit diminishing returns and may confuse the model. Choose diverse, well-crafted examples over quantity.

### Key takeaways

Few-shot prompting is often more efficient than lengthy instructions for format-specific tasks. It's especially valuable when you can't articulate the rules clearly in words but can demonstrate them through examples. This technique teaches you to think in terms of demonstrations rather than descriptions.
