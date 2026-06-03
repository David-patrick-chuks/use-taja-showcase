# Fees and Taxes

## Purpose

This document brings together the main fees, taxes, and deductions that can apply in the Taja marketplace.

## Fee Categories

| Fee Type | What It Covers | When It Applies |
|---|---|---|
| Commission | Marketplace fee charged on seller sales | Every successful sale |
| VAT | Tax applied to eligible fees or services | When required by law or policy |
| Shipping contribution | Part of delivery cost shared by seller or buyer | When shipping is required |
| Sponsored products | Paid promotion for visibility | When seller chooses ads or promotion |
| Penalties | Deduction for policy violations or operational issues | When rules are broken |

## Launch Fee Strategy

Taja should begin with a simple, predictable fee system:

| Fee Type | Launch Approach |
|---|---|
| Commission | Category-based, moderate, and transparent |
| VAT | Applied to fees where required |
| Shipping contribution | Kept simple and easy to explain |
| Sponsored products | Optional, separate from core commission |
| Penalties | Used sparingly and only for clear violations |

## Recommended Operating Model

| Charge | Recommendation |
|---|---|
| Seller commission | Charged per category |
| VAT on commission | Added to commission where applicable |
| VAT on sponsored products | Added to ad or service fees where applicable |
| Shipping support | Can be shared or subsidized depending on strategy |
| Refund handling | Commission policy should define how reversals are handled |

## Fee Calculation Stack

```text
gross_sale_amount
- base_commission
- VAT on commission
- shipping contribution if applicable
- optional ad or sponsored product fees
= seller net payout before refunds or adjustments
```

## Example Fee Breakdown

| Item | Amount |
|---|---:|
| Product price | 10,000 |
| Base commission | 800 |
| VAT on commission | 60 |
| Shipping contribution | 500 |
| Sponsored product fee | 0 |
| Seller payout before refunds | 8,640 |

## Administrative Rules

| Rule | Requirement |
|---|---|
| Clear display | Show each fee line separately where possible |
| Audit trail | Keep a record of every fee deduction |
| Policy updates | Any fee change should be versioned and communicated |
| Seller visibility | Sellers should see the fee logic in their dashboard |
| Tax compliance | Tax handling must follow the operating jurisdiction |

## Reference to Commission Model

For category commission values and VAT-inclusive commission logic, see [docs/COMMISSION_MODEL.md](docs/COMMISSION_MODEL.md).

## Summary

The fee system should be easy to understand at launch and flexible enough to grow with the business.

## Research Note

Public Jumia VendorHub pages show a fee stack that includes:

- category-based commission
- VAT included in commission calculations
- shipping cost contribution as a separate fee concept
- sponsored products as a separate paid service

That is why Taja should treat fees as a layered model instead of one flat marketplace charge.
