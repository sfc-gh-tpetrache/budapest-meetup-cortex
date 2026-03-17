# Pon.Bike Competitive Intelligence POC

Build a competitive analytics proof-of-concept for **Pon.Bike** using Snowflake Cortex.

## What We're Building
A demo environment with 25 bicycle brands (9 Pon + 16 competitors) and 250 product reviews, enabling natural language queries for executive decision-making in the Dutch bicycle market.

## Key Components
1. **POC Database** - Dimension tables (brands, bike categories) + fact tables (brand metrics, reviews)
2. **Semantic View** - Cortex Analyst integration for natural language queries
3. **Cortex Search** - Semantic search over product reviews
4. **Cortex Agent** - Combined analyst + search in Snowflake Intelligence

## Business Context
- **Company**: Pon.Bike (9 brands, EUR 2.1B revenue)
- **Challenge**: Pon brands average ~4.0 rating vs Trek/Specialized at ~4.3
- **Goal**: Identify brand gaps, category opportunities, and product improvements

## Time: ~50 minutes
See `00_exercise-pon-competitive-demo.md` for detailed step-by-step instructions.
