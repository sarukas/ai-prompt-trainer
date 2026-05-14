## Exercise 14: Designing for edge cases

### Theoretical background

Edge case design addresses a fundamental challenge in AI interactions: how should the system behave when inputs are unexpected, ambiguous, or incomplete? Traditional software engineering emphasizes edge case handling ("outs") to ensure reliability. The same principle applies to prompt engineering. By explicitly instructing AI on what to do when uncertain or when inputs don't match expectations, you improve both reliability and diagnostic value.

This technique teaches defensive prompting—anticipating failure modes and designing graceful handling rather than assuming perfect inputs. It's particularly valuable in production workflows where you're processing many inputs and need consistent, auditable behavior.

### Student task

Design a prompt for a task that processes varied inputs (e.g., extracting information from text, categorizing items, answering questions). First, test it with normal cases. Then, deliberately test edge cases: ambiguous inputs, missing information, contradictory data, or out-of-scope requests. Notice where it fails. Revise your prompt to explicitly handle these edge cases, instructing AI to output specific signals (like `<unsure>` tags or "N/A" values) when it encounters problems. Compare reliability before and after edge case design.

### Examples

**Task:** Extract company name, funding amount, and funding stage from news snippets.

**Initial prompt:**
"Extract company name, funding amount, and funding stage from the text into JSON."

**Test case 1 (normal):**
Input: "Acme Corp raised $12M in Series A funding."
Output: `{"company": "Acme Corp", "amount": "$12M", "stage": "Series A"}`
[Works correctly]

**Test case 2 (edge case—missing amount):**
Input: "Acme Corp announced Series B funding."
Output: `{"company": "Acme Corp", "amount": "undisclosed", "stage": "Series B"}`
[AI invented "undisclosed" without instruction—problematic for data analysis]

**Test case 3 (edge case—ambiguous stage):**
Input: "Acme Corp raised $12M in late-stage funding."
Output: `{"company": "Acme Corp", "amount": "$12M", "stage": "late-stage"}`
[Inconsistent terminology, hard to analyze]

**Test case 4 (edge case—non-funding text):**
Input: "Acme Corp announced a new product launch."
Output: `{"company": "Acme Corp", "amount": "N/A", "stage": "N/A"}`
[Acceptable, but should signal that this isn't a funding announcement]

**Revised prompt with edge case design:**
"Extract company name, funding amount, and funding stage from text into JSON format.

Rules for edge cases:
- If funding amount is not stated, use: null (not 'undisclosed' or any invented value)
- If funding stage is ambiguous or uses non-standard terminology, include it exactly as stated and add 'ambiguous': true
- If the text doesn't describe a funding event, output: {'type': 'not_funding', 'company': [company name if present, else null]}
- If you cannot confidently extract any value, output: {'error': 'insufficient_information'}

Examples:
Input: 'StartupX raised $5M in seed funding.'
Output: {'company': 'StartupX', 'amount': '$5M', 'stage': 'seed', 'ambiguous': false}

Input: 'StartupY completed a significant fundraise.'
Output: {'company': 'StartupY', 'amount': null, 'stage': 'not specified', 'ambiguous': true}"

**Retesting edge cases with revised prompt:**

Test case 2: `{"company": "Acme Corp", "amount": null, "stage": "Series B", "ambiguous": false}`
[Correctly uses null instead of inventing data]

Test case 3: `{"company": "Acme Corp", "amount": "$12M", "stage": "late-stage", "ambiguous": true}`
[Preserves original terminology and flags ambiguity]

Test case 4: `{"type": "not_funding", "company": "Acme Corp"}`
[Correctly identifies non-funding text]

### Gotchas

Over-specifying edge cases can create overly complex prompts that are hard to maintain. Focus on the most common and impactful edge cases. AI may not perfectly follow edge case instructions—test thoroughly with real data. You may discover new edge cases you didn't anticipate, requiring prompt updates.

Edge case handling instructions add prompt length, which can affect performance or cost in API-based scenarios. Balance thoroughness with practicality.

### Key takeaways

Designing for edge cases transforms brittle prompts into robust ones suitable for production workflows. The process of identifying potential failure modes improves your understanding of the task itself. This technique is essential when AI outputs feed into downstream processes where bad data has consequences.
