# Project Note — Core Problem #1: Data Collection

## Problem we need to solve
If this project is focused on Metro Vancouver, we need to build a **community-level grocery price database** (not just broad regional averages).

Current public sources are useful but insufficient for neighborhood-level, store-level affordability comparison.

## Why this is the first blocker
Without a reliable local price database, we cannot produce:
- valid community/store affordability rankings,
- a trustworthy savings calculator,
- actionable map outputs by neighborhood.

## Obstacles we are facing
1. **No single official community-level grocery price dataset** for Metro Vancouver.
2. **StatsCan average price tables are not designed for pure local time-series comparison** (product rotation, size/quality differences).
3. **Store-level prices are fragmented** across flyers, websites, and promotions.
4. **Scraping and access constraints** (terms of use, anti-bot controls, unstable page structures).
5. **Unit/brand/package mismatch** across stores (hard to compare apples-to-apples).
6. **High update frequency** (weekly promos) creates maintenance burden.
7. **Data quality risks** in crowdsourced/manual collection.

## Suggested actions (practical sequence)
### Phase A — Build a defensible baseline (immediate)
- Use publicly available StatsCan + CPI + wage/income datasets.
- Define an essential basket and standardized units.
- Produce regional affordability pressure metrics while local store DB is being built.

### Phase B — Create Metro Vancouver local price database (pilot)
- Start with 3–5 major chains and 20–30 essential items.
- Collect weekly prices from publicly accessible flyers/e-commerce pages.
- Standardize units (e.g., per 100g, per litre, per dozen).
- Record location metadata: city, neighborhood/community, postal prefix, store.
- Implement QA rules (missing checks, outlier checks, duplicate checks).

### Phase C — Expand and operationalize
- Add more stores and neighborhoods iteratively.
- Add crowdsourced receipt validation layer.
- Version datasets weekly; document methods/limitations clearly.

## Minimum data model to create
- `date`
- `store_name`
- `store_chain`
- `address`
- `city`
- `community/neighborhood`
- `postal_prefix`
- `item_name`
- `item_category`
- `brand`
- `package_size`
- `unit`
- `standardized_unit_price`
- `promo_flag`
- `source_url`
- `collection_method`

## Immediate next step
Create a **Week-1 data collection pilot** for 10 items × 3 stores × 2 communities, then evaluate quality and scale plan.

## Reality check: data availability
Usually, there is **no official, complete community-level grocery price dataset**.

What exists:
- StatsCan average prices (good baseline, not neighborhood-level store detail)
- CPI data (region-level index, not store/community basket prices)
- Flyers/e-commerce prices (store-level but messy/incomplete)
- Occasional community surveys (limited scope, not always continuous)
