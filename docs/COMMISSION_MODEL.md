# Commission Model

## Purpose

This document defines how Taja can charge commission from sellers in a marketplace model similar to large commerce platforms.

## Commission Principles

| Principle | Meaning |
|---|---|
| Category-based | Different product categories can have different commission rates |
| Transparent | Sellers should know the rate before listing or selling |
| Traceable | Commission must be visible in reports and settlements |
| Flexible | Rates can change by strategy, category, or promotion |
| Fair | Rates should match category economics and platform value |

## Suggested Category Model

| Category | Example Items | Suggested Commission |
|---|---|---:|
| Electronics | Phones, accessories, gadgets | 8% |
| Fashion | Clothing, shoes, bags | 12% |
| Beauty | Makeup, skincare, hair products | 10% |
| Home and Kitchen | Appliances, cookware, home goods | 10% |
| Groceries | Food items, household essentials | 6% |
| Health | Supplements, wellness items | 8% |
| Books and Learning | Books, course materials | 5% |
| Baby and Kids | Baby care, toys, kids items | 9% |
| Sports and Outdoors | Fitness and outdoor gear | 9% |
| General Marketplace | Mixed or uncategorized items | 10% |

## Commission Calculation

| Field | Example |
|---|---|
| Product price | 20,000 |
| Commission rate | 10% |
| Commission amount | 2,000 |
| Seller payout before fees | 18,000 |

Formula:

```text
commission_amount = product_price * commission_rate
seller_payout = product_price - commission_amount
```

## Operational Rules

| Rule | Requirement |
|---|---|
| Category assignment | Every product should belong to a commission category |
| Seller visibility | Commission should be visible in seller reports |
| Admin override | Admins can override special cases if needed |
| Historical tracking | Past commission records should remain auditable |
| Settlement accuracy | Payout calculations must use the right commission rate |

## Reporting Fields

| Field | Description |
|---|---|
| Order ID | Unique order reference |
| Seller ID | Seller account reference |
| Category | Product commission category |
| Gross amount | Total before commission |
| Commission rate | Applied percentage |
| Commission amount | Deducted platform fee |
| Net payout | Amount due to seller |

## Summary

The commission model should help Taja earn revenue while remaining clear and predictable for sellers.
