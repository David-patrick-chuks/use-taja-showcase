# Payments and Payouts

## Purpose

This document defines how money moves through Taja for buyers, sellers, and the platform.

## Payment Flow

| Stage | Description |
|---|---|
| Checkout | Customer confirms cart and shipping details |
| Payment initiation | System starts payment collection |
| Payment confirmation | Status updates after success or failure |
| Receipt generation | Transaction proof is created |
| Refund handling | Failed or reversed transactions are handled |

## Payout Flow

| Stage | Description |
|---|---|
| Seller earns balance | Orders completed and eligible for payout |
| Payout request | Seller or system requests withdrawal |
| Verification | Check payment or bank details |
| Disbursement | Money is sent to seller |
| Reconciliation | Record payout result and history |

## Payment Status Table

| Status | Meaning |
|---|---|
| Pending | Payment has started but not completed |
| Successful | Payment completed successfully |
| Failed | Payment did not go through |
| Refunded | Money returned to the customer |
| Disputed | Payment or order is under review |

## Payout Status Table

| Status | Meaning |
|---|---|
| Pending | Withdrawal requested |
| Processing | Being reviewed or sent |
| Paid | Payout completed |
| Failed | Payout did not complete |
| On hold | Temporary pause for review |

## Operating Rules

| Rule | Requirement |
|---|---|
| One source of truth | Payment state must be stored consistently |
| Auditability | Every money movement should be traceable |
| Seller trust | Payout status should be visible and clear |
| Error handling | Failed payments and payouts need clear recovery paths |

## Summary

Payments and payouts should feel trustworthy, visible, and easy to reconcile for both customers and sellers.
