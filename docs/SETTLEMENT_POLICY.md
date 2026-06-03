# Settlement Policy

## Purpose

This document defines how seller funds should move through Taja after a customer places an order.

It is based on a marketplace statement-and-settlement model, adjusted for Taja’s launch strategy and risk controls.

## Research Summary

Public marketplace vendor documentation shows a statement-based settlement model:

| Observation | Source Behavior |
|---|---|
| Delivered orders appear in Open Statement | Current week earnings are tracked before payout |
| Open Statement moves to Due and Unpaid | Amounts become ready to transfer after the weekly statement closes |
| Payouts follow the weekly cycle | Seller funds are released in the next payout run |
| Return handling affects settlement timing | Disputes and returns can delay or reverse settlement |

Public marketplace return and dispute pages also show that:

| Observation | Source Behavior |
|---|---|
| Returned or refused items may still be processed after delivery | Refund or return processing can continue after the initial delivery event |
| Claims must be raised quickly | Sellers have a short window to raise a return claim |
| Counterfeit or damaged items can trigger stronger controls | Funds may be withheld or penalties applied |

## What Taja Should Do

Taja should not rely on a vague fixed release delay alone.

Instead, it should use a hybrid model:

| Layer | Rule |
|---|---|
| Escrow | Customer payment is held until order state is safe for release |
| Return window | Funds are not fully released until the return window expires |
| Weekly payout run | Seller balances are paid out on a weekly schedule |
| Dispute freeze | Settlement is paused if a dispute, refund, or quality issue is open |

## Recommended Settlement Model

| Event | System Action |
|---|---|
| Order paid | Move funds into held balance |
| Order delivered | Start the return window timer |
| Return window expires | Mark funds eligible for settlement |
| Weekly payout close | Move eligible funds into due balance |
| Payout day | Transfer funds to seller |
| Dispute opened | Freeze settlement until resolution |

## Suggested Taja Policy

| Rule | Recommendation |
|---|---|
| Delivery hold | Hold funds after delivery until return window closes |
| Return window | 7 days after confirmed delivery for standard items |
| Weekly payout | Release eligible balances in a weekly payout cycle |
| High-risk categories | Use longer review or reserve periods if needed |
| Disputed orders | Freeze payout until the issue is resolved |

## Why This Works

| Benefit | Explanation |
|---|---|
| Buyer protection | Buyers can report issues within the return window |
| Seller clarity | Sellers know when funds become eligible |
| Cash flow predictability | Weekly payout runs are easy to understand |
| Risk control | Fraud, refusals, and damaged items can be reviewed before release |
| Marketplace trust | A clear settlement policy improves confidence on both sides |

## Settlement States

| State | Meaning |
|---|---|
| Pending payment | Order not yet paid |
| Held in escrow | Payment received but not releasable |
| Return window active | Delivery happened and funds are waiting |
| Eligible for settlement | Funds can be included in the next payout run |
| Due and unpaid | Funds are scheduled for transfer |
| Paid | Seller has received the payout |
| Frozen | Dispute or issue prevents release |

## Example Timeline

| Day | Order State | Settlement State |
|---|---|---|
| Day 0 | Customer pays | Held in escrow |
| Day 1 | Order delivered | Return window active |
| Day 7 | Return window ends | Eligible for settlement |
| Weekly payout day | Funds are processed | Due and unpaid to paid |

## Example Workflow

| Step | Description |
|---|---|
| 1 | Buyer pays for the order |
| 2 | Taja holds the seller balance in escrow |
| 3 | Item is delivered to the customer |
| 4 | Return window starts |
| 5 | If no dispute is raised, funds become eligible |
| 6 | On the next weekly payout run, seller is paid |

## Operational Rules

| Rule | Requirement |
|---|---|
| Traceability | Every state change must be logged |
| Refund safety | Refunds should be able to reverse or offset pending settlement |
| Admin control | Support and finance should be able to freeze or release cases where appropriate |
| Clear reporting | Seller dashboards should show held, due, and paid balances |
| Consistent timing | Payout timing should be predictable and documented |

## What Not To Do

| Anti-Pattern | Why Avoid It |
|---|---|
| Immediate release on delivery | Too risky for returns and disputes |
| Unclear ad hoc holds | Confuses sellers and support teams |
| No payout schedule | Makes revenue planning difficult |
| Silent reversals | Breaks trust with sellers |

## Recommendation

For Taja, the best structure is:

```text
Buyer pays -> Escrow -> Delivery confirmed -> 7-day return window -> Weekly payout run -> Seller paid
```

This keeps the model simple, safe, and close to how a real marketplace should operate.

## Research References

- Public marketplace account statement documentation
- Public marketplace return management documentation
- Public marketplace returns and dispute documentation

## Summary

Taja should use a weekly settlement cycle with a return window and dispute freeze, rather than a vague fixed release delay.
