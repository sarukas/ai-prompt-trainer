## Exercise 11: Role prompting

### Theoretical background

Role prompting instructs AI to adopt a specific persona, profession, or perspective, which triggers the model to draw on associated knowledge patterns and communication styles from its training data. When you say "act as a senior software architect," the model activates text patterns associated with that role—technical depth, systems thinking, trade-off analysis, and professional communication norms.

This technique is cognitively powerful because it provides implicit context without requiring exhaustive explicit instructions. A role carries bundled assumptions about expertise, values, communication style, and problem-solving approaches. Research shows role prompting can significantly improve response quality in specialized domains.

### Student task

Select a technical or professional problem from your work or studies. Ask AI to solve it three times, each time adopting a different professional role: (1) without any role specification, (2) as a practitioner in the field, and (3) as a critic or skeptic of the field. Compare the depth, perspective, and usefulness of each response.

Reflect on how the role shapes not just what information is provided but how it's framed and what's emphasized.

### Examples

**Problem:** "Should our startup build our product using microservices architecture?"

**Without role:**
"Microservices offer benefits like scalability and independent deployment but add complexity. Consider your team size and requirements when deciding."
[Generic, non-actionable advice]

**As senior software architect:**
"At your current stage—pre-Series A with 4 engineers—microservices would be architectural overengineering that slows you to a crawl. Here's why:

1. **Operational overhead:** You'll spend engineering time on service mesh configuration, distributed tracing, inter-service authentication, and API versioning instead of building features. Your team lacks the 10-15 engineers minimum to sustain microservices effectively.

2. **Premature optimization:** You haven't validated product-market fit. You need iteration speed, not hypothetical scale. A well-structured monolith with clear module boundaries gives you 90% of microservices benefits with 10% of the operational cost.

3. **The path forward:** Build a modular monolith now. Use clear interface boundaries between domains. When you reach 50K active users or Series B funding (whichever comes first), extract the 2-3 modules that actually need independent scaling into microservices.

This is the pragmatic path that lets you ship fast today while preserving migration options for tomorrow."
[Specific, contextualized, actionable—draws on real-world startup experience patterns]

**As microservices skeptic:**
"Microservices are organizational theater masquerading as technical architecture. The dirty secret is that most companies adopt microservices to solve people problems—team coordination failures—and wrongly believe technical architecture can fix cultural dysfunction.

Your real question isn't 'should we use microservices?' but 'why are we even asking this question?' If you're asking before you've hit the scaling limits of a monolith, you're cargo-culting Netflix's architecture without Netflix's problems.

Consider that Shopify, Basecamp, and StackOverflow run massive-scale businesses on monoliths or monolith-adjacent architectures. They chose developer productivity and operational simplicity over architectural buzzwords. You should too, unless you can articulate a specific technical constraint that only microservices solve—and I bet you can't."
[Provocative, challenges premise, pattern-interrupts assumption that microservices are default-correct]

### Gotchas

AI role-playing isn't perfect emulation of how a real person in that role would respond. It's pattern-matched behavior based on text the model was trained on. Treat responses as "in the style of" rather than authentic representation. Some roles (therapist, lawyer, doctor) may trigger safety restrictions where AI refuses or provides disclaimers.

Overly specific roles ("act as Steve Jobs in 2007") may produce caricature responses focused on well-known personality traits rather than substantive expertise.

### Key takeaways

Role prompting is a powerful shortcut for accessing specialized perspectives without writing extensive context. The technique teaches you to think about implicit knowledge and values associated with different professional identities. Combining role prompting with other techniques (like few-shot or CoT) creates sophisticated prompt engineering.
