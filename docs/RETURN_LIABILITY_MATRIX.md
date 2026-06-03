# Return Liability Matrix

## Purpose

This document gives the team a fast reference for who bears the financial impact in each return scenario.

## Liability Matrix

| Scenario | Primary Cause | Financial Impact | Operational Outcome |
|---|---|---|---|
| Wrong item delivered | Seller or fulfillment error | Seller bears the loss unless policy says otherwise | Customer may receive refund, replacement, or return processing |
| Fake product delivered | Seller violation | Seller bears the loss | Listing may be removed and account may be reviewed |
| Defective item delivered | Seller product quality issue | Seller bears the loss | Return is validated and settlement may be reversed |
| Not as described | Listing mismatch | Seller bears the loss | Support reviews the claim and may approve refund or return |
| Customer valid return after delivery | Customer exercises allowed return right | Seller may be debited for item value | After-sales validates the return reason |
| Customer change of mind | Customer preference | Policy dependent | Return may be approved or rejected based on category policy |
| Failed delivery | Logistics failure | Marketplace or logistics flow absorbs the operational issue | Item is returned to seller or handled by fulfillment |
| Customer refused at doorstep | Delivery refusal | Marketplace or logistics flow handles the item return | Item returns to seller or is processed through returns flow |
| Returned item lost in transit | Marketplace logistics failure | Marketplace compensates the seller | Seller receives item value compensation according to policy |
| Return not completed within SLA | Marketplace operational failure | Marketplace may owe compensation | Case is escalated and settlement is reviewed |

## Decision Rules

| Rule | Meaning |
|---|---|
| Seller fault | Seller bears the financial impact when the issue originates from the product or listing |
| Customer-approved return | If the return is valid under policy, the seller statement can be debited or offset |
| Logistics failure | If the marketplace or logistics flow loses the item, the seller should not carry the full loss |
| Policy-dependent cases | Change-of-mind returns can depend on category rules and return window rules |
| Auditability | Every decision should be visible in the return and settlement records |

## Suggested System Actions

| System Event | Suggested Action |
|---|---|
| Return approved | Mark return as validated and update payout exposure |
| Return rejected | Keep original settlement path unless policy says otherwise |
| Seller debit required | Offset seller balance or statement line item |
| Marketplace compensation required | Create compensation entry and notify finance |
| Dispute open | Freeze settlement until review is complete |

## Summary

The matrix should help product, support, finance, and engineering apply the same logic to every return case.
