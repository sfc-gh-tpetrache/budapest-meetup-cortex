# Pon.Bike: Competitive Intelligence POC
## Presentation Script (10 minutes)

---

## Opening (1 min)

**[Address Janus's pain point]**

> "Janus, you told me: *'We own 9 brands but I can't tell you in 10 seconds which ones are winning and which ones need help.'*"

Today I'll show you how we can answer that question in seconds, not weeks.

**What I built:** A competitive intelligence system using Snowflake Intelligence that lets anyone on our team ask questions in plain English and get instant, auditable answers about our brand portfolio performance in the Dutch market.

---

## Demo 1: Competitive Benchmarking (2 min)

**[Janus's question]**

**Ask:** "How do our brand ratings compare to Trek and Specialized?"

**Show:**
- Pon brands average vs Trek (4.3) and Specialized (4.3)
- The rating gap we need to close per brand
- SQL generated for Pieter's audit trail

**Talking point:**
> "We're not guessing anymore. This pulls from 250 product reviews across 25 bicycle brands. Every answer shows the SQL so Pieter can verify the numbers."

---

## Demo 2: Brand Performance (2 min)

**[Janus's question]**

**Ask:** "Which of our brands is underperforming in the Dutch market?"

**Show:**
- Rating breakdown by Pon brand
- Market share trends for each brand
- Comparison to competitors in same price tier and category

**Talking point:**
> "Instead of waiting for quarterly reports, you can drill into any brand instantly. The system shows both the numbers and the customer feedback behind them."

---

## Demo 3: Product Review Analysis (2 min)

**[Pieter's product question]**

**Ask:** "What are the top complaints about our e-bikes?"

**Show:**
- Specific complaint categories (battery range, motor noise, component quality, dealer service)
- Actual review quotes as evidence
- Comparison to what Trek and Specialized e-bike reviews praise

**Talking point:**
> "Pieter, this is what you asked for - not just 'ratings are low' but WHICH brand has WHICH problem. Is it the motor, the frame, the components, or the dealer experience? You can use this to prioritize R&D investments."

---

## Demo 4: Category Gap Analysis (2 min)

**[Marieke's growth question]**

**Ask:** "Which bike category has no strong Pon brand?"

**Show:**
- Category-level market share for Pon brands vs competitors
- Growing categories (gravel, speed pedelec) where Pon is underrepresented
- Competitor vulnerability analysis

**Talking point:**
> "Marieke, you said: *'Every brand should own a category. If there's a category where we don't have a strong contender, that's either an acquisition target or a brand repositioning opportunity.'* This shows exactly where those gaps are."

---

## Closing: Auditability (1 min)

**[Address Pieter's trust requirement]**

> "Pieter, you said: *'Data accuracy is everything. If we make product decisions based on wrong sentiment analysis, we waste R&D budget. Any AI needs to be explainable and auditable.'*"

**Show:**
- Click to reveal SQL behind any answer
- Source data is traceable to specific reviews and brand metrics
- No black box - full transparency

**Key point:**
> "Every insight is backed by SQL you can run yourself. Trust but verify."

---

## Summary

| Stakeholder | Question | Answer Time |
|-------------|----------|-------------|
| Janus (CEO) | "How do our brands compare to competitors?" | < 10 seconds |
| Pieter (Product) | "What product issues need fixing?" | < 10 seconds |
| Marieke (CMO) | "Where are the category gaps?" | < 10 seconds |

**Success criteria met:**
- Speed: Instant answers
- Accuracy: SQL-backed, verifiable
- Simplicity: Plain English, no SQL needed
- Trust: Full audit trail
- Actionable: Specific recommendations per brand

---

## Next Steps

1. **Immediate:** Share with market intelligence team for testing
2. **Day 3:** Gather feedback on additional questions
3. **Day 5:** Decision on production implementation with real Trustpilot/Google review feeds

**Questions?**

---

## Appendix: Sample Questions to Demo

**CEO (Janus):**
- "How do our brand ratings compare to Trek and Specialized?"
- "Which of our brands is underperforming in the Dutch market?"
- "What would it take to get Gazelle to a 4.5 average rating?"

**CMO (Marieke):**
- "Which bike category has no strong Pon brand?"
- "What do competitor reviews praise that our reviews don't mention?"
- "Which competitor is most vulnerable to us taking market share?"

**Product (Pieter):**
- "What are the top complaints about our e-bikes?"
- "Which product features should we prioritize based on competitor reviews?"
- "How do Cannondale road bike reviews compare to Trek and Specialized?"

**Follow-up:**
- "How is Gazelle performing compared to Batavus?"
- "What should we improve on Urban Arrow cargo bikes?"
- "Where should we invest - e-bikes or cargo bikes?"
