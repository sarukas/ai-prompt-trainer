## Exercise 12: Reverse prompting

### Theoretical background

Reverse prompting inverts the typical human-asks-AI-answers dynamic by explicitly encouraging AI to ask clarifying questions before responding. This technique addresses a fundamental limitation: AI often proceeds with whatever information you provide, filling gaps with assumptions that may not match your actual context or needs.

By instructing "ask me any questions you need before answering," you force yourself to articulate requirements you might not have realized were relevant. This surfaces implicit assumptions, edge cases, and contextual factors that dramatically improve response quality. The technique is especially valuable for complex, ambiguous, or high-stakes requests.

### Student task

Identify a complex question or request where the "right" answer depends heavily on context you haven't specified. Ask AI to respond to your question directly without reverse prompting. Then, ask the same question but add: "Before answering, ask me any clarifying questions you need to provide the best response." Compare the quality and relevance of both answers. Count how many of the AI's clarifying questions you hadn't considered initially.

### Examples

**Initial question:** "What's the best programming language for my project?"

**Direct response (without reverse prompting):**
"Python is a great general-purpose choice for most projects due to its readability, extensive libraries, and active community. It's particularly strong for data science, web development, and scripting tasks. JavaScript is essential for web applications. Consider Go or Rust for high-performance systems."
[Generic advice that may not match user's actual needs]

**Reverse prompting response:**
"Before I can recommend a programming language, I need to understand your project better. Could you help me with these questions?

1. **Project domain:** What type of application are you building? (web app, mobile app, data pipeline, embedded system, game, etc.)
2. **Performance requirements:** Are there specific latency, throughput, or resource constraints?
3. **Team context:** How many developers? What languages do they already know?
4. **Existing ecosystem:** Are you integrating with existing systems? If so, what technologies do they use?
5. **Timeline and maturity needs:** Is this a prototype, MVP, or production-critical system? What's your timeline?
6. **Scale expectations:** How many users/requests do you expect? Any specific scaling concerns?
7. **Deployment environment:** Cloud, on-premise, edge devices, mobile devices?
8. **Long-term maintenance:** Will this be actively developed for years, or is it a short-term project?

The 'best' language depends entirely on these factors. For example, my recommendation changes dramatically if you're building a real-time embedded control system versus a CRUD web application for internal company use."

**Follow-up example with answers:**
User: "Web-based B2B SaaS dashboard for data visualization. Team of 2 full-stack developers who know JavaScript. Need to launch MVP in 3 months. Expect 50-200 enterprise users. Standard cloud deployment. Plan to actively develop for 3+ years."

AI: "Given that context, I recommend:
- **Frontend:** React or Vue.js (JavaScript frameworks your team already knows)
- **Backend:** Node.js with TypeScript (leverages team's JavaScript expertise, reduces context-switching, TypeScript adds safety for long-term maintainability)
- **Data viz:** D3.js or Chart.js (mature JavaScript visualization libraries)

This stack minimizes learning curve, maximizes iteration speed for your 3-month MVP timeline, and keeps your small team in one primary language ecosystem. The TypeScript addition provides gradual typing that improves long-term code quality without blocking initial velocity.

Alternatives to consider later: If you hit significant performance bottlenecks (unlikely with 200 users), consider moving heavy data processing to Python or Go microservices while keeping the JavaScript core."
[Highly specific, contextualized recommendation based on clarifying questions]

### Gotchas

Not all AI models will generate clarifying questions even when explicitly instructed—some are trained to be more assertive and direct. You may need to iterate on your reverse prompting instruction: "I want you to ask at least 5 questions before answering" can be more effective.

AI may ask questions you can't answer, revealing gaps in your own problem definition. This is actually valuable but can be frustrating if you expected a quick answer.

### Key takeaways

Reverse prompting forces you to be a better problem-framer. The questions AI asks often reveal dimensions of the problem you hadn't consciously considered. This technique is essential for high-stakes decisions where assumptions can be costly. It transforms AI from answer-provider to thought partner in problem clarification.
