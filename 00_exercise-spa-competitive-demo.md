# Exercise: Build the Spa Competitive Intelligence POC

## Task Checklist

- [ ] **Task 1: Review Your Requirements** (5 min)
  - [ ] Step 1: Review the company background
  - [ ] Step 2: Identify key questions the data must answer

- [ ] **Task 2: Generate POC Database** (20 min)
  - [ ] Step 1: Design the data model
  - [ ] Step 2: Create the database and tables
  - [ ] Step 3: Generate spa location data
  - [ ] Step 4: Generate treatments and facilities
  - [ ] Step 5: Create spa-treatment and spa-facility mappings
  - [ ] Step 6: Generate 250 TripAdvisor-style reviews
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

Build a compelling competitive analytics POC featuring **Cortex Analyst** and **Snowflake Intelligence** that you can present to your leadership team at Aqua Serenity Spas.

**Time:** 50 minutes  
**Deliverables:** 
- Working demo database with 33 Budapest spas and 250 realistic reviews
- Semantic view for Cortex Analyst
- Snowflake Intelligence chat experience ready for your presentation

---

## Background

You're a BI Analyst at Aqua Serenity Spas. After your requirements gathering meeting with leadership, you need to build a proof-of-concept that demonstrates:
1. Natural language queries for your CEO ("How do we compare to Szechenyi?")
2. Self-service competitive analysis without SQL knowledge
3. Auditable, trustworthy AI-generated insights

**The approach:** Since you can't scrape live TripAdvisor data for the POC, you'll create a realistic demo environment based on what you know about the Budapest spa market.

Your CEO, Andras Kovacs, said:
> "I want to know exactly why customers prefer our competitors and what we need to fix."

---

## Task 1: Review Your Requirements (5 min)

### Step 1: Review the company background

```
Read the company background from fun_demo/customer-brief.md and summarize:
1. Company profile (locations, revenue, market position)
2. Current competitive environment
3. Key pain points
4. Primary stakeholders and their concerns
```

### Step 2: Identify key questions the data must answer

The POC must answer these stakeholder questions:

**From Andras (CEO):**
- "How do our ratings compare to the top 5 competitors?"
- "Which of our locations is underperforming and why?"
- "What would it take to reach a 4.5 average rating?"

**From Eva (CMO):**
- "Which districts have no premium spas? That's our opportunity."
- "What do reviews mention that we're not doing?"

**From Peter (Operations):**
- "What are the top 3 complaints at each of our locations?"
- "Which treatments should we add based on competitor success?"

---

## Task 2: Generate POC Database (20 min)

**This is where Cortex Code shines - generating realistic demo data based on your company context.**

### Step 1: Design the data model

Ask Cortex Code to design a schema based on your company's needs:

```
Based on the Aqua Serenity Spas company background and the stakeholder questions 
we need to answer, design a Snowflake database schema for our competitive 
intelligence POC. Wait for my approval before proceeding to the next step.

Consider:
- We own 3 spa locations in Budapest (different districts and price tiers)
- We have 30 competitors (thermal baths, hotel spas, wellness centers)
- We need to analyze customer reviews, ratings, and sentiment
- Leadership needs competitive benchmarking and improvement insights

Create dimension and fact tables appropriate for:
1. Spa location analytics (geography, pricing, type, facilities)
2. Customer review analysis (ratings, sentiment, complaints, praise)
3. Competitive benchmarking by district and price tier

The schema must support answering all stakeholder questions listed in Task 1.

Show me the proposed schema and wait for my confirmation before creating anything.
```

### Step 2: Create the database and tables

```
Create the BUDAPEST_SPA_DEMO database with the schema you designed.
Use the ANALYTICS schema for the business tables. Wait for my confirmation 
before proceeding to the next step.

Execute the DDL statements to create:
1. DIM_SPAS (spa locations with attributes)
2. DIM_TREATMENTS (treatment types offered)
3. DIM_FACILITIES (facilities/amenities)
4. BRIDGE_SPA_TREATMENTS (many-to-many: which spas offer which treatments)
5. BRIDGE_SPA_FACILITIES (many-to-many: which spas have which facilities)
6. FACT_REVIEWS (customer reviews with ratings and comments)

Show me confirmation that each table was created.
```

### Step 3: Generate spa location data

```
Generate 33 Budapest spas for the DIM_SPAS table. Wait for my confirmation 
before proceeding to the next step.

**Our 3 Aqua Serenity locations (is_owned = TRUE):**
1. Aqua Serenity Castle District - District I, Premium, opened 2019
2. Aqua Serenity City Park - District XIV, Mid-Range, opened 2018
3. Aqua Serenity Buda Hills - District XII, Luxury, opened 2021

**30 Competitors (is_owned = FALSE):**
- 6-8 historic thermal baths (Szechenyi, Gellert, Rudas, Kiraly, Lukacs, Palatinus, etc.)
- 8-10 hotel spas (Four Seasons, Corinthia, Aria, Kempinski, Hilton, etc.)
- 8-10 wellness/day spas across districts
- 4-6 boutique specialty spas

Include these attributes for each spa:
- spa_name, latitude (47.45-47.55), longitude (18.95-19.15)
- district (I through XXIII), neighborhood
- spa_type (Thermal Bath, Hotel Spa, Wellness Spa, Day Spa, Boutique Spa)
- price_tier (Budget, Mid-Range, Premium, Luxury)
- is_owned (TRUE/FALSE), opening_year, capacity

Distribute spas realistically across Budapest districts.
```

### Step 4: Generate treatments and facilities

```
Generate dimension data for treatments and facilities. Wait for my confirmation 
before proceeding to the next step.

**DIM_TREATMENTS (18-20 types):**
- Thermal/Bath: Thermal Bath, Cold Plunge, Mineral Bath, Mud Treatment
- Massage: Swedish Massage, Thai Massage, Hot Stone, Deep Tissue, Aromatherapy
- Facial: Classic Facial, Anti-Aging Facial, Hydrating Facial
- Body: Body Scrub, Body Wrap, Detox Treatment
- Specialty: Couples Treatment, Medical Massage, Hydrotherapy

Include: treatment_name, category, avg_duration_min, avg_price_huf

**DIM_FACILITIES (15-18 types):**
- Pools: Indoor Pool, Outdoor Pool, Thermal Pool, Wave Pool, Lap Pool
- Heat: Finnish Sauna, Steam Room, Infrared Sauna, Salt Room
- Relaxation: Relaxation Room, Rooftop Terrace, Garden, Private Cabins
- Amenities: Restaurant, Cafe, Fitness Center, Locker Room

Include: facility_name, category
```

### Step 5: Create spa-treatment and spa-facility mappings

```
Create bridge table data linking spas to their treatments and facilities.
Wait for my confirmation before proceeding to the next step.

Rules:
- Thermal baths: 10-15 treatments, 12-18 facilities (most comprehensive)
- Hotel spas: 8-12 treatments, 8-12 facilities
- Wellness spas: 6-10 treatments, 6-10 facilities
- Day spas: 4-8 treatments, 4-6 facilities
- Boutique spas: 3-6 specialized treatments, 3-5 facilities

Our Aqua Serenity spas should have FEWER treatments and facilities than 
top competitors - this creates the "gap" Peter wants to identify.
```

### Step 6: Generate 300 TripAdvisor-style reviews

```
Generate 250 realistic TripAdvisor-style reviews for FACT_REVIEWS. 
Wait for my confirmation before proceeding to the next step.

**Distribution:** ~6 reviews per spa (some popular ones get 10-12, smaller ones get 3-4)

**Rating distribution (realistic bell curve):**
- 5 stars: 35%
- 4 stars: 30%
- 3 stars: 20%
- 2 stars: 10%
- 1 star: 5%

**Review attributes:**
- reviewer_name: "John M.", "SpaLover2024", "BudapestVisitor123"
- reviewer_location: Tourist countries (UK, Germany, USA, France, Italy, Netherlands)
- rating: 1-5 stars
- review_date: January 2023 - February 2026
- review_title: Catchy title ("Best thermal bath!", "Disappointing for the price")
- review_text: 50-150 words mentioning specific details
- visit_type: Solo (15%), Couple (40%), Family (20%), Friends (20%), Business (5%)

**Content themes by rating:**
- 5-star: Exceptional staff, unique treatments, beautiful facilities, worth the price
- 4-star: Good experience, minor issues, would return
- 3-star: Average, nothing special, some problems
- 2-star: Disappointing, crowded, overpriced, rude staff
- 1-star: Terrible experience, dirty, long waits, avoid

**Important for our analysis:**
- Aqua Serenity spas should average 3.8-4.2 rating (below thermal baths at 4.3-4.5)
- Common complaints about OUR spas: wait times, outdated facilities, limited treatments
- Common praise for OUR spas: friendly staff, good location, clean
- Competitors should have varied ratings that reveal opportunities
```

### Step 7: Validate the data

```
Run validation queries to confirm:
1. Row counts for all tables
2. Rating distribution matches target percentages
3. All 33 spas have reviews
4. Sample review text looks realistic
5. Our 3 locations have lower average ratings than top competitors

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
Create a Cortex Analyst semantic view using SQL for the BUDAPEST_SPA_DEMO 
database. Wait for my confirmation before proceeding. The semantic view should:

1. Include all dimension and fact tables we created
2. Define relationships between tables (foreign keys)
3. Add business-friendly descriptions and synonyms
4. Define key metrics for competitive analysis

**Required metrics:**
- avg_rating: Average star rating
- review_count: Number of reviews
- positive_rate: Percentage of 4-5 star reviews
- negative_rate: Percentage of 1-2 star reviews

**Required synonyms:**
- "our spas" / "our locations" = is_owned = TRUE
- "competitors" / "competition" = is_owned = FALSE
- "score" / "stars" = rating
- "feedback" / "comments" = reviews
- "area" / "neighborhood" = district
- "cost" / "pricing" = price_tier

Execute the SQL to create the semantic view.
```

### Step 3: Test Cortex Analyst queries

Test the semantic view with questions leadership will ask:

```
Using the semantic view we just created, test these questions:

1. "How do our ratings compare to the top 5 competitors?" (Andras's question)
2. "Which of our locations is underperforming?" (Andras's question)
3. "Which districts have no premium spas?" (Eva's question)
4. "What are the top complaints at our Downtown location?" (Peter's question)
5. "What treatments do top-rated spas offer that we don't?" (Peter's question)

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
Create a Cortex Search Service for semantic search over our spa reviews. 
Wait for my confirmation before executing.

The search service should:
1. Be named SPA_REVIEWS_SEARCH
2. Index the REVIEW_TEXT column for semantic search
3. Include SPA_ID and VISIT_TYPE as filterable attributes
4. Include additional columns: REVIEW_ID, REVIEWER_NAME, REVIEWER_LOCATION, RATING, REVIEW_DATE, REVIEW_TITLE
5. Use the snowflake-arctic-embed-l-v2.0 embedding model
6. Set TARGET_LAG to '1 day'

Execute the DDL to create the search service.
```

### Step 3: Test the Search Service

```
Test the Cortex Search Service by searching for complaints about our spas:

1. First, get the SPA_IDs for our owned spas (IS_OWNED = TRUE)
2. Search for "complaints about wait times and crowded" filtered to only our spas
3. Show the top 5 results with rating, title, and review text

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
Create a Cortex Agent for our Aqua Serenity Spas POC with TWO tools:
1. Cortex Analyst (spa_analyst) - for structured data queries
2. Cortex Search (review_search) - for semantic search over reviews

Wait for my confirmation before executing SQL. The agent should:

1. Be named "SPA_COMPETITIVE_ANALYST"
2. Use claude-sonnet-4-5 as the orchestration model
3. Configure spa_analyst tool with our semantic view
4. Configure review_search tool with our Cortex Search Service
5. Set max_results to 10 for the search tool

**Agent instructions:**
"You help analyze spa competitive intelligence. Use the analyst tool for data 
queries (ratings, metrics, comparisons). Use the search tool to find specific 
reviews or customer feedback. Our spas have IS_OWNED=TRUE, competitors have 
IS_OWNED=FALSE."

**Response instructions:**
"Be concise and data-driven. When discussing reviews, include relevant quotes."

Execute the CREATE AGENT DDL.
```

### Step 3: Enable the agent in Snowflake Intelligence

```
Make the Aqua Serenity Competitive Analyst agent available in Snowflake Intelligence.
Wait for my confirmation before executing grants.

1. Grant USAGE on the agent to PUBLIC (or a specific role)
2. Add the agent to the Snowflake Intelligence object
3. Verify it was added successfully

Execute all SQL.
```

### Step 4: Test the agent

```
Test the agent with executive-style questions that Andras, Eva, and Peter 
might ask:

1. "How are we doing compared to Szechenyi Baths?" (uses: analyst tool)
2. "What should we fix at our Downtown location?" (uses: search tool for complaints)
3. "Where should we open our 4th spa?" (uses: analyst tool for district analysis)

Show me the SQL for each response (Peter needs auditability).
```

---

## Task 6: Prepare Your Presentation Script (5 min)

### Generate talking points

```
Based on my customer brief and stakeholder questions, create a 10-minute 
presentation script that:

1. Opens with Andras's pain point (losing customers to thermal baths)
2. Shows competitive benchmarking answering his question in seconds
3. Demonstrates sentiment analysis for Peter's operational question
4. Shows expansion opportunity analysis for Eva
5. Addresses Peter's concern about auditability (show the SQL)
6. Ends with specific recommendations for Aqua Serenity

Format as brief talking points with the exact queries to run.
Reference specific quotes from the customer brief.
```

---

## Validation Checklist

Before proceeding, verify:

- [ ] BUDAPEST_SPA_DEMO database created with all tables
- [ ] 33 spas loaded (3 owned + 30 competitors with is_owned flag)
- [ ] 250 reviews with TripAdvisor-style content
- [ ] Rating distribution: ~35% 5-star, ~30% 4-star, etc.
- [ ] Our spas average 3.8-4.2 rating (below thermal bath average of 4.4)
- [ ] Semantic view created and responding to natural language
- [ ] Generated SQL is correct and auditable
- [ ] Cortex Search Service created (SPA_REVIEWS_SEARCH)
- [ ] Cortex Agent created with TWO tools (analyst + search)
- [ ] Agent enabled in Snowflake Intelligence
- [ ] Can answer all stakeholder questions from Task 1

---

## Key Stakeholder Questions - Data Requirements

| Question | Required Data | Agent Tool Used |
|----------|---------------|------------------|
| "How do our ratings compare to top 5 competitors?" | avg_rating by spa, is_owned flag | **Analyst** (structured query) |
| "Which of our locations is underperforming?" | avg_rating by owned spa | **Analyst** (structured query) |
| "Which districts have no premium spas?" | district, price_tier, spa count | **Analyst** (structured query) |
| "What do 5-star reviews mention?" | review_text where rating=5 | **Search** (semantic search) |
| "Top 3 complaints at each location?" | review_text sentiment analysis | **Search** (semantic search) |
| "Which treatments should we add?" | treatment availability by rating | **Analyst** (structured query) |
| "What are customers saying about wait times?" | review_text semantic search | **Search** (semantic search) |
| "Staff service comparison?" | review_text sentiment on "staff" | **Search** (semantic search) |

---

## Key Takeaways

1. **Context is everything** - Your company knowledge drives realistic demos
2. **Cortex Code generates data** - No need to manually create sample datasets
3. **Semantic views are the foundation** - They teach AI how to query your data correctly
4. **Test with real questions** - Use actual questions from your stakeholders
5. **Show the SQL** - Builds trust with skeptical stakeholders like Peter

---

## Pro Tips

1. **Make it personal** - Use "our spas" vs "competitors" throughout
2. **Include realistic weaknesses** - Our spas should have fixable problems
3. **Show the opportunity** - Data should reveal clear next steps
4. **Match competitor names** - Use real Budapest spa names for credibility
5. **Test edge cases** - What if a district has no spas? Empty results?

---

## Next Steps

After completing this exercise, you can:
1. Present to Andras, Eva, and Peter
2. Iterate based on their feedback
3. Plan production implementation with real TripAdvisor data feeds
