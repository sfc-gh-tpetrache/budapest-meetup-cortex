# Exercise: Build the Pon.Bike Competitive Intelligence POC

## Task Checklist

- [ ] **Task 1: Review Your Requirements** (5 min)
  - [ ] Step 1: Review the company background
  - [ ] Step 2: Identify key questions the data must answer

- [ ] **Task 2: Generate POC Database** (20 min)
  - [ ] Step 1: Design the data model
  - [ ] Step 2: Create the database and tables
  - [ ] Step 3: Generate brand data (9 Pon + 16 competitors)
  - [ ] Step 4: Generate bike categories
  - [ ] Step 5: Create brand-category mappings
  - [ ] Step 6: Generate 250 product reviews
  - [ ] Step 7: Validate the data

- [ ] **Task 3: Create Semantic View for Cortex Analyst** (10 min)
  - [ ] Step 1: Understand semantic views
  - [ ] Step 2: Generate the semantic view
  - [ ] Step 3: Test Cortex Analyst queries

- [ ] **Task 4: Create Cortex Search Service** (5 min)
  - [ ] Step 1: Understand Cortex Search
  - [ ] Step 2: Create the Search Service
  - [ ] Step 3: Test the Search Service

- [ ] **Task 5: Configure Snowflake Intelligence** (5 min)
  - [ ] Step 1: Understand Snowflake Intelligence
  - [ ] Step 2: Create a Cortex Agent with Multiple Tools
  - [ ] Step 3: Enable the agent in Snowflake Intelligence
  - [ ] Step 4: Test the agent

- [ ] **Task 6: Prepare Your Presentation Script** (5 min)
  - [ ] Generate talking points

---

## Objective

Build a compelling competitive analytics POC featuring **Cortex Analyst** and **Snowflake Intelligence** that you can present to your leadership team at Pon.Bike.

**Time:** 50 minutes  
**Deliverables:** 
- Working demo database with 25 bicycle brands and 250 realistic product reviews
- Semantic view for Cortex Analyst
- Snowflake Intelligence chat experience ready for your presentation

---

## Background

You're a Market Intelligence Analyst at Pon.Bike, the bicycle division of Pon Holdings. After your requirements gathering meeting with leadership, you need to build a proof-of-concept that demonstrates:
1. Natural language queries for your CEO ("How do our brands compare to Trek?")
2. Self-service competitive analysis without SQL knowledge
3. Auditable, trustworthy AI-generated insights

**The approach:** Since you can't access live review platforms for the POC, you'll create a realistic demo environment based on what you know about the Dutch bicycle market.

Your CEO, Janus Smalbraak, said:
> "We own 9 brands but I can't tell you in 10 seconds which ones are winning and which ones need help."

---

## Task 1: Review Your Requirements (5 min)

### Step 1: Review the company background

```
Read the company background from assets/customer-brief.md and summarize:
1. Company profile (brands, revenue, market position)
2. Current competitive environment
3. Key pain points
4. Primary stakeholders and their concerns
```

### Step 2: Identify key questions the data must answer

The POC must answer these stakeholder questions:

**From Janus (CEO):**
- "How do our brand ratings compare to Trek and Specialized?"
- "Which of our brands is underperforming in the Dutch market?"
- "What would it take to get Gazelle to a 4.5 average rating?"

**From Marieke (CMO):**
- "Which bike category has no strong Pon brand?"
- "What do competitor reviews praise that our reviews don't mention?"

**From Pieter (Product):**
- "What are the top complaints about our e-bikes?"
- "Which product features should we prioritize based on competitor reviews?"

---

## Task 2: Generate POC Database (20 min)

**This is where Cortex Code shines - generating realistic demo data based on your company context.**

### Step 1: Design the data model

Ask Cortex Code to design a schema based on your company's needs:

```
Based on the Pon.Bike company background and the stakeholder questions 
we need to answer, design a Snowflake database schema for our competitive 
intelligence POC. Wait for my approval before proceeding to the next step.

Consider:
- We own 9 bicycle brands (Gazelle, Cannondale, Santa Cruz, etc.)
- We have 16 competitors (Trek, Specialized, Giant, Batavus, etc.)
- We need to analyze product reviews, ratings, and sentiment
- Leadership needs competitive benchmarking and product improvement insights

Create dimension and fact tables appropriate for:
1. Brand analytics (parent company, price tier, categories, dealer network)
2. Product review analysis (ratings, sentiment, complaints, praise)
3. Competitive benchmarking by brand, category, and price tier

The schema must support answering all stakeholder questions listed in Task 1.

Show me the proposed schema and wait for my confirmation before creating anything.
```

### Step 2: Create the database and tables

```
Create the PON_BIKE_DEMO database with the schema you designed.
Use the ANALYTICS schema for the business tables. Wait for my confirmation 
before proceeding to the next step.

Execute the DDL statements to create:
1. DIM_BRANDS (bicycle brands with attributes)
2. DIM_BIKE_CATEGORIES (bike category types)
3. BRIDGE_BRAND_CATEGORIES (many-to-many: which brands compete in which categories)
4. FACT_BRAND_METRICS (monthly brand performance metrics)
5. REVIEWS (product reviews with ratings and text)

Show me confirmation that each table was created.
```

### Step 3: Generate brand data

```
Generate 25 bicycle brands for the DIM_BRANDS table. Wait for my confirmation 
before proceeding to the next step.

**Our 9 Pon.Bike brands (IS_PON_BRAND = TRUE):**
1. Gazelle - Dutch heritage, city/e-bike, Mid-Range
2. Cannondale - Performance, road/MTB, Premium
3. Santa Cruz - Mountain bike specialist, Luxury
4. Cervelo - Road/triathlon, Luxury
5. Kalkhoff - German e-bike/city, Mid-Range
6. Focus - Performance road/MTB, Premium
7. Urban Arrow - Cargo bikes, Premium
8. Veloretti - Urban lifestyle, Mid-Range
9. Schwinn - Classic/casual, Budget

**16 Competitors (IS_PON_BRAND = FALSE):**
- Trek, Specialized, Giant, Cube, Scott, Merida, BMC, Canyon (global brands)
- Batavus, Sparta, Cortina, Koga (Dutch heritage, Accell Group)
- Riese & Muller, Babboe (cargo/e-bike specialists)
- Haibike (e-MTB), VanMoof (lifestyle e-bike)

Include: brand_name, parent_company, headquarters, founded_year, brand_type, 
price_tier, is_pon_brand, primary_category, nl_dealer_count
```

### Step 4: Generate bike categories

```
Generate 12 bike categories for DIM_BIKE_CATEGORIES. Wait for my confirmation 
before proceeding to the next step.

Categories:
- Urban Mobility: City/Commuter, E-bike City, E-bike Trekking, Touring, Speed Pedelec, Folding
- Performance: Road, Mountain Bike, E-MTB, Gravel
- Utility: Cargo
- Recreation: Kids

Include: category_name, segment, avg_price_eur, growth_trend
```

### Step 5: Create brand-category mappings

```
Create bridge table data linking brands to the categories they compete in.
Wait for my confirmation before proceeding to the next step.

Rules:
- Full-range brands (Trek, Giant): compete in 6-8 categories
- Performance brands (Specialized, Cannondale): 3-5 categories
- City/commuter brands (Gazelle, Batavus): 3-4 categories
- Specialists (Urban Arrow, Babboe): 1-2 categories
```

### Step 6: Generate 250 product reviews

```
Generate 250 realistic product reviews for the REVIEWS table. 
Wait for my confirmation before proceeding to the next step.

**Distribution:** Popular brands (Trek, Specialized, Gazelle) get 15-18 reviews, others get 6-10

**Rating distribution:**
- Trek/Specialized average ~4.3 (high performer competitors)
- Giant/Cube/Scott average ~4.1 (solid competitors)
- Gazelle/Kalkhoff average ~3.9-4.1 (our key brands, room for improvement)
- Other Pon brands average ~3.8-4.0 (competitive but with gaps)

**Review attributes:**
- reviewer_name: Dutch-style names (FietsFreak, CyclingDutch, JanW123)
- reviewer_city: Dutch cities (Amsterdam, Rotterdam, Utrecht, Den Haag, etc.)
- rating: 1-5 stars
- review_date: January 2023 - February 2026
- bike_category: matching brand's categories
- purchase_type: New (65%), Used (20%), Lease/Subscription (15%)
- usage_type: Daily Commute (40%), Recreation (25%), Sport (20%), Family Transport (15%)

**Content themes by brand type:**
- Pon e-bikes: battery range, motor noise, Dutch design, dealer availability
- Pon performance: components, frame quality, weight, value vs Trek/Specialized
- Pon cargo: heavy but practical, turning radius, family friendly
- Competitors (Trek/Specialized): innovation, strong dealer network, premium experience
- Competitors (Dutch brands): heritage, practical, good dealer network

Use SNOWFLAKE.CORTEX.COMPLETE to generate review text.
```

### Step 7: Validate the data

```
Run validation queries to confirm:
1. Row counts for all tables
2. Rating distribution shows Pon brands slightly below top competitors
3. All 25 brands have reviews
4. Sample review text looks realistic and bike-specific
5. Monthly metrics show realistic seasonality (spring/summer peaks)

Show me a summary of what was created.
```

---

## Task 3: Create Semantic View for Cortex Analyst (10 min)

### Step 1: Understand semantic views

```
Explain what a Cortex Analyst semantic view is and why it's important 
for natural language queries. How is it different from a YAML semantic model?
Keep it brief - 3-4 sentences.
```

### Step 2: Generate the semantic view

**Note:** Use the `semantic-view-optimization` skill if available for best results.

```
Create a Cortex Analyst semantic view using SQL for the PON_BIKE_DEMO 
database. Wait for my confirmation before proceeding. The semantic view should:

1. Include BRANDS, REVIEWS, and BRAND_METRICS tables
2. Define relationships between tables (foreign keys via BRAND_ID)
3. Add business-friendly descriptions and synonyms
4. Define key metrics for competitive analysis

**Required metrics:**
- avg_rating: Average star rating
- review_count: Number of reviews
- total_units_sold: Sum of NL units sold
- total_revenue: Sum of NL revenue
- avg_market_share: Average market share percentage

**Required synonyms:**
- "our brands" / "pon brands" = IS_PON_BRAND = TRUE
- "competitors" / "competition" = IS_PON_BRAND = FALSE
- "score" / "stars" = rating
- "feedback" / "comments" = reviews
- "dealers" / "stores" = NL_DEALER_COUNT

Execute the SQL to create the semantic view.
```

### Step 3: Test Cortex Analyst queries

Test the semantic view with questions leadership will ask:

```
Using the semantic view we just created, test these questions:

1. "How do our brand ratings compare to Trek and Specialized?" (Janus's question)
2. "Which of our brands is underperforming?" (Janus's question)
3. "Which bike category has the highest revenue?" (Marieke's question)
4. "What is Gazelle's market share trend?" (Pieter's question)
5. "Which brands have the most reviews?" (general)

For each question, show me:
- The natural language question
- The SQL that Cortex Analyst generated
- The results
```

---

## Task 4: Create Cortex Search Service (5 min)

### Step 1: Understand Cortex Search

```
Explain what Cortex Search is and why it's useful for semantic search over reviews.
How is it different from SQL queries on review text? Keep it to 3-4 sentences.
```

### Step 2: Create the Search Service

```
Create a Cortex Search Service for semantic search over our bike reviews. 
Wait for my confirmation before executing.

The search service should:
1. Be named BIKE_REVIEWS_SEARCH
2. Index the REVIEW_TEXT column for semantic search
3. Include BRAND_ID, BIKE_CATEGORY, and USAGE_TYPE as filterable attributes
4. Include additional columns: REVIEW_ID, REVIEWER_NAME, REVIEWER_CITY, RATING, REVIEW_DATE, REVIEW_TITLE
5. Use the snowflake-arctic-embed-l-v2.0 embedding model
6. Set TARGET_LAG to '1 day'

Execute the DDL to create the search service.
```

### Step 3: Test the Search Service

```
Test the Cortex Search Service by searching for complaints about our brands:

1. First, get the BRAND_IDs for our Pon brands (IS_PON_BRAND = TRUE)
2. Search for "complaints about battery range and motor noise on e-bikes" filtered to only our brands
3. Show the top 5 results with rating, title, category, and review text

This demonstrates semantic search - finding relevant reviews even when they don't contain exact keywords.
```

---

## Task 5: Configure Snowflake Intelligence (5 min)

### Step 1: Understand Snowflake Intelligence

```
What is Snowflake Intelligence and how does it differ from Cortex Analyst? 
How do they work together? Keep it to 3-4 sentences.
```

### Step 2: Create a Cortex Agent with Multiple Tools

**Note:** Use the `agent-optimization` skill if available for best results.

```
Create a Cortex Agent for our Pon.Bike POC with TWO tools:
1. Cortex Analyst (bike_analyst) - for structured data queries
2. Cortex Search (review_search) - for semantic search over reviews

Wait for my confirmation before executing SQL. The agent should:

1. Be named "PON_BIKE_ANALYST"
2. Use claude-sonnet-4-5 as the orchestration model
3. Configure bike_analyst tool with our semantic view
4. Configure review_search tool with our Cortex Search Service
5. Set max_results to 10 for the search tool

**Agent instructions:**
"You help analyze bicycle market competitive intelligence for Pon.Bike in 
the Netherlands. Use the analyst tool for data queries (ratings, metrics, 
market share comparisons). Use the search tool to find specific product 
reviews or customer feedback. Our brands have IS_PON_BRAND=TRUE, competitors 
have IS_PON_BRAND=FALSE."

**Response instructions:**
"Be concise and data-driven. When discussing reviews, include relevant quotes. 
Always specify brand names rather than just IDs."

Execute the CREATE AGENT DDL.
```

### Step 3: Enable the agent in Snowflake Intelligence

```
Make the Pon.Bike Competitive Analyst agent available in Snowflake Intelligence.
Wait for my confirmation before executing grants.

1. Grant USAGE on the agent to PUBLIC (or a specific role)
2. Add the agent to the Snowflake Intelligence object
3. Verify it was added successfully

Execute all SQL.
```

### Step 4: Test the agent

```
Test the agent with executive-style questions that Janus, Marieke, and Pieter 
might ask:

1. "How do our brand ratings compare to Trek and Specialized?" (uses: analyst tool)
2. "What are the top complaints about Gazelle e-bikes?" (uses: search tool)
3. "Which bike category has no strong Pon brand?" (uses: analyst tool)

Show me the SQL for each response (Pieter needs auditability).
```

---

## Task 6: Prepare Your Presentation Script (5 min)

### Generate talking points

```
Based on my customer brief and stakeholder questions, create a 10-minute 
presentation script that:

1. Opens with Janus's pain point (can't tell which brands are winning)
2. Shows competitive benchmarking answering his question in seconds
3. Demonstrates product review analysis for Pieter's question
4. Shows category gap analysis for Marieke
5. Addresses Pieter's concern about auditability (show the SQL)
6. Ends with specific recommendations for Pon.Bike

Format as brief talking points with the exact queries to run.
Reference specific quotes from the customer brief.
```

---

## Validation Checklist

Before proceeding, verify:

- [ ] PON_BIKE_DEMO database created with all tables
- [ ] 25 brands loaded (9 Pon + 16 competitors with IS_PON_BRAND flag)
- [ ] 250 reviews with bicycle-specific product review content
- [ ] Rating distribution: Trek/Specialized ~4.3, Pon brands ~3.9-4.1
- [ ] Monthly metrics show bike seasonality (spring/summer peaks)
- [ ] Semantic view created and responding to natural language
- [ ] Generated SQL is correct and auditable
- [ ] Cortex Search Service created (BIKE_REVIEWS_SEARCH)
- [ ] Cortex Agent created with TWO tools (analyst + search)
- [ ] Agent enabled in Snowflake Intelligence
- [ ] Can answer all stakeholder questions from Task 1

---

## Key Stakeholder Questions - Data Requirements

| Question | Required Data | Agent Tool Used |
|----------|---------------|------------------|
| "How do our brand ratings compare to Trek?" | avg_rating by brand, IS_PON_BRAND flag | **Analyst** (structured query) |
| "Which of our brands is underperforming?" | avg_rating by Pon brand | **Analyst** (structured query) |
| "Which bike category has no strong Pon brand?" | category, brand, market share | **Analyst** (structured query) |
| "What are the top complaints about our e-bikes?" | review_text semantic search | **Search** (semantic search) |
| "Which features should we prioritize?" | review_text sentiment analysis | **Search** (semantic search) |
| "What is Gazelle's market share trend?" | monthly metrics time series | **Analyst** (structured query) |
| "How do Cannondale reviews compare to Trek?" | review_text, rating by brand | **Both** (analyst + search) |
| "What do competitor reviews praise?" | review_text semantic search | **Search** (semantic search) |

---

## Key Takeaways

1. **Context is everything** - Your company knowledge drives realistic demos
2. **Cortex Code generates data** - No need to manually create sample datasets
3. **Semantic views are the foundation** - They teach AI how to query your data correctly
4. **Test with real questions** - Use actual questions from your stakeholders
5. **Show the SQL** - Builds trust with skeptical stakeholders like Pieter

---

## Pro Tips

1. **Make it personal** - Use "our brands" vs "competitors" throughout
2. **Include realistic weaknesses** - Pon brands should have fixable product gaps
3. **Show the opportunity** - Data should reveal clear category and product gaps
4. **Match brand names** - Use real brand names for credibility
5. **Test edge cases** - What if a category has no Pon brand? Empty results?

---

## Next Steps

After completing this exercise, you can:
1. Present to Janus, Marieke, and Pieter
2. Iterate based on their feedback
3. Plan production implementation with real review data feeds from Trustpilot/Google
