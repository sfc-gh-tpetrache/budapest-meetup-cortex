# Aqua Serenity Spas: Competitive Intelligence POC
## Presentation Script (10 minutes)

---

## Opening (1 min)

**[Address Andras's pain point]**

> "Andras, you told me: *'I want to know exactly why customers prefer our competitors and what we need to fix. Stop guessing - show me the data.'*"

Today I'll show you how we can answer that question in seconds, not weeks.

**What I built:** A competitive intelligence system using Snowflake Intelligence that lets anyone on our team ask questions in plain English and get instant, auditable answers.

---

## Demo 1: Competitive Benchmarking (2 min)

**[Andras's question]**

**Ask:** "How do our ratings compare to the top 5 competitors?"

**Show:**
- Our average: 4.0 vs Szechenyi's 4.5
- The 0.4-0.5 star gap we need to close
- SQL generated for Peter's audit trail

**Talking point:**
> "We're not guessing anymore. This pulls from 250 reviews across 35 Budapest spas. Every answer shows the SQL so Peter can verify the numbers."

---

## Demo 2: Location Performance (2 min)

**[Andras's question]**

**Ask:** "Which of our locations is underperforming and why?"

**Show:**
- Rating breakdown by location
- Specific complaint themes per location
- Comparison to competitors in same district/price tier

**Talking point:**
> "Instead of waiting for monthly reports, you can drill into any location instantly. The system searches actual review text to find the 'why' behind the numbers."

---

## Demo 3: Sentiment Analysis (2 min)

**[Peter's operational question]**

**Ask:** "What are the top 3 complaints at each of our locations?"

**Show:**
- Specific complaint categories (wait times, cleanliness, staff, facilities)
- Actual review quotes as evidence
- Actionable recommendations

**Talking point:**
> "Peter, this is what you asked for - not just 'we have problems' but WHICH location has WHICH problem. You can use this to prioritize training and improvements."

---

## Demo 4: Market Opportunity (2 min)

**[Eva's growth question]**

**Ask:** "Which districts have no premium spas? That's our opportunity."

**Show:**
- District heatmap of spa concentration
- Gaps in premium/luxury tier by area
- Competitor vulnerability analysis

**Talking point:**
> "Eva, you wanted to find the gap in the market. This shows where customers are underserved - exactly where we should consider opening location #6."

---

## Closing: Auditability (1 min)

**[Address Peter's trust requirement]**

> "Peter, you said: *'If we make decisions based on wrong numbers, we waste money and frustrate customers. Any AI needs to be explainable and auditable.'*"

**Show:**
- Click to reveal SQL behind any answer
- Source data is traceable to specific reviews
- No black box - full transparency

**Key point:**
> "Every insight is backed by SQL you can run yourself. Trust but verify."

---

## Summary

| Stakeholder | Question | Answer Time |
|-------------|----------|-------------|
| Andras (CEO) | "How do we compare to competitors?" | < 10 seconds |
| Peter (Ops) | "What complaints need fixing?" | < 10 seconds |
| Eva (CMO) | "Where should we expand?" | < 10 seconds |

**Success criteria met:**
- Speed: Instant answers
- Accuracy: SQL-backed, verifiable
- Simplicity: Plain English, no SQL needed
- Trust: Full audit trail
- Actionable: Specific recommendations

---

## Next Steps

1. **Immediate:** Share with analyst team for testing
2. **Day 3:** Gather feedback on additional questions
3. **Day 5:** Decision on production implementation with real TripAdvisor data feeds

**Questions?**

---

## Appendix: Sample Questions to Demo

**CEO (Andras):**
- "How do our ratings compare to the top 5 competitors?"
- "Which of our locations is underperforming and why?"
- "What would it take to reach a 4.5 average rating?"

**CMO (Eva):**
- "Which districts have no premium spas?"
- "What do reviews mention that we're not doing?"

**Operations (Peter):**
- "What are the top 3 complaints at each of our locations?"
- "Which treatments should we add based on competitor success?"
- "How are we doing compared to Szechenyi Baths?"

**Follow-up:**
- "Where should we open our 4th spa?"
- "What do 5-star reviews mention?"
