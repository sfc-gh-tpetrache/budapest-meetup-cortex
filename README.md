# Budapest Spa Competitive Intelligence POC

Build a competitive analytics proof-of-concept for **Aqua Serenity Spas** using Snowflake Cortex.

## What We're Building
A demo environment with 33 Budapest spas (3 owned + 30 competitors) and 250 TripAdvisor-style reviews, enabling natural language queries for executive decision-making.

## Key Components
1. **POC Database** - Dimension tables (spas, treatments, facilities) + fact table (reviews)
2. **Semantic View** - Cortex Analyst integration for natural language queries
3. **Cortex Search** - Semantic search over customer reviews
4. **Cortex Agent** - Combined analyst + search in Snowflake Intelligence

## Business Context
- **Company**: Aqua Serenity Spas (3 locations, 4.0 avg rating)
- **Challenge**: Trails thermal baths (4.4 avg) by 0.4 stars
- **Goal**: Identify why customers prefer competitors and what to fix

## Time: ~50 minutes
See `00_exercise-spa-competitive-demo.md` for detailed step-by-step instructions.
