## Exercise 20: Sales target generation

### Theoretical background

Sales target generation with AI demonstrates how specific business problems benefit from combining domain knowledge with AI's computational and analytical capabilities. Effective sales targets aren't arbitrary numbers—they derive from historical performance, capacity constraints, market conditions, and strategic goals. AI can synthesize these factors into coherent, achievable targets when prompted with sufficient context.

This exercise teaches the broader skill of translating business problems into structured AI prompts with relevant variables, constraints, and desired output formats.

### Student task

Present AI with a realistic sales target scenario including: current performance metrics, team composition, capacity constraints, growth goals, and any relevant market factors. Ask AI to generate specific, actionable targets broken down by relevant dimensions (time period, team member, activity metrics, etc.). Evaluate whether the generated targets are mathematically coherent, strategically sound, and practically achievable.

### Examples

**Prompt:**
"Generate Q4 sales targets for our business considering these factors:
- Current MRR: $45K
- Sales team: 3 reps (1 senior, 2 junior)
- Average deal size: $2,400 annual contracts
- Sales cycle: 45 days average
- Growth goal: 40% MRR increase by end of Q4
- Junior reps are ramping (hired 2 months ago)
- Senior rep closing at 25% rate, 20 qualified opportunities per month
- Junior reps closing at 15% rate, 12 qualified opportunities per month currently

Break down by rep, month, and include activity metrics needed to hit targets."

**AI response:**

**Q4 Growth Target Analysis:**
Current MRR: $45,000
Target MRR (40% growth): $63,000
Required new MRR: $18,000
Required new annual contracts: $18K × 12 = $216,000
Number of deals needed: $216K / $2,400 = 90 new customers

**Key constraint:** 45-day sales cycle means October pipeline must close by mid-November, and November pipeline by end-December. September pipeline is already set.

**Team capacity-adjusted targets:**

**Senior Rep (Sarah):**
- Current capacity: 20 opps/month × 25% close rate = 5 deals/month
- Q4 target: 5 deals × 3 months = 15 deals = $36,000 annual value = $3,000 MRR

**Junior Rep 1 (James):**
- Current capacity: 12 opps/month × 15% close rate = 1.8 deals/month
- Expected ramp: Month 3-4 of tenure, increasing to 15 opps/month, 18% close rate by December
- Q4 target: 2 + 2 + 3 deals = 7 deals = $16,800 annual value = $1,400 MRR

**Junior Rep 2 (Maria):**
- Current capacity: 12 opps/month × 15% close rate = 1.8 deals/month
- Expected ramp: Similar to James
- Q4 target: 2 + 2 + 3 deals = 7 deals = $16,800 annual value = $1,400 MRR

**Total team capacity: 29 deals = $69,600 annual value = $5,800 new MRR**

**Analysis: Your 40% growth target ($18K new MRR) is not achievable with current team capacity ($5,800 new MRR)**

**Revised realistic target: 15% MRR growth = $6,750 new MRR**

**Activity metrics required (working backwards from targets):**

| Rep | Monthly Deals | Required Opps | Required Qualified Leads | SDR Support Needed |
|-----|---------------|---------------|--------------------------|---------------------|
| Sarah | 5 | 20 (at 25% close) | 40 (at 50% qualification) | 40 leads/month |
| James | 2→3 | 12→15 | 24→30 | 25→30 leads/month |
| Maria | 2→3 | 12→15 | 24→30 | 25→30 leads/month |

**Total: 85-95 qualified leads required per month**

**Monthly targets breakdown:**

**October:**
- Sarah: 5 deals ($3K MRR)
- James: 2 deals ($400 MRR)
- Maria: 2 deals ($400 MRR)
- **Month total: 9 deals, $3,800 MRR**

**November:**
- Sarah: 5 deals ($3K MRR)
- James: 2 deals ($400 MRR)
- Maria: 2 deals ($400 MRR)
- **Month total: 9 deals, $3,800 MRR**

**December:**
- Sarah: 5 deals ($3K MRR)
- James: 3 deals ($600 MRR)
- Maria: 3 deals ($600 MRR)
- **Month total: 11 deals, $4,200 MRR**

**Q4 Total: 29 deals, $11,800 MRR gain → Ending MRR: $56,800 (26% growth)**

**Recommendations:**
1. **Reset expectations:** 40% quarterly growth with 3 reps (2 ramping) is unrealistic. Communicate 25-30% as ambitious but achievable.
2. **Lead generation bottleneck:** You need 85-95 qualified leads/month. Do you have SDR/marketing capacity for this? If not, reps will miss targets despite skill.
3. **Junior rep support:** Implement structured onboarding/coaching plan. Their ramp determines Q4 success.
4. **Alternative to hit 40% target:** Hire 4th rep immediately (will only contribute in December) OR increase average deal size to $3,000+ through packaging changes OR shorten sales cycle to 30 days through process improvements.

Which of these is most realistic for your business?"

[Detailed, realistic, mathematically coherent, identifies constraints, offers alternatives]

### Gotchas

AI can produce mathematically consistent targets that are strategically nonsensical if you don't provide sufficient business context. Verify that the underlying assumptions (close rates, ramp timelines, capacity estimates) match your reality, not generic benchmarks. AI may not account for seasonality, market conditions, or internal factors you haven't explicitly mentioned.

Sales targets are ultimately judgment calls. Use AI to structure analysis and test scenarios, not as a substitute for leadership decision-making.

### Key takeaways

Sales target generation demonstrates how AI excels at structured analytical problems when given clear inputs, constraints, and desired outputs. The technique teaches you to decompose complex business problems into variables AI can manipulate. This analytical structuring skill applies broadly across business planning tasks.
