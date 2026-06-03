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
| VAT-inclusive fee design | The final fee can include VAT on top of the base commission, just like a real marketplace fee stack |

## Suggested Category Model

| Category | Example Items | Suggested Commission |
|---|---|---:|
| Electronics | Phones, accessories, gadgets | 6% |
| Fashion | Clothing, shoes, bags | 8% |
| Beauty | Makeup, skincare, hair products | 7% |
| Home and Kitchen | Appliances, cookware, home goods | 7% |
| Groceries | Food items, household essentials | 4% |
| Health | Supplements, wellness items | 6% |
| Books and Learning | Books, course materials | 4% |
| Baby and Kids | Baby care, toys, kids items | 6% |
| Sports and Outdoors | Fitness and outdoor gear | 6% |
| General Marketplace | Mixed or uncategorized items | 7% |

## Launch Recommendation

To keep Taja startup-friendly at launch, use lower commission rates first and adjust later based on volume, seller adoption, and category economics.

| Launch Tier | Commission Approach |
|---|---|
| Early launch | Keep rates low and easy to explain |
| Growth phase | Review category performance and margin needs |
| Mature phase | Adjust rates by category, service cost, and seller segment |

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

## VAT-Inclusive Marketplace Fee Model

Jumia’s public VendorHub commissions page states that VAT increased to 7.5% and that the commission fee is inclusive of VAT. That means the platform fee should be treated as:

```text
base_commission = product_price * commission_rate
vat_on_commission = base_commission * 0.075
total_commission = base_commission + vat_on_commission
seller_payout = product_price - total_commission
```

Example:

| Field | Value |
|---|---:|
| Product price | 5,000 |
| Base commission rate | 6% |
| Base commission | 300 |
| VAT on commission | 22.50 |
| Total commission | 322.50 |
| Seller payout before other deductions | 4,677.50 |

This is the model we should use if we want Taja to behave like a category-based marketplace with a tax-inclusive fee structure.

## Strategic Direction

| Principle | Taja Recommendation |
|---|---|
| Keep entry low | Use conservative launch fees to attract sellers |
| Stay transparent | Show fee breakdowns in seller reports |
| Reward scale | Consider lower commissions for high-volume or strategic categories |
| Avoid fee confusion | Separate commission, VAT, shipping, and promotions |
| Protect trust | Do not introduce hidden charges |

## Operational Rules

| Rule | Requirement |
|---|---|
| Category assignment | Every product should belong to a commission category |
| Seller visibility | Commission should be visible in seller reports |
| Admin override | Admins can override special cases if needed |
| Historical tracking | Past commission records should remain auditable |
| Settlement accuracy | Payout calculations must use the right commission rate |
| VAT clarity | Fee statements should separate base commission and VAT when possible |

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

Research note:

- Jumia VendorHub publicly states that VAT for goods and services was increased to 7.5%.
- Its commissions page also states that commission fees are inclusive of VAT.
- The same page shows a Phones and Tablets example with a 6% base commission and VAT added on top of that commission amount.
