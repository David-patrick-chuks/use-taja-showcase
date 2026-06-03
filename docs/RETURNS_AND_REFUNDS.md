# Returns and Refunds

## Purpose

This document defines how Taja should handle customer returns, seller claims, and refunds.

## Core Principles

| Principle | Meaning |
|---|---|
| Clear policy | Users should know what can be returned and when |
| Buyer protection | Customers should have a fair dispute window |
| Seller protection | Sellers should be protected from abuse and false claims |
| Traceability | Every return and refund should be logged |
| Operational speed | Cases should not stay unresolved longer than necessary |

## Return Types

| Type | Description |
|---|---|
| Wrong item | Customer received the wrong product |
| Defective item | Product arrived damaged or not working |
| Not as described | Listing did not match the actual item |
| Change of mind | Customer returns under allowed policy rules |
| Delivery failure | Item could not be delivered or was refused |

## Refund Flow

| Step | System Action |
|---|---|
| 1 | Customer opens a return or refund request |
| 2 | System captures reason and order details |
| 3 | Support or automation reviews the case |
| 4 | If valid, refund is approved or return is created |
| 5 | Payment and settlement states are updated |
| 6 | Customer and seller receive status updates |

## Return Decision Table

| Case | Default Outcome |
|---|---|
| Wrong item | Refund or replacement review |
| Defective item | Refund, replacement, or seller claim |
| Change of mind | Policy-based approval or rejection |
| Delivery failure | Refund or return-to-seller handling |
| Fraud or abuse | Escalation and possible restriction |

## Required Data

| Field | Description |
|---|---|
| Order ID | Link to the original order |
| User ID | Customer account reference |
| Seller ID | Seller account reference |
| Return reason | Reason selected by the customer |
| Evidence | Photo, video, or message proof |
| Status | Open, approved, rejected, resolved |
| Resolution | Refund, replacement, return, or denial |

## Operational Rules

| Rule | Requirement |
|---|---|
| Timeliness | Requests should be handled within a clear SLA |
| Evidence | Claims should support photos, videos, or chat history when needed |
| Settlement impact | Refunds should be reflected in payout logic |
| Audit trail | Every decision should be recorded |
| Communication | Customer and seller should both see the outcome |

## Summary

Returns and refunds should reduce friction without creating abuse risk.
