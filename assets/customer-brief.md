# Company Background: Pon.Bike

## About Your Company

**Pon.Bike** is the bicycle division of Pon Holdings, a Dutch family-owned multinational headquartered in Amsterdam. With 9 major bicycle brands and over EUR 2.1 billion in annual revenue, Pon.Bike is one of the five largest bicycle manufacturers in the world and the dominant player in the Netherlands market. The company's portfolio spans city bikes, e-bikes, cargo bikes, performance road bikes, and mountain bikes.

### Key Business Metrics
- **Brands:** 9 major bicycle brands in portfolio
- **Annual Revenue:** EUR 2.1B (2024, bicycle division)
- **Employees:** ~5,000 (Pon.Bike division)
- **NL Market Position:** Largest bicycle company in the Netherlands
- **Average Product Rating:** 4.0/5.0 across brands (room for improvement)
- **NL Dealer Network:** 800+ authorized dealers

### Our 9 Brands

| Brand | Category | Price Tier | Positioning | NL Dealers |
|-------|----------|------------|-------------|------------|
| Gazelle | City/E-bike | Mid-Range | Dutch heritage, #1 Dutch bike brand | 350 |
| Cannondale | Road/MTB | Premium | Performance cycling | 120 |
| Santa Cruz | Mountain Bike | Luxury | High-end MTB | 25 |
| Cervelo | Road/Triathlon | Luxury | Professional racing | 30 |
| Kalkhoff | E-bike/City | Mid-Range | German engineering, commuter focus | 180 |
| Focus | Road/MTB | Premium | Competitive cycling | 85 |
| Urban Arrow | Cargo Bike | Premium | Urban family mobility | 60 |
| Veloretti | Urban/Lifestyle | Mid-Range | Direct-to-consumer, trendy | 15 |
| Schwinn | Classic/Casual | Budget | Heritage, entry-level | 40 |

---

## Current Competitive Environment

### Market Landscape

The Netherlands has the highest cycling rate in the world with 23 million bicycles for 17 million people. E-bikes now account for over 50% of new bike sales by revenue. We compete against:

| Competitor Type | Key Players | Avg Rating | Our Challenge |
|-----------------|-------------|------------|---------------|
| Global Performance Brands | Trek, Specialized | 4.3/5.0 | Innovation reputation, brand loyalty |
| Full-Range Manufacturers | Giant, Cube | 4.2/5.0 | Price-to-performance, dealer density |
| Dutch Heritage Brands | Batavus, Sparta, Cortina | 4.1/5.0 | Local loyalty, commuter segment |
| Cargo/E-bike Specialists | Riese & Muller, Babboe | 4.0/5.0 | Niche focus, growing segment |
| E-MTB Specialists | Haibike | 4.1/5.0 | Electric mountain bike segment |

### Top Competitors We Track

1. **Trek** - 4.4 rating, dominant dealer network, full range from city to pro
2. **Specialized** - 4.3 rating, innovation leader (Turbo e-bikes), strong brand loyalty
3. **Giant** - 4.2 rating, best price-to-performance, huge global scale
4. **Batavus** - 4.1 rating, Dutch heritage brand (Accell Group), strong commuter segment
5. **Cube** - 4.2 rating, German value brand, fast-growing in NL

---

## Pain Points Identified by Leadership

### Strategic Challenges
1. **E-bike market saturation:** Asian manufacturers entering with aggressive pricing
2. **Brand fragmentation:** 9 brands but consumers confused about positioning and overlap
3. **Review visibility:** Trek and Specialized dominate review platforms and social media
4. **Category gaps:** Some high-growth categories (gravel, speed pedelec) lack a strong Pon brand
5. **Dutch market defense:** Accell Group brands (Batavus, Sparta) competing hard for commuter segment

### Operational Challenges
1. **Manual competitive analysis:** Team spends 15+ hours/month tracking competitor reviews across platforms
2. **Delayed insights:** Product feedback reaches product teams months after launch
3. **No cross-brand analysis:** Each brand team tracks their own metrics differently
4. **Blind spots:** We don't know which product features drive competitor preference

---

## POC Requirements from Leadership

### Must Have (P0)
- [ ] Natural language interface for executives
- [ ] Brand-level and category-level competitive benchmarking
- [ ] Sentiment analysis of negative reviews to identify product improvements
- [ ] Up-to-date rating benchmarks vs top competitors

### Should Have (P1)
- [ ] Category gap analysis (where Pon has no strong brand)
- [ ] Price-tier positioning recommendations
- [ ] Feature priority analysis based on competitor review themes

---

## Key Stakeholders

### CEO and Executive Sponsor
**Janus Smalbraak, CEO**
- Led Pon.Bike through major acquisitions (Dorel Sports, Urban Arrow)
- Focused on portfolio strategy and brand synergies
- Concerned about e-bike commoditization and margin pressure
- *Your primary champion - wants data to drive brand investment decisions*

Key quote:
> "We own 9 brands but I can't tell you in 10 seconds which ones are winning and which ones need help. I need a dashboard that speaks plain language."

### CMO and Growth Lead
**Marieke de Vries, Chief Marketing Officer**
- Former Unilever brand director, joined Pon.Bike 2022
- Focused on brand differentiation and category leadership
- Wants to identify underserved segments for brand positioning
- *Cares about competitive positioning and messaging gaps*

Key quote:
> "Every brand should own a category. If there's a category where we don't have a strong contender, that's either an acquisition target or a brand repositioning opportunity."

### Head of Product
**Pieter van den Berg, VP Product Development**
- 15 years in bicycle engineering, previously at Giant
- Manages product roadmaps across all 9 brands
- Wants specific feature and quality feedback from reviews
- *Will scrutinize product insights and data accuracy*

Key quote:
> "Don't just tell me ratings are low - tell me WHICH brand has WHICH problem. Is it the motor, the frame, the components, or the dealer experience? I need specifics."

**On data and AI:**
> "Data accuracy is everything. If we make product decisions based on wrong sentiment analysis, we waste R&D budget. Any AI needs to be explainable and auditable."

### Your Team
**4 analysts** in market intelligence
- Power BI and Excel experts, moderate SQL skills
- Currently spend 40% of time on manual competitor tracking across review platforms
- Want self-service analytics without waiting for IT
- Skeptical that AI can understand bicycle product nuance

---

## POC Timeline

| Milestone | Target | Notes |
|-----------|--------|-------|
| Build POC | This session | What you're doing now |
| Present to CEO/CMO | Tomorrow | Show competitive insights |
| Gather Feedback | Day 3 | Iterate based on stakeholder questions |
| Decision | Day 5 | Go/no-go on production implementation |

---

## Why Snowflake + Cortex Code?

You've evaluated options and see potential in:
- **Cortex Analyst** - Natural language queries for competitive benchmarking
- **Snowflake Intelligence** - Chat interface for executives
- **Semantic Views** - Business-friendly layer hiding SQL complexity
- **Full Auditability** - Show SQL behind every answer (Pieter's requirement)
- **Scalability** - Can add more brands, real-time review feeds, and international markets later

Your job is to prove this can transform how Pon.Bike tracks competition across its brand portfolio.

---

## Success Criteria (from Janus)

1. **Speed:** Answer "How does Gazelle compare to Batavus?" in under 10 seconds
2. **Accuracy:** Numbers must be verifiable (Pieter will validate)
3. **Simplicity:** Non-technical users can ask questions without SQL
4. **Trust:** Show the SQL behind answers (Pieter needs auditability)
5. **Actionable:** Recommendations must be specific and implementable

---

## Sample Questions the POC Must Answer

From Janus (CEO):
- "How do our brand ratings compare to Trek and Specialized?"
- "Which of our brands is underperforming in the Dutch market?"
- "What would it take to get Gazelle to a 4.5 average rating?"

From Marieke (CMO):
- "Which bike category has no strong Pon brand?"
- "What do competitor reviews praise that our reviews don't mention?"
- "Which competitor is most vulnerable to us taking market share?"

From Pieter (Product):
- "What are the top 3 complaints about our e-bikes?"
- "Which product features should we prioritize based on competitor reviews?"
- "How do Cannondale road bike reviews compare to Trek and Specialized?"
