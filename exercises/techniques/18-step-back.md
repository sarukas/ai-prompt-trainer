## Exercise 18: Step-back prompting

### Theoretical background

Step-back prompting is a technique that improves AI responses by first asking a broader, more general question before addressing the specific query. This activates the model's background knowledge and contextual understanding, which then informs a more insightful response to the specific question. The technique leverages how human expertise works: experts don't just know facts; they understand underlying principles and context.

Research shows that asking AI to establish general principles before applying them to specific cases significantly improves reasoning quality, especially on questions requiring domain knowledge, nuanced understanding, or application of theory to practice.

### Student task

Select a specific, detailed question in a domain where general knowledge matters (science, history, strategy, etc.). First, ask AI the specific question directly. Then, use step-back prompting: ask a broader, related question first, then provide that answer as context for your specific question. Compare the depth and quality of responses.

Try this across 2-3 different domains to see where the technique adds most value.

### Examples

**Specific question:** "Why did the Byzantine Empire survive for nearly 1,000 years after the fall of the Western Roman Empire?"

**Direct response:**
"The Byzantine Empire survived due to several factors: strategic location of Constantinople controlling trade routes, strong defensive fortifications, effective diplomacy, flexible military tactics, and preservation of Roman administrative systems. The capital's walls and geography made it nearly impregnable, and Byzantine emperors skillfully played rivals against each other."
[Accurate but somewhat superficial listing of factors]

**Step-back prompting approach:**

**Step 1—Broader question:**
"What are the fundamental factors that determine whether empires survive long-term versus collapse?"

**AI response to broader question:**
"Empire longevity depends on several interdependent factors:

1. **Economic sustainability:** Can the empire generate sufficient resources to fund defense, administration, and infrastructure without depleting its economic base?

2. **Adaptive governance:** Does the political system adapt to changing circumstances, or is it rigid? Successful long-term empires typically balance continuity with flexibility.

3. **Geographic defensibility:** Are borders naturally defensible (mountains, water) or do they require constant expensive military presence?

4. **Legitimacy and identity:** Does the population accept the state's authority through shared identity, religious/ideological commitment, or effective service delivery?

5. **External threat management:** Can the empire diplomatically isolate threats, form strategic alliances, or maintain military superiority without economically exhausting itself?

6. **Elite cohesion vs. fragmentation:** Internal power struggles drain resources and create vulnerabilities; cohesive elites extend empire survival.

7. **Technological/tactical innovation:** Empires that stagnate militarily or administratively become vulnerable to more adaptive competitors.

These factors interact—economic strength enables military defense, which provides security for economic activity. Collapse often occurs when multiple factors deteriorate simultaneously."

**Step 2—Specific question with context:**
"Now, given these fundamental factors of empire longevity, explain why the Byzantine Empire survived nearly 1,000 years after the Western Roman Empire fell."

**Enhanced response:**
"The Byzantine Empire's millennium-long survival maps remarkably well onto the empire longevity factors:

**Economic sustainability:** Constantinople's position controlling Black Sea-Mediterranean trade routes generated immense customs revenue without requiring exploitative taxation of agricultural regions. Unlike the Western Empire, which depended on costly overland supply lines, Byzantium leveraged maritime trade economics.

**Adaptive governance:** The Byzantine system evolved significantly from Roman precedent—incorporating Greek as the administrative language, developing the theme system (military districts with local recruitment), and eventually accepting iconoclasm controversies through councils rather than civil war. This flexibility contrasts with the Western Empire's rigid adherence to increasingly dysfunctional Roman practices.

**Geographic defensibility:** Constantinople's position (sea on three sides, walls on the fourth) meant the empire could survive even when most territory was lost. The Western Empire had indefensible frontiers requiring constant expensive military presence across the Rhine and Danube.

**Legitimacy and identity:** Byzantine emperors cultivated religious legitimacy (crowned by the Patriarch) and Roman imperial continuity simultaneously. Orthodox Christianity provided ideological cohesion the fragmented West lacked. The concept of 'symphony' between church and state created powerful mutual reinforcement.

**External threat management:** Byzantine diplomacy was legendary—subsidizing steppe peoples to attack each other, forming strategic marriages, exploiting rival Islamic caliphates' conflicts. The Western Empire's less sophisticated diplomacy couldn't prevent coalition-building among barbarian groups.

**Elite cohesion:** While Byzantium had palace intrigues, the centralized bureaucracy and capital city prevented the territorial fragmentation that destroyed the West, where regional warlords became independent.

**Innovation:** Greek fire (naval weapon), heavy cataphract cavalry, sophisticated fortification engineering—Byzantium continually adapted militarily. The Western Empire's late-period armies were essentially Germanic mercenaries with Roman branding.

The key insight: Byzantium succeeded by focusing defensive resources on a highly defensible core (Constantinople and Anatolia) with self-sustaining economics, rather than trying to defend the entire Mediterranean periphery as the Western Empire attempted. When multiple factors aligned negatively (Fourth Crusade's sack of Constantinople, Ottoman technological superiority in siege warfare, loss of Anatolian themes), the empire finally collapsed."

[Much deeper analysis connecting specific factors to general principles, revealing causal mechanisms not just correlations]

### Gotchas

Step-back prompting doubles interaction length (two questions instead of one), which may not be justified for simple queries. The broader question must actually be relevant—a poorly chosen step-back question doesn't help and may even confuse the AI. You need domain awareness to formulate good step-back questions.

Some topics don't benefit from this approach—purely factual questions ("When was X invented?") don't need principle-based context.

### Key takeaways

Step-back prompting transforms AI from fact-retrieval mode into principle-application mode, significantly improving reasoning depth. The technique teaches you to think about the general principles underlying specific situations. This metacognitive habit—asking "what general principle applies here?"—is valuable far beyond AI interactions.
